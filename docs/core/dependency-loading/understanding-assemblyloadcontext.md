---
title: Informazioni su AssemblyLoadContext-.NET Core
description: Concetti chiave per comprendere lo scopo e il comportamento di AssemblyLoadContext in .NET Core.
ms.date: 08/09/2019
author: sdmaclea
ms.author: stmaclea
ms.openlocfilehash: 8a73a432bf8cc72cced77cf6c62a785b72032913
ms.sourcegitcommit: 9c3a4f2d3babca8919a1e490a159c1500ba7a844
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/12/2019
ms.locfileid: "72291258"
---
# <a name="understanding-systemruntimeloaderassemblyloadcontext"></a>Informazioni su System. Runtime. loader. AssemblyLoadContext

La classe <xref:System.Runtime.Loader.AssemblyLoadContext> è univoca per .NET Core. Questo articolo tenta di integrare la documentazione dell'API <xref:System.Runtime.Loader.AssemblyLoadContext> con informazioni concettuali.

Questo articolo è pertinente per gli sviluppatori che implementano il caricamento dinamico, soprattutto per gli sviluppatori di Framework con caricamento dinamico

## <a name="what-is-the-assemblyloadcontext"></a>Che cos'è AssemblyLoadContext?

Ogni applicazione .NET Core usa in modo implicito il <xref:System.Runtime.Loader.AssemblyLoadContext>.
È il provider del runtime per l'individuazione e il caricamento delle dipendenze. Ogni volta che viene caricata una dipendenza, viene richiamata un'istanza <xref:System.Runtime.Loader.AssemblyLoadContext> per individuarla.

- Fornisce un servizio per l'individuazione, il caricamento e la memorizzazione nella cache di assembly gestiti e altre dipendenze.

- Per supportare il caricamento e lo scaricamento di codice dinamico, viene creato un contesto isolato per il caricamento del codice e delle relative dipendenze nella propria istanza <xref:System.Runtime.Loader.AssemblyLoadContext>.

## <a name="when-do-you-need-multiple-assemblyloadcontext-instances"></a>Quando sono necessarie più istanze di AssemblyLoadContext?

Una singola istanza <xref:System.Runtime.Loader.AssemblyLoadContext> è limitata al caricamento di una sola versione di un <xref:System.Reflection.Assembly> per nome di assembly semplice, <xref:System.Reflection.AssemblyName.Name?displayProperty=nameWithType>.

Questa restrizione può costituire un problema durante il caricamento dinamico dei moduli di codice. Ogni modulo è compilato in modo indipendente e può dipendere da versioni diverse di un <xref:System.Reflection.Assembly>. Questo problema si verifica in genere quando diversi moduli dipendono da versioni diverse di una libreria di uso comune.

Per supportare il caricamento dinamico del codice, l'API <xref:System.Runtime.Loader.AssemblyLoadContext> fornisce per il caricamento di versioni in conflitto di un <xref:System.Reflection.Assembly> nella stessa applicazione. Ogni istanza <xref:System.Runtime.Loader.AssemblyLoadContext> fornisce un mapping del dizionario univoco ogni <xref:System.Reflection.AssemblyName.Name?displayProperty=nameWithType> a una specifica istanza di <xref:System.Reflection.Assembly>.

Fornisce inoltre un meccanismo pratico per raggruppare le dipendenze correlate a un modulo di codice per uno scaricamento successivo.

## <a name="what-is-special-about-the-assemblyloadcontextdefault-instance"></a>Cosa è speciale per l'istanza di AssemblyLoadContext. default?

L'istanza <xref:System.Runtime.Loader.AssemblyLoadContext.Default?displayProperty=nameWithType> viene popolata automaticamente dal runtime all'avvio.  Usa il [Probe predefinito](default-probing.md) per individuare e trovare tutte le dipendenze statiche.

Risolve gli scenari più comuni di caricamento delle dipendenze.

## <a name="how-does-assemblyloadcontext-support-dynamic-dependencies"></a>In che modo AssemblyLoadContext supporta le dipendenze dinamiche?

