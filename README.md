[![Android](https://github.com/ceres-solver/ceres-solver/actions/workflows/android.yml/badge.svg)](https://github.com/ceres-solver/ceres-solver/actions/workflows/android.yml)
[![Linux](https://github.com/ceres-solver/ceres-solver/actions/workflows/linux.yml/badge.svg)](https://github.com/ceres-solver/ceres-solver/actions/workflows/linux.yml)
[![macOS](https://github.com/ceres-solver/ceres-solver/actions/workflows/macos.yml/badge.svg)](https://github.com/ceres-solver/ceres-solver/actions/workflows/macos.yml)
[![Windows](https://github.com/ceres-solver/ceres-solver/actions/workflows/windows.yml/badge.svg)](https://github.com/ceres-solver/ceres-solver/actions/workflows/windows.yml)

Ceres Solver
============

Ceres Solver is an open source C++ library for modeling and solving
large, complicated optimization problems. It is a feature rich, mature
and performant library which has been used in production at Google
since 2010. Ceres Solver can solve two kinds of problems.

1. Non-linear Least Squares problems with bounds constraints.
2. General unconstrained optimization problems.

Please see [ceres-solver.org](http://ceres-solver.org/) for more
information.


## Step-by-step user guide

1. **Install build prerequisites.** Follow the platform-specific [Ceres installation guide](http://ceres-solver.org/installation.html) for a C++ compiler, CMake, Eigen, and the optional sparse linear-algebra libraries you intend to use.
2. **Configure and build this checkout.** From the repository root, run <code>cmake -S . -B build -DCMAKE_BUILD_TYPE=Release -DBUILD_EXAMPLES=ON</code>, then <code>cmake --build build --parallel</code>. The project CMake file enables examples by default; the explicit option keeps the intended build clear.
3. **Run the first example.** Build and run the hello-world target with <code>cmake --build build --target helloworld</code> and <code>build/bin/helloworld</code> (on Windows, use the generated executable under the corresponding configuration directory). Read [examples/helloworld.cc](examples/helloworld.cc) to see how a residual functor becomes a least-squares problem and how the solver reports its result.
4. **Fit a real model.** Start with [examples/curve_fitting.cc](examples/curve_fitting.cc), then compare the automatic-differentiation, numeric-differentiation, and analytic-differentiation variants. Keep the data and initial guess fixed while changing one solver option at a time.
5. **Model your problem.** Add parameter blocks and residual blocks, select a cost/loss function, set bounds or manifolds as needed, and choose a dense or sparse linear solver suitable for the problem size. Use the [tutorial](http://ceres-solver.org/nnls_tutorial.html) to understand each choice.
6. **Validate and scale.** Inspect solver summaries and residuals, then try [robust_curve_fitting.cc](examples/robust_curve_fitting.cc), bundle adjustment, and the SLAM pose-graph examples. Use covariance and evaluation callbacks when you need uncertainty or per-iteration diagnostics.

### Functionality map

- Nonlinear least-squares and general unconstrained optimization; bounded parameter blocks; robust loss functions; automatic, numeric, and analytic Jacobians; manifolds; callbacks; and covariance estimation.
- Dense and sparse linear solvers, ordering/preconditioning controls, and options for large bundle-adjustment and SLAM problems.
- Browse [examples](examples/) for curve fitting, image denoising, bundle adjustment, interpolation, pose graphs, and solver callbacks. The [Ceres tutorial](http://ceres-solver.org/tutorial.html) and [API reference](http://ceres-solver.org/nnls_modeling.html) document the complete modeling and solver options.

