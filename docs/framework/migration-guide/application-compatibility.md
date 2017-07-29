---
title: "Compatibilità delle applicazioni in .NET Framework"
ms.custom: 
ms.date: 05/19/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
- app-compat
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- application compatibility
- .NET Framework application compatibility
- .NET Framework changes
caps.latest.revision: 19
ms.assetid: c4ba3ff2-fe59-4c5d-9e0b-86bba3cd865c
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: b3c7df2984c2c9e8af308ca8070f7207d11ba49e
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---

# <a name="application-compatibility-in-the-net-framework"></a>Compatibilità delle applicazioni in .NET Framework

## <a name="introduction"></a>Introduzione

La compatibilità è un obiettivo molto importante di ogni versione di .NET, perché garantisce che ogni versione venga aggiunta alle precedenti, che pertanto continuano a funzionare. D'altra parte, quando codice o applicazioni esistenti vengono eseguiti in una versione successiva, le modifiche apportate alle funzionalità precedenti per migliorare le prestazioni, risolvere i problemi di sicurezza o correggere i bug possono causare problemi di compatibilità. In .NET Framework esiste la distinzione tra modifiche di ridestinazione e modifiche di runtime. Le modifiche di ridestinazione interessano le applicazioni destinate a una versione specifica di .NET Framework ma che vengono eseguite in una versione successiva. Le modifiche di runtime interessano tutte le applicazioni in esecuzione in una versione specifica.

Ogni app è destinata a una versione specifica di .NET Framework, che può essere indicata tramite le azioni seguenti:

- Definizione di un framework di destinazione in Visual Studio.
- Indicazione del framework di destinazione in un file di progetto.
- Applicazione di un <xref:System.Runtime.Versioning.TargetFrameworkAttribute> al codice sorgente.

Durante l'esecuzione in una versione più recente di quella di destinazione, .NET Framework simula la versione di destinazione precedente adottando un comportamento anomalo. In altre parole, l'app viene eseguita nella versione più recente di .NET Framework, ma si comporta come se fosse in esecuzione nella versione precedente. Questo modello di comportamento consente di attenuare molti problemi di compatibilità tra versioni diverse di .NET Framework.

## <a name="runtime-changes"></a>Modifiche in fase di esecuzione

I problemi di runtime sono quelli che si verificano quando in un computer viene installato un nuovo runtime e, pur eseguendo gli stessi file binari, il comportamento riscontrato è diverso. Se un file binario è stato compilato per .NET Framework 4.0, in .NET Framework versione 4.5 o successiva viene eseguito in modalità compatibilità .NET Framework 4.0. Molte delle modifiche che interessano la versione 4.5 non interessano i file binari compilati per la versione 4.0. Questo è specifico di AppDomain e dipende dalle impostazioni dell'assembly di voce.

## <a name="retargeting-changes"></a>Modifiche di reindirizzamento

I problemi di ridestinazione sono quelli che si verificano quando per un assembly destinato alla versione 4.0 viene assegnata come destinazione la versione 4.5. A questo punto l'assembly è in grado di usare le nuove funzionalità, ma può presentare problemi di compatibilità con le funzionalità precedenti. Anche in questo caso, ciò dipende dall'assembly di voce, quindi dall'app console che usa l'assembly o dal sito Web che vi fa riferimento.

## <a name="net-compatibility-diagnostics"></a>.NET Compatibility Diagnostics

.NET Compatibility Diagnostics include analizzatori basati su Roslyn che consentono di identificare problemi di compatibilità delle applicazioni tra versioni diverse di .NET Framework. Questo elenco contiene tutti gli analizzatori disponibili, anche se solo un subset sarà applicabile a ogni specifica migrazione. Saranno gli analizzatori a determinare i problemi applicabili alla migrazione pianificata e a segnalare solo quelli.

Per ogni problema sono incluse le informazioni seguenti:

-   Descrizione delle modifiche rispetto a una versione precedente.

-   Le conseguenze della modifica sui clienti e l'eventuale disponibilità di soluzioni per mantenere la compatibilità tra versioni diverse.

-   Valutazione dell'importanza della modifica. I problemi di compatibilità delle applicazioni sono classificati come segue:

    |   |   |
    |---|---|
    |Principale|Una modifica significativa che influisce su un numero elevato di app o che richiede variazioni sostanziali del codice.|
    |Secondario|Una modifica che influisce su un numero ridotto di app o che richiede variazioni marginali del codice.|
    |Caso limite|Una modifica che influisce sulle app in scenari molto specifici e non comuni.|
    |Trasparente|Una modifica senza effetti evidenti sullo sviluppatore o sull'utente dell'applicazione.|

-   La versione indica quando la modifica è comparsa per la prima volta nel framework. Alcune modifiche vengono introdotte in una versione specifica e ripristinate in una versione successiva. Anche il ripristino viene indicato.

-   Tipo di modifica:

    |   |   |
    |---|---|
    |Ridestinazione|La modifica influisce sulle app ricompilate per una nuova versione di .NET Framework.|
    |Runtime|La modifica influisce su un'app esistente destinata a una versione precedente di .NET Framework, ma che viene eseguita su una versione successiva.|

-   Le eventuali API interessate.

-   ID delle diagnostiche disponibili

## <a name="usage"></a>Utilizzo

Per iniziare, selezionare il tipo di modifica della compatibilità di seguito:

- [Modifiche di reindirizzamento](./retargeting/index.md)
- [Modifiche al runtime](./runtime/index.md)


## <a name="see-also"></a>Vedere anche

[Versioni e dipendenze](../../../docs/framework/migration-guide/versions-and-dependencies.md)   
[Novità](../../../docs/framework/whats-new/index.md)   
[Elementi obsoleti nella libreria di classi](../../../docs/framework/whats-new/whats-obsolete.md)

