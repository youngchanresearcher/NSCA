# NSCA: Necessary-and-Sufficient Condition Analysis in R

[![CRAN status](https://www.r-pkg.org/badges/version/NSCA)](https://CRAN.R-project.org/package=NSCA)
[![CRAN downloads](https://cranlogs.r-pkg.org/badges/grand-total/NSCA)](https://CRAN.R-project.org/package=NSCA)

**NSCA** is an R package for **Necessary-and-Sufficient Condition Analysis (NSCA)**, a method within condition analysis in degree. It tests and quantifies bivariate statements in which a condition is both necessary and sufficient for an outcome.

A necessary-and-sufficient statement predicts two empty corners at once, on diagonally opposite sides of the same scatter plot. NSCA estimates both empty spaces together: the necessity side with the NCA package and the sufficiency side with SCAtools. The two empty spaces and the region between them divide the scope, so the reported areas follow from one identity.

## What NSCA does

- Maps each necessary-and-sufficient direction (`"HH"`, `"HL"`, `"LH"`, `"LL"`; condition level first, outcome level second) to its two empty corners and component statements
- Estimates the necessity and sufficiency frontiers on the same scatter plot
- Reports the **joint strength** of the two components, the share of the scope the claims rule out, and the region of the data that remains admissible
- Decides significance by combining two directional **permutation tests**
- Produces a **dual threshold table** and the necessity-sufficiency interval
- Can draw an ordinary least-squares line as a central-tendency reference only; it never enters either claim

## Installation

Install the released version from CRAN. This also installs SCAtools and NCA:

```r
install.packages("NSCA")
```

## Quick example

```r
library(NSCA)

set.seed(1)
x <- sort(runif(60))
dat <- data.frame(X = x, Y = pmin(pmax(x + rnorm(60, 0, 0.1), 0), 1))

# The default 1,000 permutations take several seconds.
nsca(dat, "X", "Y")
```

## Main functions

| Function | Purpose |
|---|---|
| `nsca()` | Quick necessary-and-sufficient condition analysis |
| `nsca_analysis()` | Full necessary-and-sufficient condition analysis |
| `nsca_plot()` | Plot both frontiers |
| `nsca_joint()` | Joint strength of the two components |
| `nsca_thresholds()` | Dual thresholds and the necessity-sufficiency interval |
| `nsca_table()` | Joint necessity and sufficiency results |
| `nsca_corners()` | Empty corners of a necessary-and-sufficient statement |
| `nsca_terms()` | Terminology of condition analysis in degree |

## Related packages

- [SCAtools](https://github.com/youngchanresearcher/SCAtools): Sufficient Condition Analysis, used by NSCA for the sufficiency side
- [NCA](https://CRAN.R-project.org/package=NCA): Necessary Condition Analysis, used by NSCA for the necessity side

## Citation

If you use NSCA, please cite:

Chan, Y. (2026). *From necessity to sufficiency and necessity-and-sufficiency: Condition analysis in degree* [Working paper]. University of Leeds.

Chan, Y. (2026). *NSCA: R package for necessary-and-sufficient condition analysis* [R package]. https://github.com/youngchanresearcher/NSCA

## Contact

Young Chan, University of Leeds

Email: youngchanresearcher@gmail.com

ORCID: [0000-0003-4859-4218](https://orcid.org/0000-0003-4859-4218)

Questions and bug reports: [GitHub issues](https://github.com/youngchanresearcher/NSCA/issues)

## License

GPL (>= 3)
