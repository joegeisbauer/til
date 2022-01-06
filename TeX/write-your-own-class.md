# Write Your Own Class

## The initial Setup
The first two lines below are needed by every LaTeX class. You need to define the LaTeX edition depedency using the first line. The second line defines the class name, the date it was created, and a small description for the class. The small description is helpful for letting others know how the class should be used in LaTeX documents. This should all be saved in a file that has the format `<className>.cls`, e.g. testClass.cls for the example below here.

```latex
\NeedsTeXFormat{LaTeX2e}
\ProvidesClass{testClass}[2022/01/06 Class for til purposes]

\LoadClass{article}
\RequirePackage{xcolor}
```

The last two lines are how you load classes that act as dependencies for your class, and how you include LaTeX packages that are needed to ensure your class works properly.

There is still a lot more to come for this, but this will generally get you started and let you start messing around with LaTeX classes in general.