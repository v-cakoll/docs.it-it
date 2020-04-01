---
title: Informazioni su AssemblyLoadContext - .NET CoreUnderstanding AssemblyLoadContext - .NET Core
description: Concetti chiave per comprendere lo scopo e il comportamento di AssemblyLoadContext in .NET Core.Key concepts to understand the purpose and behavior of AssemblyLoadContext in .NET Core.
ms.date: 08/09/2019
author: sdmaclea
ms.author: stmaclea
ms.openlocfilehash: 43fb0d792ddeb20b8a141af452a86dd50f37ba43
ms.sourcegitcommit: 79b0dd8bfc63f33a02137121dd23475887ecefda
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2020
ms.locfileid: "80523604"
---
# <a name="understanding-systemruntimeloaderassemblyloadcontext"></a>Informazioni su System.Runtime.Loader.AssemblyLoadContextUnderstanding System.Runtime.Loader.AssemblyLoadContext

La <xref:System.Runtime.Loader.AssemblyLoadContext> classe è univoca per .NET Core.The class is unique to .NET Core. Questo articolo tenta <xref:System.Runtime.Loader.AssemblyLoadContext> di integrare la documentazione dell'API con informazioni concettuali.

Questo articolo è rilevante per gli sviluppatori che implementano il caricamento dinamico, in particolare gli sviluppatori di framework di caricamento dinamico.

## <a name="what-is-the-assemblyloadcontext"></a>Che cos'è AssemblyLoadContext?

Ogni applicazione .NET Core <xref:System.Runtime.Loader.AssemblyLoadContext>utilizza in modo implicito l'oggetto .
È il provider del runtime per l'individuazione e il caricamento delle dipendenze. Ogni volta che viene <xref:System.Runtime.Loader.AssemblyLoadContext> caricata una dipendenza, viene richiamata un'istanza per individuarla.

- Fornisce un servizio di individuazione, caricamento e memorizzazione nella cache di assembly gestiti e altre dipendenze.

- Per supportare il caricamento e lo scaricamento dinamici del codice, <xref:System.Runtime.Loader.AssemblyLoadContext> crea un contesto isolato per il caricamento del codice e le relative dipendenze nella propria istanza.

## <a name="when-do-you-need-multiple-assemblyloadcontext-instances"></a>Quando sono necessarie più istanze di AssemblyLoadContext?

Una <xref:System.Runtime.Loader.AssemblyLoadContext> singola istanza è limitata al <xref:System.Reflection.Assembly> caricamento di esattamente <xref:System.Reflection.AssemblyName.Name?displayProperty=nameWithType>una versione di un nome di assembly per un nome di assembly semplice, .

Questa restrizione può diventare un problema durante il caricamento dinamico dei moduli di codice. Ogni modulo è compilato in modo indipendente <xref:System.Reflection.Assembly>e può dipendere da versioni diverse di un file . Questo problema si verifica in genere quando diversi moduli dipendono da versioni diverse di una libreria di uso comune.

Per supportare il <xref:System.Runtime.Loader.AssemblyLoadContext> caricamento dinamico del codice, <xref:System.Reflection.Assembly> l'API fornisce per il caricamento di versioni in conflitto di un oggetto nella stessa applicazione. Ogni <xref:System.Runtime.Loader.AssemblyLoadContext> istanza fornisce un <xref:System.Reflection.AssemblyName.Name?displayProperty=nameWithType> dizionario <xref:System.Reflection.Assembly> univoco che esegue il mapping di ogni istanza a un'istanza specifica.

Fornisce inoltre un pratico meccanismo per raggruppare le dipendenze correlate a un modulo di codice per uno scaricamento successivo.

## <a name="what-is-special-about-the-assemblyloadcontextdefault-instance"></a>Quali sono le caratteristiche speciali dell'istanza di AssemblyLoadContext.Default?

L'istanza <xref:System.Runtime.Loader.AssemblyLoadContext.Default?displayProperty=nameWithType> viene popolata automaticamente dal runtime all'avvio.  Utilizza il [probe predefinito](default-probing.md) per individuare e trovare tutte le dipendenze statiche.

Risolve gli scenari di caricamento delle dipendenze più comuni.

