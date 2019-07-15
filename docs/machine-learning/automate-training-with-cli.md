---
title: Automatizzare il training del modello con l'interfaccia della riga di comando ML.NET
description: Informazioni su come usare lo strumento dell'interfaccia della riga di comando ML.NET per eseguire automaticamente il training del modello migliore dalla riga di comando.
author: CESARDELATORRE
ms.date: 04/17/2019
ms.custom: how-to
ms.openlocfilehash: e5f75dc70ea5a76951d8698ea9c0d07cb2d4ddec
ms.sourcegitcommit: d6e27023aeaffc4b5a3cb4b88685018d6284ada4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2019
ms.locfileid: "67663933"
---
# <a name="automate-model-training-with-the-mlnet-cli"></a>Automatizzare il training del modello con l'interfaccia della riga di comando ML.NET

L'interfaccia della riga di comando ML.NET "democratizza" ML.NET per gli sviluppatori .NET durante l'apprendimento di ML.NET.

Per usare l'API ML.NET in modo indipendente, ovvero senza l'interfaccia della riga di comando AutoML di ML.NET, è necessario scegliere un formatore (implementazione di un algoritmo di apprendimento automatico per una determinata attività) e il set di trasformazioni dei dati (progettazione di funzionalità) da applicare ai dati. La pipeline ottimale varia in base al set di dati e selezionare l'algoritmo ottimale da tutte le opzioni disponibili aumenta la complessità. In più, ogni algoritmo ha un set di iperparametri da ottimizzare. Di conseguenza, il processo di ottimizzazione del modello di apprendimento automatico può richiedere settimane, a volte mesi, poiché si tenta di trovare le combinazioni migliori di progettazione di funzionalità, algoritmi di apprendimento e iperparametri.

Il processo si può automatizzare con l'interfaccia della riga di comando ML.NET, che implementa il motore intelligente AutoML di ML.NET.

> [!NOTE]
> Questo argomento fa riferimento all'**interfaccia della riga di comando** ML.NET e alla funzionalità di Machine Learning automatico (**AutoML**), attualmente in anteprima, e il materiale può essere soggetto a modifiche.

## <a name="what-is-the-mlnet-command-line-interface-cli"></a>Informazioni sull'interfaccia della riga di comando (CLI) ML.NET

È possibile eseguire l'interfaccia della riga di comando ML.NET in qualsiasi prompt dei comandi (Windows, Mac o Linux) per generare modelli e codice sorgente ML.NET di buona qualità in base ai propri set di dati di training.

Come illustra l'immagine che segue, è facile generare un modello ML.NET di buona qualità (file ZIP di modello serializzato) e il codice C# di esempio per eseguire/assegnare un punteggio al modello. Viene anche generato automaticamente il codice C# per creare/eseguire il training del modello in modo da ricercare l'algoritmo e le impostazioni usate per il "modello ottimale" generato.

![immagine](media/automate-training-with-cli/cli-high-level-process.png "Motore AutoML usato all'interno dell'interfaccia della riga di comando ML.NET")

Poiché questi asset si possono generare dal proprio set di dati senza scrivere alcun codice, è possibile migliorare la produttività anche se si conosce già ML.NET.

Attualmente, le attività di apprendimento automatico supportate dall'interfaccia della riga di comando ML.NET sono:

- `binary-classification`
- `multiclass-classification`
- `regression`
- In futuro: altre attività di apprendimento automatico, ad esempio `recommendation`, `ranking`, `anomaly-detection`, `clustering`

Esempio di utilizzo:

```console
> mlnet auto-train --task binary-classification --dataset "customer-feedback.tsv" --label-column-name Sentiment
```

![immagine](media/automate-training-with-cli/cli-model-generation.gif)

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

Quando si genera un "modello ottimale" con lo strumento dell'interfaccia della riga di comando vengono visualizzate metriche relative alla qualità, ad esempio accuratezza e R quadrato, in base all'attività di apprendimento automatico che interessa.

Nel riepilogo che segue le metriche sono raggruppate per attività di apprendimento automatico per consentire all'utente di comprendere la qualità del "modello ottimale" generato automaticamente.

### <a name="metrics-for-binary-classification-models"></a>Metriche per i modelli di classificazione binaria

Di seguito è visualizzato l'elenco delle metriche delle attività di apprendimento automatico per la classificazione binaria dei primi cinque modelli individuati dall'interfaccia della riga di comando:

![immagine](media/automate-training-with-cli/cli-binary-classification-metrics.png)

L'accuratezza è una metrica molto diffusa per i problemi di classificazione, tuttavia non è sempre la metrica più adatta per selezionare il modello ottimale, come spiegato di seguito. Vi sono casi in cui è necessario valutare la qualità del modello con metriche supplementari.

Per esaminare e comprendere le metriche generate dall'interfaccia della riga di comando, vedere [Metriche per la classificazione binaria](resources/metrics.md#metrics-for-binary-classification).

### <a name="metrics-for-multi-class-classification-models"></a>Metriche per i modelli di classificazione multiclasse

Di seguito è visualizzato l'elenco delle metriche delle attività di apprendimento automatico per la classificazione multiclasse dei primi cinque modelli individuati dall'interfaccia della riga di comando:

![immagine](media/automate-training-with-cli/cli-multiclass-classification-metrics.png)

Per esaminare e comprendere le metriche generate dall'interfaccia della riga di comando, vedere [Metriche per la classificazione multiclasse](resources/metrics.md#metrics-for-multi-class-classification).

### <a name="metrics-for-regression-models"></a>Metriche per i modelli di regressione

Un modello di regressione risulta adatto ai dati se le differenze tra i valori osservati e valori stimati del modello sono ridotti e non distorti. La regressione può essere valutata con alcune metriche.

Verrà visualizzato un elenco simile di metriche per i primi cinque modelli di qualità ottimale individuati dall'interfaccia della riga di comando. In questo caso particolare, correlato a un'attività di regressione dell'apprendimento automatico:

![immagine](media/automate-training-with-cli/cli-regression-metrics.png)

Per esaminare e comprendere le metriche generate dall'interfaccia della riga di comando, vedere [Metriche per la regressione](resources/metrics.md#metrics-for-regression).

## <a name="see-also"></a>Vedere anche

- [Come installare lo strumento dell'interfaccia della riga comando ML.NET](how-to-guides/install-ml-net-cli.md)
- [Esercitazione: Generare automaticamente un classificatore binario con l'interfaccia della riga di comando ML.NET](tutorials/mlnet-cli.md)
- [Informazioni di riferimento sui comandi dell'interfaccia della riga di comando ML.NET](reference/ml-net-cli-reference.md)
- [Telemetria nell'interfaccia della riga di comando ML.NET](resources/ml-net-cli-telemetry.md)
