---
title: Automatizzare il training del modello con l'interfaccia della riga di comando ML.NET
description: Informazioni su come usare lo strumento dell'interfaccia della riga di comando ML.NET per eseguire automaticamente il training del modello migliore dalla riga di comando.
ms.date: 12/17/2019
ms.custom: how-to, mlnet-tooling
ms.openlocfilehash: 3344ed15266503d4d5c7cd9db0a0596f58a904fa
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "79185890"
---
# <a name="automate-model-training-with-the-mlnet-cli"></a>Automatizzare il training del modello con l'interfaccia della riga di comando ML.NET

L'interfaccia della riga di comando ML.NET automatizza la generazione di modelli per gli sviluppatori .NET.

Per usare l'API ML.NET in modo indipendente, ovvero senza l'interfaccia della riga di comando AutoML di ML.NET, è necessario scegliere un formatore (implementazione di un algoritmo di apprendimento automatico per una determinata attività) e il set di trasformazioni dei dati (progettazione di funzionalità) da applicare ai dati. La pipeline ottimale varia in base al set di dati e selezionare l'algoritmo ottimale da tutte le opzioni disponibili aumenta la complessità. In più, ogni algoritmo ha un set di iperparametri da ottimizzare. Di conseguenza, il processo di ottimizzazione del modello di apprendimento automatico può richiedere settimane, a volte mesi, poiché si tenta di trovare le combinazioni migliori di progettazione di funzionalità, algoritmi di apprendimento e iperparametri.

L'interfaccia della riga di comando ML.NET semplifica questo processo usando l'apprendimento automatico automatico (AutoML).

> [!NOTE]
> Questo argomento fa riferimento all'**interfaccia della riga di comando** ML.NET e alla funzionalità di Machine Learning automatico (**AutoML**), attualmente in anteprima, e il materiale può essere soggetto a modifiche.

## <a name="what-is-the-mlnet-command-line-interface-cli"></a>Che cos'è l'interfaccia della riga di comando (CLI) ML.NET?

L'interfaccia della riga di comando ML.NET è uno [strumento .NET Core](../core/tools/global-tools.md). Una volta installato, si assegna un'attività di apprendimento automatico e un set di dati di training e genera un modello di ML.NET, nonché il codice C , da eseguire per usare il modello nell'applicazione.

Come illustrato nella figura seguente, è semplice generare un modello di ML.NET di alta qualità (file .zip del modello serializzato) più il codice di esempio in c'è per eseguire/partitura tale modello. Viene anche generato automaticamente il codice C# per creare/eseguire il training del modello in modo da ricercare l'algoritmo e le impostazioni usate per il "modello ottimale" generato.

![Immagine](media/automate-training-with-cli/cli-high-level-process.png "Il motore AutoML funziona all'interno della ML.NET CLI")

Poiché questi asset si possono generare dal proprio set di dati senza scrivere alcun codice, è possibile migliorare la produttività anche se si conosce già ML.NET.

Attualmente, le attività di Machine Learning supportate dall'interfaccia della riga di comando di ML.NET sono:

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

I primi due asset possono essere usati direttamente nelle app degli utenti finali (app Web ASP.NET Core, servizi, app desktop e così via) per effettuare previsioni con il modello di Machine Learning generato.

Il terzo asset, ovvero il codice di training, indica quale codice API ML.NET è stato usato dall'interfaccia della riga di comando per eseguire il training del modello generato, in modo che sia possibile ripetere il training del modello ed esaminare il formatore/algoritmo e gli iperparametri specifici selezionati in background dall'interfaccia della riga di comando e dalla funzionalità AutoML.

## <a name="understanding-the-quality-of-the-model"></a>Informazioni sulla qualità del modello

Quando generi un "miglior modello" con lo strumento CLI, visualizzi le metriche di qualità (ad esempio precisione e R al quadrato) appropriate per l'attività di ML di destinazione.

Qui queste metriche sono riepilogate raggruppate per attività di ML in modo da poter comprendere la qualità del tuo "miglior modello" generato automaticamente.

### <a name="metrics-for-binary-classification-models"></a>Metriche per i modelli di classificazione binaria

Di seguito è visualizzato l'elenco delle metriche delle attività di apprendimento automatico per la classificazione binaria dei primi cinque modelli individuati dall'interfaccia della riga di comando:

![image](media/automate-training-with-cli/cli-binary-classification-metrics.png)

L'accuratezza è una metrica comune per i problemi di classificazione, tuttavia l'accuratezza non è sempre la metrica migliore tra cui selezionare il modello migliore, come spiegato nei riferimenti seguenti. Vi sono casi in cui è necessario valutare la qualità del modello con metriche supplementari.

Per esplorare e comprendere le metriche output dell'interfaccia della riga di comando, vedere Metriche di valutazione per la [classificazione binaria](resources/metrics.md#evaluation-metrics-for-binary-classification).

### <a name="metrics-for-multi-class-classification-models"></a>Metriche per i modelli di classificazione multiclasse

Di seguito è visualizzato l'elenco delle metriche delle attività di apprendimento automatico per la classificazione multiclasse dei primi cinque modelli individuati dall'interfaccia della riga di comando:

![image](media/automate-training-with-cli/cli-multiclass-classification-metrics.png)

Per esplorare e comprendere le metriche output dell'interfaccia della riga di comando, vedere Metriche di valutazione per la [classificazione multiclasse.](resources/metrics.md#evaluation-metrics-for-multi-class-classification)

### <a name="metrics-for-regression-and-recommendation-models"></a>Metriche per i modelli di regressione e raccomandazioneMetrics for Regression and Recommendation models

Un modello di regressione risulta adatto ai dati se le differenze tra i valori osservati e valori stimati del modello sono ridotti e non distorti. La regressione può essere valutata con alcune metriche.

Vedrai un elenco di metriche simile per i migliori cinque modelli di qualità trovati dalla CLI. In questo caso particolare, correlato a un'attività di regressione dell'apprendimento automatico:

![image](media/automate-training-with-cli/cli-regression-metrics.png)

Per esplorare e comprendere le metriche output dall'interfaccia della riga di comando, vedere Metriche di [valutazione per la regressione](resources/metrics.md#evaluation-metrics-for-regression-and-recommendation).

## <a name="see-also"></a>Vedere anche

- [Come installare lo strumento dell'interfaccia della riga comando ML.NET](how-to-guides/install-ml-net-cli.md)
- [Esercitazione: Analizzare il sentiment usando l'interfaccia della riga di comando di ML.NET](tutorials/sentiment-analysis-cli.md)
- [Informazioni di riferimento sui comandi dell'interfaccia della riga di comando ML.NET](reference/ml-net-cli-reference.md)
- [Telemetria nell'interfaccia della riga di comando ML.NET](resources/ml-net-cli-telemetry.md)
