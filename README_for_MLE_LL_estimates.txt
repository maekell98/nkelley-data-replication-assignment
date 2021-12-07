A tab-delimited text file containing parameter estimates and
log-likelihood values obtained from fitting 8 probability
distributions to 182 datasets on clutch or litter size
distributions. Species, data sources, and models are described in
the associated publication.

Each row is the fit of a particular model to a particular dataset.

There are 14 columns, with the following headings:

ID: Row identifier

Species: Short species name, with a number appended if multiple
datasets were analyzed for the same species

DistributionName: Name of the probability distribution being fit to
the data

Parameter1Name: Name of the first parameter of the distribution

Parameter1Value: Maximum likelihood estimate of the first parameter

Parameter2Name: Name of the second parameter of the distribution (if
applicable; otherwise blank)

Parameter2Value: Maximum likelihood estimate of the second parameter
(if applicable; otherwise blank)

Parameter3Name: Name of the third parameter of the distribution (if
applicable; otherwise blank)

Parameter3Value: Maximum likelihood estimate of the third parameter
(if applicable; otherwise blank)

Loglikelihood: log-likelihood of the fitted model

AIC: AIC (Akaike Information Criterion) value of the fitted model

Loglikelihood_Empirical: log-likelihood of the saturated model (true
distribution taken to be identical to observed distribution)

AIC_Empirical: AIC value of the saturated model

MaxNestSize: Maximum clutch or litter size in the dataset (used to
determine number of parameters in the saturated model)
