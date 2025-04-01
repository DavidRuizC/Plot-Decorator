
# 📊 Plot Decorator in Python

This project implements a flexible **plotting system** in Python using the **Decorator design pattern**. It allows users to dynamically compose matplotlib plots with various features such as titles, grids, labels, and extrema markers—**without modifying the core plotting logic**.

## 🎯 Goal

To demonstrate how the **Decorator Pattern** can simplify plot customization by composing behavior through layered decorators instead of writing large, complex functions.

## 🧩 Project Structure

- `Plot.py`: Contains the abstract base classes for plots and decorators.
- `PlotDecorator.py`: Defines all plot decorators (Grid, Labels, Title, Size, Legend, Mean, Global and Local Extrema).
- `main.py`: Example usage demonstrating how to create different plot configurations by chaining decorators.

## 🧠 Key Concepts

- **Decorator Pattern**: Adds behavior to individual objects without affecting others. Each feature (e.g., grid, title, labels) is implemented as a decorator class that wraps a plot object.
- **High Cohesion**: Each class has a single, well-defined responsibility, in line with the GRASP design principles.
- **Modularity & Extensibility**: Easily add new features by creating new decorators.

## ▶️ How to Run

1. Make sure you have `matplotlib` and `numpy` installed:
   ```bash
   pip install matplotlib numpy
   ```

2. Run the main script:
   ```bash
   python main.py
   ```

This will generate multiple plots with different combinations of features.

## 💡 Example

Here’s how a decorated plot is built in `main.py`:

```python
p_full = PlotSize(18, 18,
            PlotTitle('full',
                PlotLabels('x','sin(x)/x',
                    PlotLegend(
                        PlotGrid(
                            PlotMean(
                                PlotGlobalExtrema(
                                    PlotLocalExtrema(
                                        PlotBasic()))))))))
```

This produces a full-featured plot with:
- Custom size
- Title
- Axis labels
- Grid
- Mean line
- Global and local extrema
- Legend

## 📝 Explanation
The decorator works by adding responsibilities to individual objects dynamically and without affecting other objects. Each element (grid, title, etc.) is added independently, forming a chain. This improves modularity and follows the GRASP principle of high cohesion.

## 📄 License

This project is open source and available under the [MIT License](LICENSE).
