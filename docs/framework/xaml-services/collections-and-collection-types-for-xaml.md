---
title: Raccolte e tipi di raccolte per XAML
ms.date: 03/30/2017
ms.assetid: 58f8e7c6-9a41-4f25-8551-c042f1315baa
ms.openlocfilehash: 4123b64545f7c47a96c4cae496046a89b7e576b0
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57494623"
---
# <a name="collections-and-collection-types-for-xaml"></a>Raccolte e tipi di raccolte per XAML

Questo argomento descrive come definire le proprietà di tipi che sono progettate per supportare una raccolta e per supportare la sintassi XAML per creare un'istanza di elementi della raccolta come elementi figlio di un elemento oggetto padre o un elemento di proprietà.

## <a name="xaml-collection-concepts"></a>Concetti di raccolta XAML

Concettualmente, una relazione in XAML in cui sono presenti più elementi figlio all'interno dell'ambito di un elemento oggetto XAML o elemento di proprietà XAML deve essere implementata come una raccolta. Tale raccolta deve essere associata a una particolare proprietà XAML del tipo XAML che rappresenta l'elemento padre nella relazione. La proprietà deve essere una raccolta perché un processore XAML prevede di assegnare ogni elemento nel markup in un elemento appena aggiunta della proprietà della raccolta sottostante.

A livello di linguaggio XAML, i requisiti specifici di supporto delle raccolte non sono definiti completamente. Il concetto che una raccolta può essere un elenco o un dizionario (ma non entrambi) viene definito a livello di linguaggio XAML, ma i tipi di backup rappresentano entrambi gli elenchi o dizionari non è definita dal linguaggio XAML.

Nei servizi XAML di .NET Framework, il concetto di supporto della raccolta XAML è più chiaramente definito in termini di .NET Framework i tipi di supporto. In particolare, il supporto XAML per le raccolte si basa su diversi concetti di .NET Framework e le API usati per elenchi e dizionari nella programmazione generale di .NET Framework.

1. Il <xref:System.Collections.IList> interfaccia indica una raccolta di elenchi.

2. Il <xref:System.Collections.IDictionary> interfaccia indica una raccolta di dizionari.

3. <xref:System.Array> rappresenta una matrice e una matrice supporta <xref:System.Collections.IList> metodi.

In ognuno di questi concetti di raccolta, un processore XAML di servizi XAML di .NET Framework prevede di chiamare il `Add` metodo in un'istanza specifica del tipo della proprietà di raccolta. In alternativa, in uno scenario di serializzazione, un processore XAML produce istanze del tipo XAML discrete per ogni elemento trovato nell'elenco, dizionario o matrice in base al concetto di specifiche di ogni raccolta di "Elementi". Questi sono: <xref:System.Collections.IList.Item%2A>; <xref:System.Collections.IDictionary.Item%2A>; l'impostazione esplicita <xref:System.Array.System%23Collections%23IList%23Item%2A> per <xref:System.Array>.

## <a name="generic-collections"></a>Raccolte generiche

Le raccolte generiche possono essere utile per la programmazione generale di .NET Framework e possono essere utilizzate anche per le proprietà della raccolta XAML. Tuttavia, il tipo generico interfacce <xref:System.Collections.Generic.IList%601> e <xref:System.Collections.Generic.IDictionary%602> non sono identificate dai processori di servizi XAML di .NET Framework XAML come equivalente a non generica <xref:System.Collections.IList> o <xref:System.Collections.IDictionary>. Anziché implementare le interfacce, è un approccio consigliato per i tipi di proprietà di raccolta generica di derivare dalle classi <xref:System.Collections.Generic.List%601> o <xref:System.Collections.Generic.Dictionary%602>. Queste classi implementano le interfacce non generiche e pertanto includono il supporto previsto per le raccolte XAML nell'implementazione di base.

## <a name="read-only-collections-and-initialization-logic"></a>Le raccolte di sola lettura e la logica di inizializzazione

In .NET Framework di programmazione, è uno schema progettuale comune per rendere le proprietà che contiene un valore di una raccolta come una raccolta di sola lettura. Questo modello consente l'istanza che possiede la proprietà di raccolta per controllare meglio cosa accade alla raccolta... In particolare, il criterio impedisce la sostituzione accidentale dell'intera raccolta di pre-esistente impostando la proprietà. In questo modello, qualsiasi accesso alla raccolta dai chiamanti invece deve essere eseguita da chiamano metodi o proprietà, supportata dal tipo di raccolta e/o le interfacce di raccolta pertinenti, ad esempio <xref:System.Collections.IList>.

Usando questo modello implica che una classe che espone una proprietà della raccolta di sola lettura prima di tutto necessario inizializzare tale proprietà per contenere una raccolta vuota. In genere l'inizializzazione viene eseguita come parte del comportamento della costruzione della classe. Per essere utile per XAML, è importante che tale logica viene sempre fatto riferimento dal costruttore predefinito, poiché XAML è in genere chiama il costruttore predefinito prima di elaborare le proprietà (proprietà della raccolta o in caso contrario).

## <a name="xaml-type-system-support-and-collections"></a>Le raccolte e supporto di sistema di tipi XAML

Oltre il meccanismo di base per l'analisi XAML e la compilazione o la serializzazione delle proprietà di raccolta, il sistema di tipi XAML implementato nei servizi XAML di .NET Framework include diverse funzionalità di progettazione relative alle raccolte in XAML.

1. <xref:System.Xaml.XamlType.IsCollection%2A> Restituisce true se il tipo XAML è supportato da un tipo che fornisce supporto delle raccolte XAML.

2. <xref:System.Xaml.XamlType.IsDictionary%2A> e <xref:System.Xaml.XamlType.IsArray%2A> può identificare ulteriormente la modalità di raccolta supporta il tipo XAML. Per XAML personalizzato processori a cui si basano su servizi XAML di .NET Framework e di XAML sistema di tipi ma non in base a esistente <xref:System.Xaml.XamlWriter> implementazioni, sapendo che viene utilizzata la modalità di raccolta potrebbe essere necessario per conoscere il metodo da richiamare per elaborazione della raccolta.

3. Ognuno dei valori della proprietà precedente potenzialmente sono influenzate dalle sostituzioni di <xref:System.Xaml.XamlType.LookupCollectionKind%2A> su un tipo XAML.
