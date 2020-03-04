---
title: Automatizzare il training del modello con l'interfaccia della riga di comando ML.NET
description: Informazioni su come usare lo strumento dell'interfaccia della riga di comando ML.NET per eseguire automaticamente il training del modello migliore dalla riga di comando.
ms.date: 12/17/2019
ms.custom: how-to
ms.openlocfilehash: 9c493b1df0dd326ad2f0a5d1cac0fc11d7cf37e2
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/03/2020
ms.locfileid: "78240623"
---
# <a name="automate-model-training-with-the-mlnet-cli"></a>Automatizzare il training del modello con l'interfaccia della riga di comando ML.NET

L'interfaccia della riga di comando di ML.NET automatizza la generazione di modelli per gli sviluppatori .NET.

Per usare l'API ML.NET in modo indipendente, ovvero senza l'interfaccia della riga di comando AutoML di ML.NET, è necessario scegliere un formatore (implementazione di un algoritmo di apprendimento automatico per una determinata attività) e il set di trasformazioni dei dati (progettazione di funzionalità) da applicare ai dati. La pipeline ottimale varia in base al set di dati e selezionare l'algoritmo ottimale da tutte le opzioni disponibili aumenta la complessità. In più, ogni algoritmo ha un set di iperparametri da ottimizzare. Di conseguenza, il processo di ottimizzazione del modello di apprendimento automatico può richiedere settimane, a volte mesi, poiché si tenta di trovare le combinazioni migliori di progettazione di funzionalità, algoritmi di apprendimento e iperparametri.

L'interfaccia della riga di comando di ML.NET semplifica questo processo usando automazione Machine Learning (AutoML). 

> [!NOTE]
> Questo argomento fa riferimento all'**interfaccia della riga di comando** ML.NET e alla funzionalità di Machine Learning automatico (**AutoML**), attualmente in anteprima, e il materiale può essere soggetto a modifiche.

## <a name="what-is-the-mlnet-command-line-interface-cli"></a>Che cos'è l'interfaccia della riga di comando di ML.NET?

L'interfaccia della riga di comando di ML.NET è uno [strumento di .NET Core](../core/tools/global-tools.md). Una volta eseguita l'installazione, viene assegnata un'attività di machine learning e un set di dati di training e viene generato un modello C# ml.NET, nonché il codice da eseguire per usare il modello nell'applicazione.

Come illustrato nella figura seguente, è semplice generare un modello ML.NET di qualità elevata (file con estensione zip del modello serializzato) più il codice C# di esempio per eseguire/assegnare un punteggio al modello. Viene anche generato automaticamente il codice C# per creare/eseguire il training del modello in modo da ricercare l'algoritmo e le impostazioni usate per il "modello ottimale" generato.

![image](media/automate-training-with-cli/cli-high-level-process.png "Motore AutoML che funziona nell'interfaccia della riga di comando di ML.NET")

Poiché è possibile generare questi asset dal proprio set di dati senza scrivere alcun codice, è possibile migliorare la produttività anche se si conosce già ML.NET.

Attualmente, le attività di apprendimento automatico supportate dall'interfaccia della riga di comando ML.NET sono:

- `binary-classification`
- `multiclass-classification`
- `regression`
- In futuro: altre attività di apprendimento automatico, ad esempio `recommendation`, `ranking`, `anomaly-detection`, `clustering`

Esempio di utilizzo:

```console
mlnet auto-train --task binary-classification --dataset "customer-feedback.tsv" --label-column-name Sentiment
```

![image](media/automate-training-with-cli/cli-model-generation.gif)

È possibile eseguire la funzionalità come si esegue *Windows PowerShell*, *bash di macOS/Linux o una *finestra di comando di Windows*. Tuttavia, il completamento automatico in formato tabella (suggerimento dei parametri) non funzionerà nella *finestra di comando di Windows*.

## <a name="output-assets-generated"></a>Asset di output generati

Il comando `auto-train` dell'interfaccia della riga di comando genera gli asset seguenti nella cartella di output:

- Un file ZIP di modello serializzato ("modello ottimale") pronto per l'uso nell'esecuzione di stime.
- Soluzione C# con:
  - Il codice C# per eseguire e assegnare punteggi al modello generato (per eseguire stime nelle app per utenti finali con il modello).
  - Il codice C# con il codice di training usato per generare il modello (a scopo di apprendimento o nuovo training del modello).
