---
layout: default
mathjax: true
---

# Empirical Model Learning

This repository contains resources related to Empirical Model Learning (EML), a technique to enable Combinatorial Optimization and decision making over complex real-world systems. The method is based on the (relatively simple) idea of:

1. Using a Machine Learning (ML) model to approximate the input/output behavior of a system that is hard to model by conventional means.
2. Embedding such _Empirical Model_ into a Combinatorial Optimization model.

The emphasis of EML is mostly on the techniques to perform the embedding. These should be designed so that the optimization engine can exploit the structure of the empirical model to boost the search process.

The technique has been developed by researchers from the [University of Bologna](http://www.ai.unibo.it), but has connections to existing methods in other fields (see the survey link later on the page).

More information, including a thorough presentation of the method, a number of embedding techniques, and application example on two workload dispatching problems can be found on the "Empirical Decision Model Learning" paper [1], published on "Artificial Intelligence".

So far, the EML approach has been applied using:

* Artificial Neural Networks, Decision Trees, and Random Forests on the Machine Learning side
* Local Search, Mixed (Non) Linear Integer Programming, Constraint Programming, and SAT Modulo Theories on the optimization side.

## Applications

The range of potential applications of EML is quite vast and includes:

1. Applying Combinatorial Optimization to Complex Systems (in the proper sense), or systems that are too complicated to obtain an expert-design, hand-crafted model.
2. Enabling _prescriptive_ analytics by taking advantage of a pre-extracted _predictive_ analytics model.
3. Enable indirect interaction between a high-level optimizer and a lower-level optimizer (whose approximate behavior can be captured via Machine Learning).
4. Based on 3, it is possible to use EML to enable multi-level optimization and therefore optimization over large scale systems.
5. Self adapting systems, that could be obtained by retraining the Empirical Model

So far, the method has been applied to _two thermal-aware workload dispatching problems_. Both problems are defined over a multi-core CPU by Intel (called SCC) featuring thermal controllers that abruptly reduce the operating frequency of each core if a threshold temperature is exceeding.

Obtaining a hand-crafted model for this system is very difficult since:

1) The temperature of each core depends on a number of complex factors
2) The platform is subject to the action of low-level controllers (beside the thermal controller, each core is managed by an on-line, thermal-aware, scheduler).

EML allows to extract an approximate model from data and hence to define Combinatorial Optimization problems over this platform. In particular, we define:

**We are looking for more application examples!** If you manage to apply EML to a new problem, we would love to hear it and post a link on this web site.

## List of Resources

As mentioned, this web site is mostly a connection

### Main EML paper

The "Empirical Decision Model Learning" paper can be found:

