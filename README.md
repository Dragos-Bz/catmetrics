# catmetrics
Repository for the stata command called "catmetrics"

## Overview

catmetrics is a Stata and Mata package that computes a broad catalogue of association, correlation, and forecast accuracy metrics for categorical variables. The package was formerly named classify and has since been renamed to catmetrics. It provides a unified interface for calculating 257 metrics, each documented in an accompanying help file, and is intended for researchers who evaluate agreement, association, or predictive performance between categorical measures.

The package is developed under the supervision of Andriy Sirchenko at the University of Amsterdam, as part of a broader initiative to publish methodological Stata tools in the Stata Journal. Development is carried out jointly with Konrad Wrebiac.

## Installation

Instructions for installing the package from the Stata Journal archive or from source will be provided upon publication.

## Core Files

The package consists of the following components.

* classify.ado, the main program computing the selected metrics
* estimates.ado, handling storage and presentation of results
* helpfunctest.ado, containing helper routines used across the package
* test_metrics.ado, used for internal validation of metric computations
* metric_ranges.ado, defining valid ranges and bounds for each metric

## Options

The package supports the following functionality.

* A SYMMETRIC option, which reports the symmetry classification of each requested metric using four categories: Truly Symmetric (TS), Conditionally Symmetric (CS), Conditionally Truly Symmetric (CTS), and Asymmetric (AS). When exported, results include a dedicated Symmetry column.
* A metrics() option, allowing users to specify a subset of metrics by name or index rather than computing the full catalogue.
* A noexcel option, suppressing export of results to an Excel workbook.
* Probabilistic score selection through tokens p1 through p11, allowing users to request specific probabilistic scoring rules without listing each metric individually.
* Warnings for input that is not an integer or that contains missing values, ensuring users are alerted before metrics are computed on unsuitable data.

## Metric Catalogue

The package implements a catalogue of 257 metrics of categorical association, correlation, and forecast accuracy. Metrics recently added or revised include gilbert_wells, log_forbes, cohen_pi, fleiss_kappa, and a generalized family of Fleiss metrics indexed 102 through 115. The catalogue has also undergone correction of indexing errors and renaming of entries, including the renaming of cole_c7 to galton and austin_colwell to goodall, to align terminology with the metrics' original sources.

## Symmetry Classification

A separate line of methodological work underlies the SYMMETRIC option. This research examined, both analytically and through Mata based simulation, whether individual metrics satisfy properties of symmetry under exchange of rows and columns in a contingency table. Metrics studied in this context include Discrimination Distance (metric 51), the Forbes and Loevinger H statistic (metric 68), Gini 3 (metric 81), Goodman Concomitance (metric 84), and Pollack Norman (metric 153).

Findings from this work include the following.

* Asymmetric measures that depend only on column proportions are algebraically Conditionally Symmetric in two by two tables.
* The original formulation of Gini 3 contained errors that mixed row and column marginals, which have since been corrected.
* Goodman Concomitance was confirmed to be genuinely Truly Symmetric.

## Authors and Acknowledgements

catmetrics is developed by Konrad Wrebiac and Dragos Binzari, under the supervision of Andriy Sirchenko at the University of Amsterdam. The package builds upon and extends the metric catalogue introduced in Huismans, Nijenhuis, and Sirchenko (2023).

## References

Huismans, N., Nijenhuis, J., and Sirchenko, A. (2023). Details to be completed with full citation information.

## License

License information to be added prior to publication.