## <a name="how-does-assemblyloadcontext-support-dynamic-dependencies"></a>In che modo AssemblyLoadContext supporta le dipendenze dinamiche?

<xref:System.Runtime.Loader.AssemblyLoadContext>ha vari eventi e funzioni virtuali che possono essere sostituiti.

L'istanza <xref:System.Runtime.Loader.AssemblyLoadContext.Default?displayProperty=nameWithType> supporta solo l'override degli eventi.

Gli articoli Algoritmo di [caricamento assembly gestiti](loading-managed.md), [Algoritmo](loading-resources.md)di caricamento assembly Satellite e Algoritmo di [caricamento libreria non gestita (nativa)](loading-unmanaged.md) fanno riferimento a tutti gli eventi e le funzioni virtuali disponibili.  Gli articoli mostrano la posizione relativa di ogni evento e funzione negli algoritmi di caricamento. In questo articolo non vengono riprodotti tali informazioni.

In questa sezione vengono illustrati i principi generali per gli eventi e le funzioni pertinenti.

- **Essere ripetibile**. Una query per una dipendenza specifica deve sempre generare la stessa risposta. Deve essere restituita la stessa istanza di dipendenza caricata. Questo requisito è fondamentale per la coerenza della cache. Per gli assembly gestiti in <xref:System.Reflection.Assembly> particolare, stiamo creando una cache. La chiave di cache è <xref:System.Reflection.AssemblyName.Name?displayProperty=nameWithType>un nome di assembly semplice, .
- **In genere non gettare**.  Si prevede che queste `null` funzioni restituiscano anziché generare quando non è possibile trovare la dipendenza richiesta. La generazione terminerà prematuramente la ricerca e verrà propagata un'eccezione al chiamante. La generazione deve essere limitata a errori imprevisti, ad esempio un assembly danneggiato o una condizione di memoria insufficiente.
- **Evitare la ricorsione**. Tenere presente che queste funzioni e gestori implementano le regole di caricamento per individuare le dipendenze. L'implementazione non deve chiamare API che attivano la ricorsione. Il codice deve in genere chiamare funzioni di caricamento **AssemblyLoadContext** che richiedono un percorso specifico o un argomento di riferimento alla memoria.
- **Caricare nell'assemblyLoadContext corretto.** La scelta della posizione in cui caricare le dipendenze è specifica dell'applicazione.  La scelta è implementata da questi eventi e funzioni. Quando il codice chiama le funzioni load-by-path **AssemblyLoadContext** le chiamano nell'istanza in cui si desidera caricare il codice. A volte `null` la restituzione e la lasciare che il <xref:System.Runtime.Loader.AssemblyLoadContext.Default?displayProperty=nameWithType> carico possa essere l'opzione più semplice.
- **Essere consapevoli delle gare di thread**. Il caricamento può essere attivato da più thread. Il AssemblyLoadContext gestisce le gare di thread aggiungendo in modo atomico gli assembly alla relativa cache. L'istanza del perdente di razza viene scartata. Nella logica di implementazione, non aggiungere logica aggiuntiva che non gestisce correttamente più thread.

## <a name="how-are-dynamic-dependencies-isolated"></a>Come vengono isolate le dipendenze dinamiche?

Ogni <xref:System.Runtime.Loader.AssemblyLoadContext> istanza rappresenta un <xref:System.Reflection.Assembly> ambito <xref:System.Type> univoco per istanze e definizioni.

Non esiste alcun isolamento binario tra queste dipendenze. Sono isolati solo non trovandosi l'un l'altro per nome.

In <xref:System.Runtime.Loader.AssemblyLoadContext>ogni :

- <xref:System.Reflection.AssemblyName.Name?displayProperty=nameWithType>può riferirsi <xref:System.Reflection.Assembly> a un'istanza diversa.
- <xref:System.Type.GetType%2A?displayProperty=nameWithType>può restituire un'istanza di `name`tipo diversa per lo stesso tipo .

## <a name="how-are-dependencies-shared"></a>Come vengono condivise le dipendenze?

