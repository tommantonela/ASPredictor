# ASPredictor

This prototype tool supports the prediction of dependency-based Architectural Smells and also the evaluation of those predictions using a sequence of system versions. **ASPredictor** is designed as a pipeline of processing components. Each component receives a number of inputs and generates outputs for other components downstream. 

The main functionality consists of three steps, namely: pre-processing, classification construction, and smell prediction.

![Tool Pipeline Overview](https://github.com/tommantonela/ASPredictor/blob/gh-pages/tool_pipeline.png)

-  _Extract-Detect_. Parses Java source code from predefined versions and extracts packages dependency graphs, relying on a Java static analyzer. 

- _Dep-Pred_. Takes two dependency graphs as inputs, and produces an ordered list of predicted dependencies, relying on  a trained binary classifier.

- _Smell-Pred_. Receives dependency graphs and the predicted dependencies, and identifies potentially ”new” AS in the expanded graph to appear in the next system version, which are ranked according to their relevance. Currently, three types of smells are supported: cyclic dependencies, hub-like dependencies and unstable dependencies.

- _Eval_. Compares the predicted dependencies and/or smells with the actual dependencies/smells, and computes typical Machine Learning metrics such as: precision, recall, F-measure and nDCG.

**ASPredictor** is licenced under the Apache License V2.0. Copyright 2019 - ISISTAN - UNICEN - CONICET

**Contact information**:
- _Antonela Tommasel_ (ISISTAN, CONICET-UNICEN. Argentina) antonela.tommasel@isistan.unicen.edu.ar 
- _J. Andres Diaz-Pace_ (ISISTAN, CONICET-UNICEN. Argentina) andres.diazpace@isistan.unicen.edu.ar 


A description of the software features and usage can be found in the project's [Wiki](https://github.com/tommantonela/ASPredictor/wiki).