* In pre-print format [on the personal collection of one of the authors](https://www.researchgate.net/publication/290480833_Empirical_decision_model_learning)
* In its published form [at its official link](https://www.sciencedirect.com/science/article/pii/S0004370216000126).

### Running Survey

EML is not the only approach to boost modeling of optimization problems by means of Machine Learning, and it it related to similar techniques in different fields. 

Rather than providing links directly in the web site, we are maintaining an updated survey on methods to integrate optimization and Machine Learning at the modeling level. The first version of the survey has been just accepted and published at IJCAI 2018.

* The current state of the survey (right now, the IJCAI 2018 submission) [can be found here](assets/papers/survey.pdf).
* The work can be cited as:

```
@inproceedings{DBLP:conf/ijcai/0001M18,
  author    = {Michele Lombardi and
               Michela Milano},
  title     = {Boosting Combinatorial Problem Modeling with Machine Learning},
  booktitle = {Proceedings {IJCAI}},
  pages     = {5472--5478},
  year      = {2018}
}
```

### EMLlib

We have just started to maintain a GitHub repository that implements techniques related to EML, including:

* Actual embedding techniques (encodings and global constraints)
* Pre- and post- processing methods
* I/O support (in particular readers for popular ML libraries)

The repository can be found at [https://github.com/emlopt/emllib](https://github.com/emlopt/emllib)

The repository is not limited to work by the University of Bologna group: it includes (or rather will include) implementations of other techniques that are closely related to EML. The code relies on a Python API and is work in progress: at the moment, only a fraction of the existing EML techniques have been included, but that number should grow quickly.

### EML Tutorial

On Jul 14 2018, we will publish an on-line repository containing the code for the EML tutorial held at IJCAI 2018.

The tutorial material is available at [https://github.com/emlopt/emltutorial](https://github.com/emlopt/emltutorial)

## Contacts

For more information, you can contact:

* [Michela Milano](mailto:michela.milano@unibo.it), full professor at University of Bologna
* [Michele Lombardi](mailto:michele.lombardi2@unibo.it), assistant professor at University of Bologna


## EML Related Publications

These are other publications about EML from the University of Bologna group:


**[1]** M. Lombardi, A. Bartolini, M. Milano: "Empirical Decision Model Learning" -- submitted to Artificial Intelligence (2015)"

```
@article{LombardiMB17,
  author    = {Michele Lombardi and
               Michela Milano and
               Andrea Bartolini},
  title     = {Empirical decision model learning},
  journal   = {Artif. Intell.},
  volume    = {244},
  pages     = {343--367},
  year      = {2017}
}
```

**[2]** Andrea Bartolini, Michele Lombardi, Michela Milano, Luca Benini: "Neuron Constraints to Model Complex Real-World Problems". CP 2011: 115-129

```
@inproceedings{BartoliniLMB11,
  author    = {Andrea Bartolini and
               Michele Lombardi and
               Michela Milano and
               Luca Benini},
  title     = {Neuron Constraints to Model Complex Real-World Problems},
  booktitle = {Proceedings of {CP}},
  pages     = {115--129},
  year      = {2011}
}
```

**[3]** Andrea Bartolini, Michele Lombardi, Michela Milano, Luca Benini: "Optimization and Controlled Systems: A Case Study on Thermal Aware Workload Dispatching". AAAI 2012

```
@inproceedings{BartoliniLMB12,
  author    = {Andrea Bartolini and
               Michele Lombardi and
               Michela Milano and
               Luca Benini},
  title     = {Optimization and Controlled Systems: {A} Case Study on Thermal Aware
               Workload Dispatching},
  booktitle = {Proceedings {AAAI}},
  year      = {2012}
}
```

**[4]** Michele Lombardi, Stefano Gualandi: A lagrangian propagator for artificial neural networks in constraint programming. Constraints 21(4): 435-462 (2016)

```
@article{LombardiG16,
  author    = {Michele Lombardi and
               Stefano Gualandi},
  title     = {A lagrangian propagator for artificial neural networks in constraint
               programming},
  journal   = {Constraints},
  volume    = {21},
  number    = {4},
  pages     = {435--462},
  year      = {2016}
}
```


**[5]** Michele Lombardi, Stefano Gualandi: "A New Propagator for Two-Layer Neural Networks in Empirical Model Learning". CP 2013: 448-463

```
@inproceedings{LombardiG13,
  author    = {Michele Lombardi and
               Stefano Gualandi},
  title     = {A New Propagator for Two-Layer Neural Networks in Empirical Model
               Learning},
  booktitle = {Proceedings of {CP}},
  pages     = {448--463},
  year      = {2013}
}
```

**[6]** Alessio Bonfietti, Michele Lombardi, Michela Milano: "Embedding Decision Trees and Random Forests in Constraint Programming". CPAIOR 2015: 74-90

```
@inproceedings{BonfiettiLM15,
  author    = {Alessio Bonfietti and
               Michele Lombardi and
               Michela Milano},
  title     = {Embedding Decision Trees and Random Forests in Constraint Programming},
  booktitle = {Proceedings of {CPAIOR}},
  pages     = {74--90},
  year      = {2015}
}
```