- File di log con informazioni su tutte le iterazioni e gli sweep eseguiti su più algoritmi valutati, inclusa la configurazione/pipeline dettagliata.

I primi due asset possono essere usati direttamente nelle app degli utenti finali (app Web ASP.NET Core, servizi, app desktop, ecc.) per effettuare previsioni con il modello di Machine Learning generato.

Il terzo asset, ovvero il codice di training, indica quale codice API ML.NET è stato usato dall'interfaccia della riga di comando per eseguire il training del modello generato, in modo che sia possibile ripetere il training del modello ed esaminare il formatore/algoritmo e gli iperparametri specifici selezionati in background dall'interfaccia della riga di comando e dalla funzionalità AutoML.

## <a name="understanding-the-quality-of-the-model"></a>Informazioni sulla qualità del modello

Quando si genera un modello "migliore" con lo strumento dell'interfaccia della riga di comando, vengono visualizzate le metriche qualitative (ad esempio l'accuratezza e il quadrato R) in base alle esigenze dell'attività ML di destinazione.

Queste metriche vengono riepilogate raggruppate per attività di Machine Learning, in modo che sia possibile comprendere la qualità del "modello migliore" generato automaticamente.

### <a name="metrics-for-binary-classification-models"></a>Metriche per i modelli di classificazione binaria

Di seguito è visualizzato l'elenco delle metriche delle attività di apprendimento automatico per la classificazione binaria dei primi cinque modelli individuati dall'interfaccia della riga di comando:

![image](media/automate-training-with-cli/cli-binary-classification-metrics.png)

L'accuratezza è una metrica diffusa per i problemi di classificazione, tuttavia l'accuratezza non è sempre la metrica migliore per selezionare il modello migliore da come illustrato nei riferimenti seguenti. Vi sono casi in cui è necessario valutare la qualità del modello con metriche supplementari.

Per esplorare e comprendere le metriche restituite dall'interfaccia della riga di comando, vedere [metriche di valutazione per la classificazione binaria](resources/metrics.md#evaluation-metrics-for-binary-classification).

### <a name="metrics-for-multi-class-classification-models"></a>Metriche per i modelli di classificazione multiclasse

Di seguito è visualizzato l'elenco delle metriche delle attività di apprendimento automatico per la classificazione multiclasse dei primi cinque modelli individuati dall'interfaccia della riga di comando:

![image](media/automate-training-with-cli/cli-multiclass-classification-metrics.png)

Per esplorare e comprendere le metriche restituite dall'interfaccia della riga di comando, vedere [metriche di valutazione per la classificazione multiclasse](resources/metrics.md#evaluation-metrics-for-multi-class-classification).

### <a name="metrics-for-regression-and-recommendation-models"></a>Metriche per i modelli di regressione e di raccomandazione

Un modello di regressione risulta adatto ai dati se le differenze tra i valori osservati e valori stimati del modello sono ridotti e non distorti. La regressione può essere valutata con alcune metriche.

Verrà visualizzato un elenco simile di metriche per i primi cinque modelli di qualità trovati dall'interfaccia della riga di comando. In questo caso particolare, correlato a un'attività di regressione dell'apprendimento automatico:

![image](media/automate-training-with-cli/cli-regression-metrics.png)

Per esplorare e comprendere le metriche restituite dall'interfaccia della riga di comando, vedere [metriche di valutazione per la regressione](resources/metrics.md#evaluation-metrics-for-regression-and-recommendation).

## <a name="see-also"></a>Vedere anche

- [Come installare lo strumento dell'interfaccia della riga comando ML.NET](how-to-guides/install-ml-net-cli.md)
- [Esercitazione: analizzare i sentimenti usando l'interfaccia della riga di comando di ML.NET](tutorials/sentiment-analysis-cli.md)
- [Informazioni di riferimento sui comandi dell'interfaccia della riga di comando ML.NET](reference/ml-net-cli-reference.md)
- [Telemetria nell'interfaccia della riga di comando di ML.NET](resources/ml-net-cli-telemetry.md)
