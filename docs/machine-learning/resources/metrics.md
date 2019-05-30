---
title: Metriche di ML.NET
description: Informazioni sulle metriche usate per valutare le prestazioni di un modello ML.NET
ms.date: 04/29/2019
author: ''
ms.openlocfilehash: 802f0a8fd32c492c8d9f89933b183802cb178cb3
ms.sourcegitcommit: 7e129d879ddb42a8b4334eee35727afe3d437952
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/23/2019
ms.locfileid: "66053047"
---
# <a name="model-evaluation-metrics-in-mlnet"></a>Metriche di valutazione dei modelli in ML.NET

## <a name="metrics-for-binary-classification"></a>Metriche per la classificazione binaria

| Metrica   |      Description      |  Obiettivo |
|-----------|-----------------------|-----------|
| **Accuracy** |  [Accuracy](https://en.wikipedia.org/wiki/Accuracy_and_precision#In_binary_classification) o accuratezza corrisponde alla percentuale di stime corrette con un set di dati di test. Equivale al rapporto tra il numero di stime corrette e il numero totale di campioni di input. È una metrica valida solo nel caso di un numero simile di campioni appartenente a ogni classe.| **Quanto più vicino a 1,00, tanto meglio**. Ma se il risultato è esattamente 1,00, significa che si è verificato un problema, in genere di tipo dispersione di dati (etichetta/destinazione), sovradattamento oppure uso di dati di training per il test. Se i dati di test sono squilibrati (per cui la maggior parte delle istanze appartengono a una delle classi), il set di dati è molto piccolo oppure i punteggi si avvicinano a 0,00 o 1,00, l'accuratezza non rileva in realtà l'efficacia di un classificatore ed è necessario controllare altre metriche. |
| **AUC** |    [aucROC](https://en.wikipedia.org/wiki/Receiver_operating_characteristic) o *area sotto la curva*: corrisponde alla misurazione dell'area sotto la curva creata verificando la percentuale di veri positivi rispetto a quella di falsi positivi.  |   **Quanto più vicino a 1,00, tanto meglio**. Il valore dovrebbe essere maggiore di 0,50 perché un modello sia accettabile; un modello con AUC minore o uguale 0,50 è inutile. |
| **AUCPR** | [aucPR](https://www.coursera.org/lecture/ml-classification/precision-recall-curve-rENu8) o *area sotto la curva di precisione-recupero*: si tratta di una misura utile del successo di una stima quando le classi sono molto sbilanciate (set di dati ampiamente distorti). |  **Quanto più vicino a 1,00, tanto meglio**. I punteggi elevati vicini a 1,00 mostrano che il classificatore restituisce risultati accurati (alta precisione), oltre a restituire una maggioranza di risultati tutti positivi (alto recupero). |
| **F1-score** | [F1 score](https://en.wikipedia.org/wiki/F1_score) anche detto *F-score bilanciato o F-measure*. Si tratta della media armonica di precisione e recupero. La metrica F1 Score è utile se si vuole trovare un equilibrio tra precisione e recupero.| **Quanto più vicino a 1,00, tanto meglio**.  F1-score raggiunge il valore ottimale con un punteggio 1,00 e il valore peggiore con 0,00. Indica il grado di precisione del classificatore. |

Per altre informazioni sulle metriche di classificazione binaria, vedere gli articoli seguenti:

- [Accuracy, Precision, Recall or F1?](https://towardsdatascience.com/accuracy-precision-recall-or-f1-331fb37c5cb9)
- [Classe BinaryClassificationMetrics](xref:Microsoft.ML.Data.BinaryClassificationMetrics)
- [The Relationship Between Precision-Recall and ROC Curves](http://pages.cs.wisc.edu/~jdavis/davisgoadrichcamera2.pdf)

## <a name="metrics-for-multi-class-classification"></a>Metriche per la classificazione multiclasse

| Metrica   |      Description      |  Obiettivo |
|-----------|-----------------------|-----------|
| **Micro-Accuracy** |  L'[accuratezza micro-media](xref:Microsoft.ML.Data.MulticlassClassificationMetrics.MicroAccuracy) aggrega i contributi di tutte le classi per calcolare la metrica media. Corrisponde alla percentuale di istanze stimate correttamente. La micro-media non tiene conto dell'appartenenza a una classe. Essenzialmente, ogni coppia campione-classe contribuisce nello stesso modo alla metrica di accuratezza. | **Quanto più vicino a 1,00, tanto meglio**. In un'attività di classificazione multiclasse la micro-accuratezza è preferibile rispetto alla macro-accuratezza se si sospetta uno squilibrio di classi, ossia la presenza di molti più esempi di una classe rispetto ad altre.|
| **Macro-Accuracy** | L'[accuratezza macro-media](xref:Microsoft.ML.Data.MulticlassClassificationMetrics.MacroAccuracy) corrisponde all'accuratezza media a livello di classe. Viene confrontata l'accuratezza per ogni classe e l'accuratezza macro-media è la media di queste accuratezze. Essenzialmente, ogni classe contribuisce nello stesso modo alla metrica di accuratezza. Alle classi di minoranza viene assegnato un peso uguale a quello delle classi più grandi. La metrica della macro-media assegna lo stesso peso a ogni classe, indipendentemente dal numero di istanze di tale classe contenute nel set di dati. |  **Quanto più vicino a 1,00, tanto meglio**.  Calcola la metrica in modo indipendente per ogni classe e quindi ne considera la media, di conseguenza tratta tutte le classi allo stesso modo |
| **Log-loss**| La [perdita logaritmica](http://wiki.fast.ai/index.php/Log_Loss) misura le prestazioni di un modello di classificazione in cui l'input della stima è un valore di probabilità compreso tra 0,00 e 1,00. Questa metrica aumenta quando la probabilità stimata devia dall'etichetta effettiva. | **Quanto più vicino a 0,00, tanto meglio**. In un modello perfetto, log-loss sarebbe uguale a 0,00. L'obiettivo dei modelli di Machine Learning è ridurre al minimo questo valore.|
| **Log-Loss Reduction** | La [riduzione della perdita logaritmica](xref:Microsoft.ML.Data.MulticlassClassificationMetrics.LogLossReduction) può essere interpretata come un vantaggio del classificatore rispetto alla stima casuale.| **Il valore è compreso nell'intervallo da -inf a 1,00, dove 1,00 corrisponde a stime perfette e 0,00 indica stime medie**. Ad esempio, se il valore equivale a 0,20, può essere interpretato come "la probabilità di una stima corretta è il 20% maggiore rispetto alla stima casuale"|

La micro-accuratezza è generalmente più indicata per le esigenze aziendali di stime di ML. Se si vuole selezionare una singola metrica per scegliere la qualità dell'attività di classificazione multiclasse, è in genere preferibile puntare alla micro-accuratezza.

Ad esempio, per un'attività di classificazione dei ticket di supporto: (mapping dei ticket in arrivo con i team di supporto)

- Micro-accuratezza: con quale frequenza un ticket in ingresso viene classificato per il team corretto?
- Macro-accuratezza: con quale frequenza un ticket in ingresso è corretto per un tipico team?

In questo esempio la macro-accuratezza assegna un peso eccessivo ai piccoli team. Un piccolo team che riceve solo 10 ticket all'anno viene conteggiato allo stesso modo di un grande team con 10.000 ticket all'anno. La micro-accuratezza in questo caso si adatta meglio all'esigenza aziendale di calcolare la quantità di tempo/denaro che è possibile risparmiare automatizzando il processo di instradamento dei ticket.

Per altre informazioni sulle metriche di classificazione multiclasse, vedere gli articoli seguenti:

- [Micro- and Macro-average of Precision, Recall and F-Score](http://rushdishams.blogspot.com/2011/08/micro-and-macro-average-of-precision.html)
- [Multiclass Classification with Imbalanced Dataset](https://towardsdatascience.com/machine-learning-multiclass-classification-with-imbalanced-data-set-29f6a177c1a)

## <a name="metrics-for-regression"></a>Metriche per la regressione

| Metrica   |      Description      |  Obiettivo |
|-----------|-----------------------|-----------|
| **R-Squared** |  [R-squared (R2)](https://en.wikipedia.org/wiki/Coefficient_of_determination) o *coefficiente di determinazione* rappresenta la potenza predittiva del modello come valore compreso tra -inf e 1,00. 1,00 significa corrispondenza perfetta e la corrispondenza può essere arbitrariamente insufficiente, quindi i punteggi possono essere negativi. Il punteggio 0,00 significa che il modello indovina il valore previsto per l'etichetta. R2 misura il grado di prossimità dei valori dei dati di test effettivi ai valori stimati. | **Quanto più vicino a 1,00, tanto migliore è la qualità**. Tuttavia, a volte i valori di R-squared bassi (ad esempio 0,50) possono essere perfettamente normali o sufficientemente validi per uno specifico scenario, mentre quelli alti non sono sempre validi e possono essere sospetti. |
| **Absolute-loss** |  [Absolute-loss](https://en.wikipedia.org/wiki/Mean_absolute_error) o *errore assoluto medio* misura la prossimità delle stime ai risultati effettivi. Corrisponde alla media di tutti gli errori del modello, dove un errore del modello è la distanza tra il valore di etichetta stimato e quello corretto. Questo errore di stima viene calcolato per ogni record del set di dati di test. Infine, viene calcolato il valore medio per tutti gli errori assoluti registrati.| **Quanto più vicino a 0,00, tanto migliore è la qualità**. Si noti che l'errore assoluto medio usa la stessa scala dei dati misurati, ossia non è normalizzato in base a un intervallo specifico. Le metriche Absolute-loss, Squared-loss e RMS-loss possono essere usate solo per eseguire confronti tra modelli per lo stesso set di dati o per un set di dati con una distribuzione simile dei valori di etichetta. |
| **Squared-loss** |  [Squared-loss](https://en.wikipedia.org/wiki/Mean_squared_error) o *errore quadratico medio*, detto anche *deviazione quadratica media*, indica la prossimità di una retta di regressione a un set di valori di dati di test. A questo scopo esegue la quadratura delle distanze tra i punti e la retta di regressione (queste distanze sono gli errori, E). La quadratura assegna più peso alle differenze maggiori. | È sempre un valore non negativo e i **valori migliori sono quelli più vicini a 0,00**. A seconda dei dati, può essere impossibile ottenere un valore molto piccolo per l'errore quadratico medio.|
| **RMS-loss** |  [RMS-loss](https://en.wikipedia.org/wiki/Root-mean-square_deviation) o *radice dell'errore quadratico medio*, anche detto *radice della deviazione quadratica media*, misura la differenza tra i valori stimati da un modello e i valori effettivamente osservati nell'ambiente del modello. RMS-loss è la radice quadrata di Squared-loss e ha la stessa unità come etichetta, simile a absolute-loss ma assegnando più peso alle differenze maggiori. La radice dell'errore quadratico medio viene comunemente usata in climatologia, previsioni e analisi di regressione per verificare i risultati sperimentali. | È sempre un valore non negativo e i **valori migliori sono quelli più vicini a 0,00**. RMSD è una misura dell'accuratezza, per confrontare gli errori di previsione di diversi modelli per uno specifico set di dati e non tra set di dati, in quando è dipendente dalla scala.|

Per altre informazioni sulle metriche di regressione, vedere gli articoli seguenti:

- [Regression Analysis: How Do I Interpret R-squared and Assess the Goodness-of-Fit?](https://blog.minitab.com/blog/adventures-in-statistics-2/regression-analysis-how-do-i-interpret-r-squared-and-assess-the-goodness-of-fit)
- [How To Interpret R-squared in Regression Analysis](https://statisticsbyjim.com/regression/interpret-r-squared-regression)
- [R-Squared Definition](https://www.investopedia.com/terms/r/r-squared.asp)
- [Mean Squared Error Definition](https://www.statisticshowto.datasciencecentral.com/mean-squared-error/)
- [What are Mean Squared Error and Root Mean Squared Error?](https://www.vernier.com/til/1014/)
