---
title: Panoramica di .NET
description: Panoramica guidata di alcune delle principali funzionalità di .NET.
author: cartermp
ms.author: wiwagn
ms.date: 05/22/2017
ms.technology: dotnet-standard
ms.assetid: bbfe6465-329d-4982-869d-472e7ef85d93
ms.openlocfilehash: 0154910b91df0b2f72daebe802e4c75bbca964bb
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75337585"
---
# <a name="tour-of-net"></a>Panoramica di .NET

.NET è una piattaforma di sviluppo con finalità generali che offre varie funzionalità chiave, ad esempio il supporto per più linguaggi di programmazione, modelli di programmazione asincroni e simultanei e l'interoperabilità nativa, che consente l'esecuzione di un'ampia gamma di scenari su più piattaforme.

Questo articolo offre una panoramica guidata di alcune delle principali funzionalità di .NET. Per informazioni sui componenti dell'architettura di .NET e sulle relative modalità d'uso, vedere l'argomento [Componenti dell'architettura .NET](components.md).

## <a name="how-to-run-the-code-samples"></a>Come eseguire i codici di esempio

Per informazioni su come configurare un ambiente di sviluppo all'interno del quale eseguire i codici di esempio, vedere l'articolo [Introduzione](get-started.md). È possibile copiare i codici di esempio da questa pagina e incollarli nel proprio ambiente per eseguirli. 

## <a name="programming-languages"></a>Linguaggi di programmazione

.NET supporta più linguaggi di programmazione. Le implementazioni di .NET implementano l'[infrastruttura CLI](https://visualstudio.microsoft.com/license-terms/ecma-c-common-language-infrastructure-standards/) che, tra altre cose, specifica un runtime indipendente dal linguaggio e l'interoperabilità di linguaggio. In questo modo, è possibile scegliere qualsiasi linguaggio .NET per creare applicazioni e servizi in .NET.

Microsoft sviluppa e supporta attivamente tre linguaggi .NET: C#, F#e Visual Basic. 

* C# è un linguaggio semplice, potente, indipendente dai tipi e orientato agli oggetti che mantiene al tempo stesso l'espressività e l'eleganza tipiche dei linguaggi di tipo C. Gli sviluppatori che hanno familiarità con C e linguaggi simili si adattano con facilità a C#. Per altre informazioni su C#, vedere [Guida a C#](../csharp/index.yml).

* F# è un linguaggio di programmazione multipiattaforma e funzionale che supporta anche la programmazione tradizionale imperativa e orientata agli oggetti. Per altre informazioni su F#, vedere [Guida a F#](../fsharp/index.yml).

* Visual Basic è un linguaggio semplice da apprendere che consente di creare una vasta gamma di app da eseguire in .NET. Tra i linguaggi .NET, la sintassi di Visual Basic è la più vicina alla lingua umana comune, rendendo spesso più semplice per gli utenti nuovi allo sviluppo del software.

## <a name="automatic-memory-management"></a>Gestione automatica della memoria

.NET usa [Garbage Collection](garbage-collection/index.md) per consentire la gestione automatica della memoria per i programmi. Garbage Collection ha un approccio "lazy" alla gestione della memoria, anteponendo la velocità effettiva dell'app alla raccolta immediata di memoria. Per altre informazioni sul Garbage Collector di.NET, vedere [Principi fondamentali di Garbage Collection](garbage-collection/fundamentals.md).

Le due righe di codice seguenti allocano entrambe memoria:

