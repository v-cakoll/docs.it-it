---
title: Concetti e modello a oggetti di .NET Compiler Platform SDK
description: Questa panoramica include le informazioni di base necessarie per utilizzare in modo efficiente l'SDK del compilatore .NET. Vengono presentati i livelli dell'API, i tipi principali coinvolti e il modello a oggetti generale.
ms.date: 07/13/2020
ms.custom: mvc
ms.openlocfilehash: a65d282dd3c58279bbfd635c0386d50ce3f30055
ms.sourcegitcommit: e7748001b1cee80ced691d8a76ca814c0b02dd9b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2020
ms.locfileid: "86374468"
---
# <a name="understand-the-net-compiler-platform-sdk-model"></a>Informazioni sul modello di .NET Compiler Platform SDK

I compilatori elaborano il codice scritto seguendo regole strutturate spesso diverse dal modo in cui gli essere umani leggono e interpretano il codice. Una conoscenza di base del modello usato dai compilatori è essenziale per comprendere le API usate durante la compilazione di strumenti basati su Roslyn.

## <a name="compiler-pipeline-functional-areas"></a>Aree funzionali della pipeline del compilatore

.NET Compiler Platform SDK espone l'analisi del codice dei compilatori C# e Visual Basic tramite un livello API che rispecchia una pipeline del compilatore tradizionale.

![Passaggi della pipeline del compilatore per l'elaborazione del codice sorgente come codice oggetti](media/compiler-api-model/compiler-pipeline.png)

Ogni fase della pipeline è un componente separato. Innanzitutto, la fase di analisi suddivide in token e analizza il testo di origine convertendolo in sintassi conforme alla grammatica del linguaggio. In secondo luogo, la fase di dichiarazione analizza l'origine e i metadati importati per formare simboli denominati. La fase di associazione abbina poi gli identificatori nel codice ai simboli. La fase di creazione, infine, genera un assembly con tutte le informazioni raccolte dal compilatore.

![L'API della pipeline del compilatore consente l'accesso a ogni passaggio incluso nella pipeline](media/compiler-api-model/compiler-pipeline-api.png)

In modo corrispondente a ciascuna di queste fasi, .NET Compiler Platform SDK espone un modello a oggetti che consente l'accesso alle informazioni in tale fase. La fase di analisi espone un albero della sintassi, la fase di dichiarazione espone una tabella dei simboli gerarchici, la fase di associazione espone il risultato dell'analisi semantica del compilatore e la fase di creazione è un'API che produce codici di byte IL.

![Servizi di linguaggio disponibili dall'API del compilatore in ogni fase della pipeline del compilatore](media/compiler-api-model/compiler-pipeline-lang-svc.png)

Ogni compilatore combina questi componenti come singola unità completa.

Queste API sono le stesse usate da Visual Studio. Ad esempio, la struttura del codice e le funzionalità di formattazione usano gli alberi della sintassi, le funzionalità di **Visualizzatore oggetti**e di navigazione usano la tabella dei simboli, i refactoring e **Vai a definizione** usano il modello semantico e **modifica e continuazione** usa tutti questi elementi, inclusa l'API Emit.

## <a name="api-layers"></a>Livelli delle API

.NET Compiler SDK è costituito da diversi livelli di API: API del compilatore, API di diagnostica, API di scripting e API per le aree di lavoro.

### <a name="compiler-apis"></a>API del compilatore

Il livello del compilatore contiene i modelli a oggetti che corrispondono alle informazioni esposte in ogni fase della pipeline del compilatore, sia semantiche che sintattiche. Il livello del compilatore contiene anche uno snapshot non modificabile di una singola chiamata di un compilatore, inclusi riferimenti ad assembly, opzioni del compilatore e file del codice sorgente. Esistono due API distinte che rappresentano il linguaggio C# e il linguaggio Visual Basic. Le due API sono simili in forma, ma sono personalizzate per la massima fedeltà a ogni singolo linguaggio. Questo livello non ha dipendenze da componenti di Visual Studio.

### <a name="diagnostic-apis"></a>API di diagnostica

Come parte dell'analisi, il compilatore può produrre un set di dati diagnostici relativi a tutti gli elementi: sintassi, semantica, precisi errori di assegnazione, vari avvisi e dati diagnostici informativi. Il livello dell'API del compilatore espone i dati diagnostici tramite un'API estensibile che consente di integrare analizzatori definiti dall'utente nel processo di compilazione. Consente di produrre dati diagnostici definiti dall'utente, ad esempio quelli prodotti da strumenti come StyleCop o FxCop, insieme a quelli definiti dal compilatore. La produzione di diagnostica in questo modo offre il vantaggio di integrarsi naturalmente con strumenti come MSBuild e Visual Studio, che dipendono dalla diagnostica per esperienze quali l'arresto di una compilazione in base ai criteri e la visualizzazione di controllo ortografia durante in tempo reale nell'editor e il suggerimento di correzioni del codice.

### <a name="scripting-apis"></a>API di scripting

Le API di hosting e scripting fanno parte del livello del compilatore. È possibile usarle per eseguire frammenti di codice e accumulare un contesto di esecuzione di runtime.
Il ciclo Read–Eval–Print (REPL) interattivo di C# usa queste API. Il ciclo REPL consente di usare C# come linguaggio di scripting, eseguendo il codice in modo interattivo mentre lo si scrive.

### <a name="workspaces-apis"></a>API delle aree di lavoro

Il livello delle aree di lavoro contiene l'API Workspace, ovvero il punto di partenza per eseguire l'analisi del codice e il refactoring su intere soluzioni. Consente di organizzare tutte le informazioni sui progetti in una soluzione in un unico modello a oggetti, offrendo accesso diretto ai modelli a oggetti del livello del compilatore senza la necessità di analizzare i file, configurare le opzioni o gestire le dipendenze da progetto a progetto.

Inoltre, il livello delle aree di lavoro espone un set di API usate durante l'implementazione di strumenti di analisi del codice e refactoring che operano all'interno di un ambiente host come l'IDE di Visual Studio. Sono esempi le API Trova tutti i riferimenti, Formattazione e Generazione codice.

Questo livello non ha dipendenze da componenti di Visual Studio.
