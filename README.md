# Scindo Delivery

#### il progetto è stato sviluppato per ottenere due api endpoint

# 1) training pipeline:

#### training_pipeline consiste 3 classi che fanno i parassi della creazione di modelli.
####   - input_controller:
#####    controlla l'esistenza e correttezza del file csv (input)
######   esempio: (https://github.com/bizhanzahedi/scindo_final_delivery/tree/main/input)
####   - input_ingestor:
#####    consiste la preparazione di un pandas dataframe pronto per modelli ML
####   - trainer:
#####    addestra e salva i modelli nella cartella [/built_models](https://github.com/bizhanzahedi/scindo_final_delivery/tree/main/built_models)
#####    le metriche reportistiche del modello viene salvato nella cartella /report 


# 2) prediction pipeline
