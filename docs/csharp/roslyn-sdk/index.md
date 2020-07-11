---
title: .NET Compiler Platform SDK (API Roslyn)
description: Informazioni su come usare .NET Compiler Platform SDK (detto anche API Roslyn) per analizzare il codice .NET, individuare gli errori e risolverli.
ms.date: 10/10/2017
ms.custom: mvc
ms.openlocfilehash: 872bfd388f6974a6d99f769c43e5d341454518cc
ms.sourcegitcommit: 67cf756b033c6173a1bbd1cbd5aef1fccac99e34
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2020
ms.locfileid: "86226673"
---
# <a name="the-net-compiler-platform-sdk"></a>.NET Compiler Platform SDK

I compilatori creano un modello dettagliato del codice dell'applicazione durante la convalida della sintassi e della semantica di tale codice. Questo modello viene poi usato per compilare l'output eseguibile dal codice sorgente. .NET Compiler Platform SDK consente l'accesso a questo modello. Sempre più spesso, per ottenere una maggiore produttività ci si affida a funzionalità dell'ambiente di sviluppo integrato (IDE) quali IntelliSense, refactoring, ridenominazione intelligente, "Trova tutti i riferimenti" e "Vai a definizione". Si fa affidamento agli strumenti di analisi codice per migliorare la qualità del codice e ai generatori di codice per facilitare la costruzione dell'applicazione. Questi strumenti, man mano che diventano più intelligenti, devono accedere un numero sempre maggiore di elementi del modello che viene creato solo dai compilatori durante l'elaborazione del codice dell'applicazione. Questa è la principale missione delle API Roslyn: aprendo le caselle opache e consentendo agli strumenti e agli utenti finali di condividere la vasta gamma di compilatori di informazioni sul codice.
Anziché svolgere il ruolo di traduttori da codice sorgente opaco a codice di output basato su oggetti, tramite Roslyn i compilatori diventano piattaforme, ovvero API utilizzabili per attività correlate al codice negli strumenti e nelle applicazioni.

## <a name="net-compiler-platform-sdk-concepts"></a>Concetti relativi a .NET Compiler Platform SDK

Con .NET Compiler Platform SDK si riduce drasticamente la barriera all'ingresso per la creazione di strumenti e applicazioni incentrati su codice. Consente di creare numerose opportunità di innovazione in aree quali la metaprogrammazione, la generazione e la trasformazione del codice, l'uso interattivo dei linguaggi C# e Visual Basic e l'incorporamento di C# e Visual Basic in linguaggi specifici del dominio.

.NET Compiler Platform SDK consente di realizzare ***analizzatori*** e ***correzioni del codice*** in grado di trovare e correggere gli errori di scrittura del codice. Gli ***analizzatori*** comprendono la sintassi e la struttura del codice e rilevano gli elementi da correggere. Le ***correzioni del codice*** propongono una o più correzioni consigliate per la risoluzione degli errori del codice rilevati dagli analizzatori. In genere, un analizzatore e le correzioni del codice associate sono riuniti in un unico progetto.

Gli analizzatori e le correzioni del codice usano l'analisi statica per comprendere il codice. Non eseguono il codice, né offrono altri vantaggi a livello di test. Possono, tuttavia, sottolineare procedure che spesso causano bug, codice non gestibile o violazione di linee guida standard.

.NET Compiler Platform SDK offre un singolo set di API che consentono di esaminare e comprendere una codebase C# o Visual Basic. Grazie alla possibilità di usare questa singola codebase, si possono scrivere analizzatori e correzioni del codice più facilmente sfruttando le API di analisi sintattica e semantica fornite da .NET Compiler Platform SDK. Non dovendo più dipendere dall'attività onerosa di replica dell'analisi eseguita dal compilatore, è possibile concentrarsi sull'attività di individuazione e correzione degli errori di scrittura del codice più comuni per il progetto o la libreria.

Un vantaggio più piccolo deriva dal fatto che gli analizzatori e le correzioni del codice hanno dimensioni minori e usano molta meno memoria quando vengono caricati in Visual Studio, rispetto a quella che sarebbe necessaria se si scrivesse una codebase personalizzata per analizzare il codice in un progetto. Sfruttando le stesse classi usate dal compilatore e da Visual Studio, è possibile creare strumenti di analisi statica personalizzati. Questo significa che il team può usare gli analizzatori e le correzioni del codice senza un impatto significativo sulle prestazioni dell'IDE.

Esistono tre scenari principali per la scrittura di analizzatori e correzioni del codice:

