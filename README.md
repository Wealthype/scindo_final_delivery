# Scindo Delivery

#### il progetto è stato sviluppato per ottenere due api endpoint

# 1) training pipeline:

#### training_pipeline consiste 3 classi che fanno i prassi della creazione di modelli.
####   - input_controller:
#####    controlla l'esistenza e correttezza del file CSV [/input](https://github.com/bizhanzahedi/scindo_final_delivery/tree/main/input)
####   - input_ingestor:
#####    consiste la preparazione di un pandas dataframe pronto per addestrare modelli ML
####   - trainer:
#####    addestra e salva i modelli nella cartella [/built_models](https://github.com/bizhanzahedi/scindo_final_delivery/tree/main/built_models)
#####    le metriche reportistiche del modello viene salvato nella cartella [/report](https://github.com/bizhanzahedi/scindo_final_delivery/tree/main/report) 


# 2) prediction pipeline
#### prediction pipeline consiste 3 classi che fanno i prassi dell'utilizzo di modelli.
####   - input_controller:
#####    controlla l'esistenza e correttezza delle chiavi e valori del file JSON [/input](https://github.com/bizhanzahedi/scindo_final_delivery/tree/main/input)
####   - input_ingestor:
#####    consiste la preparazione di un JSON pronto per modelli ML e BI
####   - predictor:
#####    interroga gli algoritmi di ML ([/built_models](https://github.com/bizhanzahedi/scindo_final_delivery/tree/main/built_models)), di prior ([/built_models](https://github.com/bizhanzahedi/scindo_final_delivery/tree/main/prior_default_probability_loans/output_model)), e di BI 
#####    l'output è un JSON del tipo:
    {
        'UserID': 1, 
        'default_probability': 0.0855, 
        'sign': 1
    }
##### sign = 1 : non erogare il prestito
##### sign = 0 : puoi erogare il prestito