<xref:System.Runtime.Loader.AssemblyLoadContext> ha vari eventi e funzioni virtuali di cui è possibile eseguire l'override.

L'istanza <xref:System.Runtime.Loader.AssemblyLoadContext.Default?displayProperty=nameWithType> supporta solo l'override degli eventi.

Gli articoli [algoritmo di caricamento assembly gestito](loading-managed.md), [algoritmo di caricamento assembly satellite](loading-resources.md)e [algoritmo di caricamento libreria non gestito (nativo)](loading-unmanaged.md) fanno riferimento a tutti gli eventi e le funzioni virtuali disponibili.  Gli articoli mostrano la posizione relativa di ogni evento e funzione negli algoritmi di caricamento. Questo articolo non riproduce tali informazioni.

In questa sezione vengono illustrati i principi generali per gli eventi e le funzioni rilevanti.

- **Essere ripetibile**. Una query per una dipendenza specifica deve sempre generare la stessa risposta. È necessario che venga restituita la stessa istanza di dipendenza caricata. Questo requisito è fondamentale per la coerenza della cache. Per gli assembly gestiti in particolare, si sta creando una cache <xref:System.Reflection.Assembly>. La chiave di cache è un nome di assembly semplice, <xref:System.Reflection.AssemblyName.Name?displayProperty=nameWithType>.
- **In genere non generano**.  Si prevede che queste funzioni restituiscano `null` anziché generate quando non è in grado di trovare la dipendenza richiesta. La generazione di terminerà in modo anomalo la ricerca e propagherà un'eccezione al chiamante. La generazione deve essere limitata a errori imprevisti come un assembly danneggiato o una condizione di memoria insufficiente.
- **Evitare la ricorsione**. Tenere presente che queste funzioni e gestori implementano le regole di caricamento per l'individuazione delle dipendenze. L'implementazione non deve chiamare le API che attivano la ricorsione. Il codice deve in genere chiamare le funzioni di caricamento **AssemblyLoadContext** che richiedono un percorso specifico o un argomento di riferimento alla memoria.
- **Caricare nel AssemblyLoadContext corretto**. La scelta della posizione in cui caricare le dipendenze è specifica dell'applicazione.  La scelta è implementata da questi eventi e funzioni. Quando il codice chiama **AssemblyLoadContext** funzioni di caricamento per percorso, chiamarle nell'istanza in cui si vuole caricare il codice. A volte viene restituito `null` e l'opzione che consente di gestire il carico <xref:System.Runtime.Loader.AssemblyLoadContext.Default?displayProperty=nameWithType> potrebbe essere l'opzione più semplice.
- Tenere **presente le gare di thread**. Il caricamento può essere attivato da più thread. AssemblyLoadContext gestisce le corse di thread mediante l'aggiunta atomica di assembly alla relativa cache. L'istanza di Race Loser è stata eliminata. Nella logica di implementazione non aggiungere una logica aggiuntiva che non gestisca correttamente più thread.

## <a name="how-are-dynamic-dependencies-isolated"></a>Come sono isolate le dipendenze dinamiche?

Ogni istanza <xref:System.Runtime.Loader.AssemblyLoadContext> rappresenta un ambito univoco per le istanze <xref:System.Reflection.Assembly> e le definizioni di <xref:System.Type>.

Non esiste un isolamento binario tra queste dipendenze. Sono isolate solo se non vengono individuate in base al nome.

In ogni <xref:System.Runtime.Loader.AssemblyLoadContext>:

- <xref:System.Reflection.AssemblyName.Name?displayProperty=nameWithType> può fare riferimento a un'istanza diversa di <xref:System.Reflection.Assembly>.
- <xref:System.Type.GetType%2A?displayProperty=nameWithType> può restituire un'istanza di tipo diversa per lo stesso tipo `name`.

## <a name="how-are-dependencies-shared"></a>Come vengono condivise le dipendenze?