1. [*Imporre standard di scrittura del codice a livello di team*](#enforce-team-coding-standards)
1. [*Includere linee guida nei pacchetti di librerie*](#provide-guidance-with-library-packages)
1. [*Fornire indicazioni generali*](#provide-general-guidance)

## <a name="enforce-team-coding-standards"></a>Imporre standard di scrittura del codice a livello di team

Molti team usano standard di scrittura del codice imposti tramite la revisione del codice da parte di altri membri del team. Gli analizzatori e le correzioni del codice possono rendere questo processo molto più efficiente. Le revisioni del codice vengono eseguite quando uno sviluppatore condivide il proprio lavoro con altri utenti del team. Questo significa che ha già dedicato tutto il tempo necessario per completare una nuova funzionalità prima di ricevere i commenti ed è possibile che segua per settimane abitudini non corrispondenti alle procedure stabilite dal team.

Gli analizzatori vengono eseguiti durante la scrittura del codice. Lo sviluppatore ottiene così un riscontro immediato che promuove il rispetto delle linee guida sin dall'inizio, abituandosi a scrivere codice conforme sin dalle fasi iniziali di creazione del prototipo. Quando la funzionalità è pronta per la revisione da parte di un collega, tutte le linee guida standard sono state applicate.

I team possono creare analizzatori e correzioni del codice per individuare le abitudini più comuni che violano le procedure di scrittura del codice consigliate a livello di team. Questi strumenti possono essere installati nel computer di ogni sviluppatore per imporre gli standard.

## <a name="provide-guidance-with-library-packages"></a>Includere linee guida nei pacchetti di librerie

Sono disponibili numerose librerie per gli sviluppatori .NET in NuGet.
Alcune provengono da Microsoft, alcune da società di terze parti e altre da membri e volontari della community. Queste librerie ottengono tassi di adozione maggiori e recensioni migliori quando possono essere usate efficacemente dagli sviluppatori.

Oltre a fornire la documentazione, è possibile includere anche analizzatori e correzioni del codice per l'individuazione e correzione degli usi errati più comuni della libreria. Questa possibilità di usufruire di correzioni immediate consentirà agli sviluppatori di lavorare con efficacia più rapidamente.

È possibile includere analizzatori e correzioni del codice nel pacchetto della libreria personalizzata in NuGet. In questo scenario, ogni sviluppatore che installa il pacchetto NuGet installerà anche il pacchetto dell'analizzatore. Tutti gli sviluppatori che usano la libreria avranno immediatamente a disposizione le linee guida del team sotto forma di un riscontro immediato in presenza di errori, con suggerimenti per la correzione.

## <a name="provide-general-guidance"></a>Fornire indicazioni generali

La community di sviluppatori .NET ha scoperto in base all'esperienza modelli che funzionano meglio e modelli che è preferibile evitare. Diversi membri della community hanno creato analizzatori per l'applicazione di tali modelli consigliati. Nuove esperienze, inoltre, creano sempre spazio per nuove idee.

Gli analizzatori possono essere caricati in [Visual Studio Marketplace](https://marketplace.visualstudio.com/vs) e scaricati dagli sviluppatori che usano Visual Studio. In questo modo i neofiti del linguaggio e della piattaforma possono apprendere rapidamente le procedure consolidate e diventare più velocemente produttivi nel mondo .NET. Con una più ampia diffusione, tali procedure vengono inoltre adottate dalla community.

## <a name="next-steps"></a>Passaggi successivi

.NET Compiler Platform SDK include i modelli a oggetti del linguaggio più recenti per la generazione, l'analisi e il refactoring del codice. In questa sezione è disponibile una panoramica concettuale di .NET Compiler Platform SDK. Ulteriori informazioni sono disponibili nelle sezioni guide introduttive, esempi ed esercitazioni.

Altre informazioni sui concetti di .NET Compiler Platform SDK sono disponibili in questi cinque argomenti:

- [Esplorare il codice con il visualizzatore di sintassi](syntax-visualizer.md)
- [Informazioni sul modello delle API del compilatore](compiler-api-model.md)
- [Utilizzare la sintassi](work-with-syntax.md)
- [Utilizzare la semantica](work-with-semantics.md)
- [Utilizzare un'area di lavoro](work-with-workspace.md)

Per iniziare, è necessario installare **.NET Compiler Platform SDK**:

[!INCLUDE[interactive-note](~/includes/roslyn-installation.md)]

<!--

Turn this on as more of the conceptual content is in place:
- Try the [Quickstarts](quickstart/index.md) to create your first tutorial.
- Experiment with one of the [Tutorials](tutorials/index.md).
- Explore the [Samples](samples/index.md) to see some simple analyzers.
- Read the [Concepts](concepts/index.md) to understand the ideas behind analyzers and code fixes.

-->
