---
title: Metriche di ML.NET
description: Informazioni sulle metriche usate per valutare le prestazioni di un modello ML.NET
ms.date: 12/17/2019
ms.openlocfilehash: 8e823fd8cc344c1b8e0ecd709b527137368cbfa0
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "75739600"
---
# <a name="evaluate-your-mlnet-model-with-metrics"></a>Valutare il modello ML.NET con le metriche

Informazioni sulle metriche usate per valutare un modello ML.NET.

Le metriche di valutazione sono specifiche del tipo di attività di Machine Learning eseguita da un modello.

Per l'attività di classificazione, ad esempio, il modello viene valutato misurando il modo in cui una categoria stimata corrisponde alla categoria effettiva. Per il clustering, la valutazione è basata sul modo in cui gli elementi del cluster si chiudono tra loro e sulla quantità di separazione tra i cluster.

## <a name="evaluation-metrics-for-binary-classification"></a>Metriche di valutazione per la classificazione binaria

| Metrica   |      Descrizione      |  Cercare |
|-----------|-----------------------|-----------|
| **Accuracy** |  [Accuracy](https://en.wikipedia.org/wiki/Accuracy_and_precision#In_binary_classification) o accuratezza corrisponde alla percentuale di stime corrette con un set di dati di test. Equivale al rapporto tra il numero di stime corrette e il numero totale di campioni di input. Funziona bene se è presente un numero simile di esempi appartenenti a ogni classe.| **Quanto più vicino a 1,00, tanto meglio**. Ma se il risultato è esattamente 1,00, significa che si è verificato un problema, in genere di tipo dispersione di dati (etichetta/destinazione), sovradattamento oppure uso di dati di training per il test. Quando i dati di test non sono bilanciati (dove la maggior parte delle istanze appartiene a una delle classi), il set di dati è di dimensioni ridotte o l'approccio con i punteggi 0,00 o 1,00, l'accuratezza non acquisisce effettivamente l'efficacia di un classificatore ed è necessario controllare le metriche aggiuntive. |
| **AUC** |    [aucROC](https://en.wikipedia.org/wiki/Receiver_operating_characteristic) o *area sotto la curva* misura l'area sotto la curva creata spostando il vero tasso positivo rispetto al tasso di falsi positivi.  |   **Quanto più vicino a 1,00, tanto meglio**. Deve essere maggiore di 0,50 affinché un modello sia accettabile. Un modello con AUC 0,50 o meno è inutile. |
| **AUCPR** | [aucPR](https://www.coursera.org/lecture/ml-classification/precision-recall-curve-rENu8) o *area sotto la curva di una curva di richiamo di precisione*: misura utile di esito positivo della stima quando le classi sono sbilanciate (set di impostazioni di set di impostazioni molto inclinati). |  **Quanto più vicino a 1,00, tanto meglio**. I punteggi elevati vicini a 1,00 mostrano che il classificatore restituisce risultati accurati (alta precisione), oltre a restituire una maggioranza di risultati tutti positivi (alto recupero). |
| **F1-score** | [F1 score](https://en.wikipedia.org/wiki/F1_score) anche detto *F-score bilanciato o F-measure*. Si tratta della media armonica di precisione e recupero. La metrica F1 Score è utile se si vuole trovare un equilibrio tra precisione e recupero.| **Quanto più vicino a 1,00, tanto meglio**.  F1-score raggiunge il valore ottimale con un punteggio 1,00 e il valore peggiore con 0,00. Indica il grado di precisione del classificatore. |

Per altre informazioni sulle metriche di classificazione binaria, vedere gli articoli seguenti:

- [Accuratezza, precisione, richiamo o F1?](https://towardsdatascience.com/accuracy-precision-recall-or-f1-331fb37c5cb9)
- [Classe BinaryClassificationMetrics](xref:Microsoft.ML.Data.BinaryClassificationMetrics)
- [The Relationship Between Precision-Recall and ROC Curves](http://pages.cs.wisc.edu/~jdavis/davisgoadrichcamera2.pdf)

## <a name="evaluation-metrics-for-multi-class-classification"></a>Metriche di valutazione per la classificazione multiclasse

| Metrica   |      Descrizione      |  Cercare |
|-----------|-----------------------|-----------|
| **Micro-Accuracy** |  L'[accuratezza micro-media](xref:Microsoft.ML.Data.MulticlassClassificationMetrics.MicroAccuracy) aggrega i contributi di tutte le classi per calcolare la metrica media. Corrisponde alla percentuale di istanze stimate correttamente. La micro-media non tiene conto dell'appartenenza a una classe. Essenzialmente, ogni coppia campione-classe contribuisce nello stesso modo alla metrica di accuratezza. | **Quanto più vicino a 1,00, tanto meglio**. In un'attività di classificazione multiclasse la micro-accuratezza è preferibile rispetto alla macro-accuratezza se si sospetta uno squilibrio di classi, ossia la presenza di molti più esempi di una classe rispetto ad altre.|
| **Macro-Accuracy** | L'[accuratezza macro-media](xref:Microsoft.ML.Data.MulticlassClassificationMetrics.MacroAccuracy) corrisponde all'accuratezza media a livello di classe. Viene confrontata l'accuratezza per ogni classe e l'accuratezza macro-media è la media di queste accuratezze. Essenzialmente, ogni classe contribuisce nello stesso modo alla metrica di accuratezza. Alle classi di minoranza viene assegnato un peso uguale a quello delle classi più grandi. La metrica della macro-media assegna lo stesso peso a ogni classe, indipendentemente dal numero di istanze di tale classe contenute nel set di dati. |  **Quanto più vicino a 1,00, tanto meglio**.  Calcola la metrica in modo indipendente per ogni classe e quindi ne considera la media, di conseguenza tratta tutte le classi allo stesso modo |
| **Log-loss**| La [perdita logaritmica](http://wiki.fast.ai/index.php/Log_Loss) misura le prestazioni di un modello di classificazione in cui l'input della stima è un valore di probabilità compreso tra 0,00 e 1,00. Questa metrica aumenta quando la probabilità stimata devia dall'etichetta effettiva. | **Quanto più vicino a 0,00, tanto meglio**. In un modello perfetto, log-loss sarebbe uguale a 0,00. L'obiettivo dei modelli di Machine Learning è ridurre al minimo questo valore.|
| **Log-Loss Reduction** | La [riduzione della perdita logaritmica](xref:Microsoft.ML.Data.MulticlassClassificationMetrics.LogLossReduction) può essere interpretata come un vantaggio del classificatore rispetto alla stima casuale.| **Il valore è compreso nell'intervallo da -inf a 1,00, dove 1,00 corrisponde a stime perfette e 0,00 indica stime medie**. Ad esempio, se il valore equivale a 0,20, può essere interpretato come "la probabilità di una stima corretta è il 20% maggiore rispetto alla stima casuale"|

La micro-accuratezza è generalmente più indicata per le esigenze aziendali di stime di ML. Se si vuole selezionare una singola metrica per scegliere la qualità dell'attività di classificazione multiclasse, è in genere preferibile puntare alla micro-accuratezza.

Ad esempio, per un'attività di classificazione dei ticket di supporto: (mapping dei ticket in arrivo con i team di supporto)

- Micro-accuratezza: con quale frequenza un ticket in ingresso viene classificato per il team corretto?
- Macro-accuratezza: con quale frequenza un ticket in ingresso è corretto per un tipico team?

In questo esempio, l'accuratezza macro pesa i piccoli team. un piccolo team che ottiene solo 10 ticket per anno viene conteggiato come un grande team con 10.000 ticket all'anno. La micro-accuratezza in questo caso si adatta meglio all'esigenza aziendale di calcolare la quantità di tempo/denaro che è possibile risparmiare automatizzando il processo di instradamento dei ticket.

Per altre informazioni sulle metriche di classificazione multiclasse, vedere gli articoli seguenti:

- [Micro e macro-media di precisione, richiamo e Punteggio F](https://rushdishams.blogspot.com/2011/08/micro-and-macro-average-of-precision.html)
- [Multiclass Classification with Imbalanced Dataset](https://towardsdatascience.com/machine-learning-multiclass-classification-with-imbalanced-data-set-29f6a177c1a)

## <a name="evaluation-metrics-for-regression-and-recommendation"></a>Metriche di valutazione per regressione e raccomandazione

Entrambe le attività di regressione e raccomandazione stimano un numero. Nel caso della regressione, il numero può essere qualsiasi proprietà di output influenzato dalle proprietà di input. Per la raccomandazione, il numero è in genere un valore di classificazione (compreso tra 1 e 5) oppure una raccomandazione Yes/No, rappresentata rispettivamente da 1 e 0.

| Metrica   |      Descrizione      |  Cercare |
|----------|-----------------------|-----------|
| **R-Squared** |  [R-squared (R2)](https://en.wikipedia.org/wiki/Coefficient_of_determination) o *coefficiente di determinazione* rappresenta la potenza predittiva del modello come valore compreso tra -inf e 1,00. 1,00 significa corrispondenza perfetta e la corrispondenza può essere arbitrariamente insufficiente, quindi i punteggi possono essere negativi. Il punteggio 0,00 significa che il modello indovina il valore previsto per l'etichetta. R2 misura il grado di prossimità dei valori dei dati di test effettivi ai valori stimati. | **Quanto più vicino a 1,00, tanto migliore è la qualità**. Tuttavia, a volte i valori di R-squared bassi (ad esempio 0,50) possono essere perfettamente normali o sufficientemente validi per uno specifico scenario, mentre quelli alti non sono sempre validi e possono essere sospetti. |
| **Absolute-loss** |  [Absolute-loss](https://en.wikipedia.org/wiki/Mean_absolute_error) o *errore assoluto medio* misura la prossimità delle stime ai risultati effettivi. Corrisponde alla media di tutti gli errori del modello, dove un errore del modello è la distanza tra il valore di etichetta stimato e quello corretto. Questo errore di stima viene calcolato per ogni record del set di dati di test. Infine, viene calcolato il valore medio per tutti gli errori assoluti registrati.| **Quanto più vicino a 0,00, tanto migliore è la qualità**. L'errore assoluto medio usa la stessa scala dei dati misurati (non viene normalizzato in un intervallo specifico). Le metriche Absolute-loss, Squared-loss e RMS-loss possono essere usate solo per eseguire confronti tra modelli per lo stesso set di dati o per un set di dati con una distribuzione simile dei valori di etichetta. |
| **Squared-loss** |  Il [quadratino di perdita](https://en.wikipedia.org/wiki/Mean_squared_error) o l' *errore quadratico medio (MSE)* , detto anche *media quadratica deviazione (MSD)* , indica il modo in cui la linea di regressione viene stabilita in un set di valori di dati di test prendendo le distanze dai punti alla retta di regressione (queste distanze sono gli errori e) e la quadratura. La quadratura assegna più peso alle differenze maggiori. | È sempre un valore non negativo e i **valori migliori sono quelli più vicini a 0,00**. A seconda dei dati, può essere impossibile ottenere un valore molto piccolo per l'errore quadratico medio.|
| **RMS-loss** |  [RMS-perdita](https://en.wikipedia.org/wiki/Root-mean-square_deviation) o *radice errore quadratico medio (valori RMSE)* (detta anche *deviazione radice media quadrata, RMSD*), misura la differenza tra i valori stimati da un modello e i valori osservati dall'ambiente in fase di modellazione. RMS-loss è la radice quadrata di Squared-loss e ha la stessa unità come etichetta, simile a absolute-loss ma assegnando più peso alle differenze maggiori. La radice dell'errore quadratico medio viene comunemente usata in climatologia, previsioni e analisi di regressione per verificare i risultati sperimentali. | È sempre un valore non negativo e i **valori migliori sono quelli più vicini a 0,00**. RMSD è una misura dell'accuratezza, per confrontare gli errori di previsione di diversi modelli per uno specifico set di dati e non tra set di dati, in quando è dipendente dalla scala.|

Per altre informazioni sulle metriche di regressione, vedere gli articoli seguenti:

- [Analisi di regressione: come si interpreta R-Squared e si valuta la bontà della soluzione?](https://blog.minitab.com/blog/adventures-in-statistics-2/regression-analysis-how-do-i-interpret-r-squared-and-assess-the-goodness-of-fit)
- [How To Interpret R-squared in Regression Analysis](https://statisticsbyjim.com/regression/interpret-r-squared-regression)
- [R-Squared Definition](https://www.investopedia.com/terms/r/r-squared.asp)
- [Mean Squared Error Definition](https://www.statisticshowto.datasciencecentral.com/mean-squared-error/)
- [What are Mean Squared Error and Root Mean Squared Error?](https://www.vernier.com/til/1014/)

## <a name="evaluation-metrics-for-clustering"></a>Metriche di valutazione per il clustering

| Metrica   |      Descrizione      |  Cercare |
|----------|-----------------------|-----------|
|**Distanza media**|Media della distanza tra i punti dati e il centro del cluster assegnato. La distanza media è una misura della prossimità dei punti dati al cluster centroidi. Si tratta di una misura della "stretta" del cluster.|I valori più vicini a **0** sono migliori. Più vicino a zero è la distanza media, maggiore è il numero di cluster di dati. Si noti tuttavia che questa metrica diminuirà se il numero di cluster viene aumentato e, nel caso estremo, in cui ogni punto dati distinto è il proprio cluster, sarà uguale a zero.
|**Indice Bouldin Davies**|Rapporto medio tra le distanze tra i cluster e le distanze tra i cluster. Più stretta è il cluster e, più a fondo, i cluster sono, minore è il valore.|I valori più vicini a **0** sono migliori. I cluster più lontani e meno dispersi comporteranno un punteggio migliore.|
|**Informazioni comuni normalizzate**|Può essere usato quando i dati di training usati per eseguire il training del modello di clustering sono forniti anche con le etichette di verità (ovvero il clustering supervisionato). La metrica delle informazioni comuni normalizzate misura se i punti dati simili vengono assegnati allo stesso cluster e i punti dati diversi vengono assegnati a cluster diversi. Le informazioni comuni normalizzate sono un valore compreso tra 0 e 1|I valori più prossimi a **1** sono migliori|

## <a name="evaluation-metrics-for-ranking"></a>Metriche di valutazione per la classificazione

| Metrica   |      Descrizione      |  Cercare |
|----------|-----------------------|-----------|
|**Guadagni cumulativi scontati**|Il guadagno cumulativo scontato (DCG) è una misura della qualità di rango. Deriva da due presupposti. Uno: gli elementi molto rilevanti sono più utili quando vengono visualizzati in ordine di rango superiore. Due: l'utilità tiene traccia della pertinenza, maggiore è la pertinenza, più è utile un elemento. Il guadagno cumulativo scontato viene calcolato per una determinata posizione nell'ordine di rango. Viene sommata la classificazione della pertinenza divisa per il logaritmo dell'indice di rango fino alla posizione di interesse. Viene calcolato tramite $ \ sum_ {i = 0} ^ {p} \frac {rel_i} {\ log_ {e} {i + 1}} $. le gradazioni di pertinenza vengono fornite a un algoritmo di training di rango come etichette di base. Viene fornito un valore DCG per ogni posizione nella tabella di classificazione, di conseguenza il nome ha scontato i **guadagni**cumulativi. |**I valori più elevati sono migliori**|
|**Guadagni cumulativi scontati normalizzati**|La normalizzazione di DCG consente di confrontare la metrica per elenchi di rango di lunghezze diverse|**I valori più prossimi a 1 sono migliori**|

## <a name="evaluation-metrics-for-anomaly-detection"></a>Metriche di valutazione per il rilevamento delle anomalie

| Metrica   |      Descrizione      |  Cercare |
|----------|-----------------------|-----------|
|**Area sotto la curva ROC**|L'area sotto la curva operatore ricevitore misura il modo in cui il modello separa i punti dati anomali e usuali.|**I valori più prossimi a 1 sono migliori**. Solo i valori maggiori di 0,5 dimostrano l'efficacia del modello. I valori 0,5 o seguenti indicano che il modello non è migliore dell'allocazione casuale degli input alle categorie anomale e consuete|
|**Frequenza di rilevamento con conteggio falso positivo**|Il tasso di rilevamento a un conteggio falso positivo è il rapporto tra il numero di anomalie identificate correttamente e il numero totale di anomalie in un set di test, indicizzate da ogni falso positivo. Ovvero, è presente un valore per la frequenza di rilevamento con numero di falsi positivi per ogni elemento falso positivo.|**I valori più prossimi a 1 sono migliori**. Se non sono presenti falsi positivi, questo valore è 1|