Le dipendenze possono essere facilmente condivise tra le istanze <xref:System.Runtime.Loader.AssemblyLoadContext>. Il modello generale è per una <xref:System.Runtime.Loader.AssemblyLoadContext> per caricare una dipendenza.  L'altra condivide la dipendenza utilizzando un riferimento all'assembly caricato.

Questa condivisione è necessaria per gli assembly di Runtime. Questi assembly possono essere caricati solo nel <xref:System.Runtime.Loader.AssemblyLoadContext.Default?displayProperty=nameWithType>. Lo stesso è necessario per i Framework come `ASP.NET`, `WPF` o `WinForms`.

È consigliabile caricare le dipendenze condivise in <xref:System.Runtime.Loader.AssemblyLoadContext.Default?displayProperty=nameWithType>. Questa condivisione è il modello di progettazione comune.

La condivisione viene implementata nella codifica dell'istanza di @no__t 0 personalizzata. <xref:System.Runtime.Loader.AssemblyLoadContext> ha vari eventi e funzioni virtuali di cui è possibile eseguire l'override. Quando una di queste funzioni restituisce un riferimento a un'istanza di @no__t 0 che è stata caricata in un'altra istanza di <xref:System.Runtime.Loader.AssemblyLoadContext>, l'istanza di <xref:System.Reflection.Assembly> è condivisa. L'algoritmo Load standard rinvia a <xref:System.Runtime.Loader.AssemblyLoadContext.Default?displayProperty=nameWithType> per il caricamento per semplificare il modello di condivisione comune.  Vedere [algoritmo di caricamento assembly gestito](loading-managed.md).

## <a name="complications"></a>Complicazioni

### <a name="type-conversion-issues"></a>Problemi di conversione dei tipi

Quando due istanze <xref:System.Runtime.Loader.AssemblyLoadContext> contengono definizioni di tipi con lo stesso `name`, non sono dello stesso tipo. Si tratta dello stesso tipo se e solo se provengono dalla stessa istanza <xref:System.Reflection.Assembly>.

Per complicare le problematiche, i messaggi di eccezione relativi a questi tipi non corrispondenti possono generare confusione. Ai tipi viene fatto riferimento nei messaggi di eccezione in base ai relativi nomi di tipo semplice. Il messaggio di eccezione comune in questo caso sarà nel formato seguente:

> Non è possibile convertire l'oggetto di tipo ' IsolatedType ' nel tipo ' IsolatedType '.

### <a name="debugging-type-conversion-issues"></a>Problemi di conversione dei tipi di debug

Data una coppia di tipi non corrispondenti è importante tenere presente anche quanto segue:

- Ogni tipo <xref:System.Type.Assembly?displayProperty=nameWithType>
- Ogni tipo <xref:System.Runtime.Loader.AssemblyLoadContext>, che può essere ottenuto tramite la funzione <xref:System.Runtime.Loader.AssemblyLoadContext.GetLoadContext(System.Reflection.Assembly)?displayProperty=nameWithType>.

Considerati due oggetti `a` e `b`, la valutazione dei seguenti elementi nel debugger sarà utile:

```csharp
// In debugger look at each assembly's instance, Location, and FullName
a.GetType().Assembly
b.GetType().Assembly
// In debugger look at each AssemblyLoadContext's instance and name
System.Runtime.AssemblyLoadContext.GetLoadContext(a.GetType().Assembly)
System.Runtime.AssemblyLoadContext.GetLoadContext(b.GetType().Assembly)
```

### <a name="resolving-type-conversion-issues"></a>Risoluzione dei problemi di conversione dei tipi

Esistono due modelli di progettazione per la risoluzione di questi problemi di conversione dei tipi.

1. Usare i tipi condivisi comuni. Questo tipo condiviso può essere un tipo di runtime primitivo oppure può implicare la creazione di un nuovo tipo condiviso in un assembly condiviso.  Spesso il tipo condiviso è un' [interfaccia](../../csharp/language-reference/keywords/interface.md) definita in un assembly dell'applicazione. Vedere anche: [Come vengono condivise le dipendenze?](#how-are-dependencies-shared)

2. Utilizzare le tecniche di marshalling per convertire un tipo in un altro.
