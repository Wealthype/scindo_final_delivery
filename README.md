# Scindo Delivery

#### il progetto è stato sviluppato per ottenere due api endpoint

# 1) training pipeline:

#### training_pipeline consiste 3 classi che fanno i prassi della creazione di modelli.
####   - input_controller: controlla l'esistenza e correttezza del file CSV [input](https://github.com/bizhanzahedi/scindo_final_delivery/tree/main/input)
####   - input_ingestor: consiste la preparazione di un pandas dataframe pronto per addestrare modelli ML
####   - trainer: addestra e salva i modelli nella cartella [built_models](https://github.com/bizhanzahedi/scindo_final_delivery/tree/main/built_models)
####    le metriche reportistiche del modello viene salvato nella cartella [report](https://github.com/bizhanzahedi/scindo_final_delivery/tree/main/report) 


# 2) prediction pipeline
#### prediction pipeline consiste 3 classi che fanno i prassi dell'utilizzo di modelli.
####   - input_controller: controlla l'esistenza e correttezza delle chiavi e valori del file JSON [/input](https://github.com/bizhanzahedi/scindo_final_delivery/tree/main/input)
####   - input_ingestor: consiste la preparazione di un JSON pronto per modelli ML e BI
####   - predictor: interroga gli algoritmi di ML ([built_models](https://github.com/bizhanzahedi/scindo_final_delivery/tree/main/built_models)), di prior ([prior](https://github.com/bizhanzahedi/scindo_final_delivery/tree/main/prior_default_probability_loans/output_model)), e di BI 
####    l'output è un JSON del tipo:
    {
        'UserID': 1, 
        'default_probability': 0.0855, 
        'sign': 1
    }

##### sign è la decisione finale di algoritmi:
     sign =  {
         1 : non erogare il prestito
         0 : puoi erogare il prestito
     }

# config file
##### config file contiene le variabili utilizzati nelle classi

##### 1) le mappe:
######   sia il pipeline di training che il pipeline di prediction si aspettano valori codificati per evitare stringhe nelle file CSV e JSON
       map_Address, map_Gender, map_Position, map_Education, map_Sector, map_Device
######   i valori codificati vengono ulteriormente controllati
       encoded_variables


##### 2) le chiavi del JSON:
######   il pipeline di prediction si aspetta chiavi predefiniti, questo viene controllato
       variables_1st_layer, variables_user_layer, variables_behaviour_layer, variables_genericinfo_layer, variables_job_layer
       variables_finance_layer, variables_balance_layer, variables_cumsum_layer, variables_eop_layer, variables_totalloans_layer

##### 3) le colonne del CSV:
######   il pipeline di training si aspetta chiavi predefiniti, questo viene controllato
       all_variables

##### 4) la tipologia dei valori:
######   sia il pipeline di training che il pipeline di prediction si aspettano valori di un certo tipo predefinito, questo viene controllato
       string_variables, int_variables, float_variables, boolean_variables

##### 5) le variabili di natura numericha vengono scalati
       norm_vector

##### 5) le variabili di natura categorica vengono codificati (trasformati in bool)
       one_hot_encode
    
       