[!code-csharp[MemoryManagement](../../samples/csharp/snippets/tour/MemoryManagement.csx#L1-L2)]

Non esiste una parola chiave analoga per deallocare la memoria, in quanto la deallocazione viene eseguita automaticamente quando il Garbage Collector recupera la memoria durante l'esecuzione pianificata.

Garbage Collector è uno dei servizi che consentono di garantire la *sicurezza della memoria*. Un programma è sicuro a livello di memoria se accede solo alla memoria allocata. Il runtime assicura ad esempio che un'app non acceda a memoria non allocata oltre i limiti di una matrice.

Nell'esempio seguente il runtime genera un'eccezione <xref:System.IndexOutOfRangeException> per garantire la sicurezza della memoria:

[!code-csharp[MemoryManagement](../../samples/csharp/snippets/tour/MemoryManagement.csx#L4-L5)]

## <a name="working-with-unmanaged-resources"></a>Utilizzo di risorse non gestite

Alcuni oggetti fanno riferimento a *risorse non gestite*. Le risorse non gestite sono risorse che non vengono gestite automaticamente dal runtime di .NET. Ad esempio, un handle di file è una risorsa non gestita. Un oggetto <xref:System.IO.FileStream> è un oggetto gestito, ma fa riferimento a un handle di file, che non è gestito. Dopo aver usato <xref:System.IO.FileStream>, è necessario rilasciare l'handle di file.

In .NET gli oggetti che fanno riferimento a risorse non gestite implementano l'interfaccia <xref:System.IDisposable>. Dopo aver usato l'oggetto, è possibile chiamare il metodo <xref:System.IDisposable.Dispose> dell'oggetto, che è responsabile del rilascio delle risorse non gestite. I linguaggi .NET forniscono una comoda [istruzione`using`](../csharp/language-reference/keywords/using.md) per tali oggetti, come illustrato nell'esempio seguente:

[!code-csharp[UnmanagedResources](../../samples/csharp/snippets/tour/UnmanagedResources.csx#L1-L6)]

Dopo che il blocco `using` è stato completato, il runtime di .NET chiama automaticamente il metodo <xref:System.IDisposable.Dispose> dell'oggetto `stream`, che rilascia l'handle di file. Il runtime esegue questa operazione anche se un'eccezione fa sì che il controllo lasci il blocco.

Per informazioni dettagliate, vedere gli argomenti seguenti:

* Per C#, vedere l'argomento [Istruzione using (Riferimenti per C#)](../csharp/language-reference/keywords/using-statement.md).
* Per F#, vedere [Resource Management: The use Keyword](../fsharp/language-reference/resource-management-the-use-keyword.md) (Gestione delle risorse: la parola chiave use).
* Per Visual Basic, vedere l'argomento [istruzioni using (Visual Basic)](../visual-basic/language-reference/statements/using-statement.md) .

## <a name="type-safety"></a>Indipendenza dai tipi

Un oggetto è un'istanza di un tipo specifico. Le uniche operazioni consentite per un determinato oggetto sono quelle del relativo tipo. Un oggetto `Dog` può avere i metodi `Jump` e `WagTail`, ma non un metodo `SumTotal`. Un programma chiama solo i metodi appartenenti a un tipo specifico. Tutte le altre chiamate generano un errore in fase di compilazione o un'eccezione di runtime, se si usano funzionalità dinamiche o `object`.

I linguaggi .NET sono orientati agli oggetti, con gerarchie di classi di base e derivate. Il runtime .NET consente solo cast degli oggetti e chiamate allineate alla gerarchia di oggetti. Si tenga presente che ogni tipo definito in un qualsiasi linguaggio .NET deriva dal tipo di base <xref:System.Object>.

[!code-csharp[TypeSafety](../../samples/csharp/snippets/tour/TypeSafety.csx#L19-L23)]

L'indipendenza dai tipi viene inoltre usata per forzare l'incapsulamento garantendo la fedeltà delle parole chiave di accesso. Le parole chiave di accesso sono elementi che controllano l'accesso ai membri di un determinato tipo da parte di altro codice. Vengono in genere usate per diversi dati presenti all'interno di un tipo e per gestire il comportamento del tipo stesso.

[!code-csharp[TypeSafety](../../samples/csharp/snippets/tour/TypeSafety.csx#L3-L3)]

C#, Visual Basic e F# supportano l'*inferenza del tipo* locale. Con l'inferenza del tipo, il compilatore deduce il tipo dell'espressione sul lato sinistro dall'espressione sul lato destro. Questo non significa che l'indipendenza dai tipi è interrotta o evitata. Il tipo risultante ha un tipo sicuro, con tutto quello che implica tale caratteristica. Nell'esempio precedente `dog` viene riscritto per introdurre l'inferenza del tipo e il resto dell'esempio non subisce modifiche:

[!code-csharp[TypeSafety](../../samples/csharp/snippets/tour/TypeSafety.csx#L28-L34)]

F#dispone anche di altre funzionalità di inferenza del tipo rispetto all'inferenza del C# tipo locale del metodo disponibile in e Visual Basic. Per altre informazioni, vedere [Inferenza del tipo](../fsharp/language-reference/type-inference.md).

## <a name="delegates-and-lambdas"></a>Delegati e lambda

Un delegato è rappresentato da una firma del metodo. Ogni metodo con tale firma può essere assegnato al delegato e viene eseguito quando viene richiamato il delegato.

I delegati sono simili ai puntatori a funzione del linguaggio C++, ma sono indipendenti dai tipi. Sono un tipo di metodo disconnesso all'interno del sistema di tipo CLR. I metodi regolari sono collegati a una classe e possono essere chiamati direttamente solo tramite convenzioni di chiamata statiche o di istanza.

In .NET i delegati vengono usati comunemente nei gestori dell'evento, nella definizione delle operazioni asincrone e nelle espressioni lambda, che costituiscono uno degli elementi fondamentali di LINQ. Per altre informazioni, vedere l'argomento [Delegati e lambda](delegates-lambdas.md).

## <a name="generics"></a>Generics

I generics consentono al programmatore di introdurre un *parametro di tipo* durante la definizione delle classi, operazione che consente al codice client (gli utenti del tipo) di specificare il tipo esatto da usare al posto del parametro di tipo.

I generics sono stati aggiunti per consentire ai programmatori di implementare strutture dati generiche. Prima del loro arrivo, per un tipo, ad esempio il tipo `List` essere generico, sarebbe necessario utilizzare elementi di tipo `object`. Si sono verificati diversi problemi di prestazioni e semantica, oltre a possibili errori di run-time. Un errore di run-time comune si verifica quando una struttura di dati contiene, ad esempio, sia numeri interi che stringhe e viene generata un'<xref:System.InvalidCastException> durante l'elaborazione dei membri dell'elenco.

L'esempio seguente mostra un programma di base in esecuzione mediante un'istanza dei tipi <xref:System.Collections.Generic.List%601>:

[!code-csharp[GenericsShort](../../samples/csharp/snippets/tour/GenericsShort.csx)]

Per altre informazioni, vedere l'argomento [Panoramica di tipi generici (generics)](generics.md).

## <a name="async-programming"></a>Programmazione asincrona

La programmazione asincrona è uno dei concetti fondamentali di .NET, poiché offre supporto asincrono nel runtime, nelle librerie del framework e nei costrutti dei linguaggi .NET. A livello interno, questi elementi sono basati su oggetti, ad esempio `Task`, e sfruttano i vantaggi offerti dal sistema operativo per eseguire i processi di I/O nel modo più efficiente possibile.

Per altre informazioni sulla programmazione asincrona in .NET, iniziare con la lettura dell'argomento [Panoramica della programmazione asincrona](async.md).

## <a name="language-integrated-query-linq"></a>LINQ (Language-Integrated Query)

LINQ è un potente set di funzionalità per C# e Visual Basic che consentono di scrivere codice semplice e dichiarativo per operare sui dati. I dati possono avere diverse forme, ad esempio oggetti in memoria, dati in un database SQL o un documento XML, ma il codice LINQ scritto non presenta in genere differenze in base alle origini dati.

Per altre informazioni e alcuni esempi, vedere l'argomento [LINQ (Language-Integrated Query)](using-linq.md).

## <a name="native-interoperability"></a>Interoperabilità nativa

Ogni sistema operativo include un'API (Application Programming Interface) che fornisce servizi di sistema. .NET consente di chiamare tali API in diversi modi.

Il metodo principale per ottenere l'interoperabilità nativa è usare "platform invoke", abbreviato in P/Invoke, supportato nelle piattaforme Linux e Windows. Un metodo, valido solo per Windows, per ottenere l'interoperabilità nativa è noto come "interoperabilità COM" ed è usato per operare con [componenti COM](/cpp/atl/introduction-to-com) nel codice gestito. Tale metodo è basato sull'infrastruttura P/Invoke, ma funziona in modo leggermente diverso.

La maggior parte del supporto per l'interoperabilità di Mono (e di Xamarin) per Java e Objective-C è realizzato in modo simile, nel senso che vengono usati gli stessi principi.

Per altre informazioni sull'interoperabilità nativa, vedere l'articolo [Interoperabilità nativa](native-interop/index.md).

## <a name="unsafe-code"></a>Codice di tipo unsafe

In base al supporto del linguaggio, CLR consente di accedere alla memoria nativa e di eseguire l'aritmetica dei puntatori tramite il codice `unsafe`. Queste operazioni sono necessarie per determinati algoritmi e per l'interoperabilità dei sistemi. Anche se il codice di tipo unsafe è uno strumento potente, non è consigliabile usarlo a meno che non sia necessario per l'interoperabilità con API di sistema o per implementare l'algoritmo più efficiente. Il codice di tipo unsafe non può essere eseguito nello stesso modo in ambienti diversi e inoltre non sfrutta i vantaggi offerti da un Garbage Collector e dall'indipendenza dai tipi. È consigliabile limitare e centralizzare il codice di tipo unsafe nella misura massima possibile. È inoltre necessario testare tale codice in modo accurato.

L'esempio seguente è una versione modificata del metodo `ToString()` della classe `StringBuilder` e illustra come l'uso di codice `unsafe` possa implementare in modo efficiente un algoritmo spostando direttamente blocchi di memoria:

[!code-csharp[Unsafe](../../samples/csharp/snippets/tour/Unsafe.csx)]

## <a name="next-steps"></a>Passaggi successivi

Per una panoramica delle funzionalità di C#, vedere [Tour of C#](../csharp/tour-of-csharp/index.md) (Panoramica di C#).

Per una panoramica delle funzionalità di F#, vedere l'articolo [Tour of F#](../fsharp/tour.md) (Panoramica di F#).

Per un'introduzione alla scrittura di codice personalizzato, vedere [Introduzione](get-started.md).

Per informazioni sui componenti principali di .NET, vedere [Componenti dell'architettura .NET](components.md).
