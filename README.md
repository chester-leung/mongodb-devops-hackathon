# mongodb-devops-hackathon

* Difficult to differentiate between large language models
  * Gap between open and closed source models are closing
  * Difficult to even quantify and compare different models -- all benchmarks are novel
* In this age of data, data will be the differentiator -- and the moat
  * Leading to the rise of domain-specific models
* Companies will leverage the specific data they have to build proprietary models specific to their domain
  * e.g., an oil and gas company will have proprietary models trained on terminology and data specific to their industry. A derivatives company will have proprietary models trained on financial data and terminology

* Today, even with the growing adoption of the cloud, companies that care about security and privacy are unwilling to transmit data outside their environment, which may be on-prem --> if companies want to monetize their proprietary, domain-specific models quickly, they may have to serialize / share the model with the customer, and have the customer host it in their environment
    * How can companies do this without exposing the internals of their models (e.g. weights) with the customer? How can they trust that the customer won't deploy their model on some infrastructure that will create a back-door to access the model?
    
* Customer can provide a "confidential computing environment", on which the model can be securely deployed. In this case, secure means:
    * The internals of the model remain confidential at all times, even to the customer, and that the model itself is not tampered with
    * The model provider receives a digital signature, signed by the hardware manufacturer (e.g. Intel, AMD, NVIDIA), that the model is running 1) on genuine hardware, and 2) in an environment that is running code that they expect, i.e. the environment has not been tampered with.
    * The model provider does not have to trust the customer to do what was agreed on. Instead, the model provider can trust the cryptographic proofs provided by the hardware manufacturer.