Le dipendenze possono <xref:System.Runtime.Loader.AssemblyLoadContext> essere facilmente condivise tra le istanze. Il modello generale <xref:System.Runtime.Loader.AssemblyLoadContext> prevede che uno carichi una dipendenza.  L'altro condivide la dipendenza utilizzando un riferimento all'assembly caricato.

Questa condivisione è obbligatoria per gli assembly di runtime. Questi assembly possono essere <xref:System.Runtime.Loader.AssemblyLoadContext.Default?displayProperty=nameWithType>caricati solo nel file . Lo stesso è necessario `ASP.NET`per `WPF`framework `WinForms`come , , o .

È consigliabile caricare le dipendenze <xref:System.Runtime.Loader.AssemblyLoadContext.Default?displayProperty=nameWithType>condivise in . Questa condivisione è il modello di progettazione comune.

La condivisione viene implementata <xref:System.Runtime.Loader.AssemblyLoadContext> nella codifica dell'istanza personalizzata. <xref:System.Runtime.Loader.AssemblyLoadContext>ha vari eventi e funzioni virtuali che possono essere sostituiti. Quando una di queste funzioni <xref:System.Reflection.Assembly> restituisce un riferimento <xref:System.Runtime.Loader.AssemblyLoadContext> a <xref:System.Reflection.Assembly> un'istanza caricata in un'altra istanza, l'istanza viene condivisa. L'algoritmo di <xref:System.Runtime.Loader.AssemblyLoadContext.Default?displayProperty=nameWithType> caricamento standard rinvia a per il caricamento per semplificare il modello di condivisione comune.  Vedere Algoritmo di [caricamento di assembly gestiti](loading-managed.md).

## <a name="complications"></a>Complicazioni

### <a name="type-conversion-issues"></a>Problemi di conversione dei tipi

Quando <xref:System.Runtime.Loader.AssemblyLoadContext> due istanze contengono `name`definizioni di tipo con lo stesso , non sono dello stesso tipo. Sono dello stesso tipo se e solo se <xref:System.Reflection.Assembly> provengono dalla stessa istanza.

Per complicare le cose, i messaggi di eccezione su questi tipi non corrispondenti possono creare confusione. I tipi sono indicati nei messaggi di eccezione dai relativi nomi di tipo semplice. Il messaggio di eccezione comune in questo caso sarebbe nel formato:

> Impossibile convertire l'oggetto di tipo 'IsolatedType' nel tipo 'IsolatedType'.

### <a name="debugging-type-conversion-issues"></a>Problemi di conversione dei tipi di debugDebugging type conversion issues

Data una coppia di tipi non corrispondenti è importante conoscere anche:

- Ogni tipo di<xref:System.Type.Assembly?displayProperty=nameWithType>
- Di <xref:System.Runtime.Loader.AssemblyLoadContext>ogni tipo, che può <xref:System.Runtime.Loader.AssemblyLoadContext.GetLoadContext(System.Reflection.Assembly)?displayProperty=nameWithType> essere ottenuto tramite la funzione.

Dato due `a` `b`oggetti e , la valutazione di quanto segue nel debugger sarà utile:

```csharp
// In debugger look at each assembly's instance, Location, and FullName
a.GetType().Assembly
b.GetType().Assembly
// In debugger look at each AssemblyLoadContext's instance and name
System.Runtime.Loader.AssemblyLoadContext.GetLoadContext(a.GetType().Assembly)
System.Runtime.Loader.AssemblyLoadContext.GetLoadContext(b.GetType().Assembly)
```

### <a name="resolving-type-conversion-issues"></a>Risoluzione dei problemi di conversione dei tipi

Esistono due modelli di progettazione per risolvere questi problemi di conversione dei tipi.

1. Utilizzare tipi condivisi comuni. Questo tipo condiviso può essere un tipo di runtime primitivo o può comportare la creazione di un nuovo tipo condiviso in un assembly condiviso.  Spesso il tipo condiviso è [un'interfaccia](../../csharp/language-reference/keywords/interface.md) definita in un assembly dell'applicazione. Vedere anche: [Come vengono condivise le dipendenze?](#how-are-dependencies-shared).

2. Utilizzare tecniche di marshalling per eseguire la conversione da un tipo a un altro.
