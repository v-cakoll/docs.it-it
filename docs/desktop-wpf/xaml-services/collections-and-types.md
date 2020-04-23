---
title: Raccolte e tipi di raccolte per XAML
ms.date: 03/30/2017
ms.assetid: 58f8e7c6-9a41-4f25-8551-c042f1315baa
ms.openlocfilehash: 2ec58026c605df31489c8aab4c4cc714dab11474
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "82071297"
---
# <a name="collections-and-collection-types-for-xaml"></a>Raccolte e tipi di raccolta per XAMLCollections and collection types for XAML

In questo articolo viene descritto come definire le proprietà dei tipi destinati a supportare una raccolta e per supportare la sintassi XAML per la creazione di istanze di elementi della raccolta come elementi figlio di un elemento oggetto padre o di un elemento proprietà.

## <a name="xaml-collection-concepts"></a>Concetti relativi alle raccolte XAMLXAML Collection Concepts

Concettualmente, qualsiasi relazione in XAML in cui sono presenti più elementi figlio all'interno dell'ambito di un elemento oggetto XAML o di un elemento proprietà XAML deve essere implementata come raccolta. Tale raccolta deve essere associata a una particolare proprietà XAML del tipo XAML che è l'elemento padre in tale relazione. La proprietà deve essere una raccolta perché un processore XAML prevede di assegnare ogni elemento nel markup come elemento appena aggiunto della proprietà della raccolta di backup.

A livello di linguaggio XAML, i requisiti esatti del supporto della raccolta non sono completamente definiti. Il concetto che una raccolta può essere un elenco o un dizionario (ma non entrambi) è definito a livello di linguaggio XAML, ma quali tipi di supporto rappresentano elenchi o dizionari non è definito dal linguaggio XAML.

Nei servizi XAML di .NET, il concetto di supporto della raccolta XAML è definito in modo più chiaro in termini di tipi di supporto .NET. In particolare, il supporto XAML per le raccolte si basa su diversi concetti e API di .NET utilizzati per elenchi e dizionari nella programmazione .NET generale.

1. L'interfaccia <xref:System.Collections.IList> indica una raccolta di elenchi.

2. L'interfaccia <xref:System.Collections.IDictionary> indica una raccolta di dizionario.

3. <xref:System.Array>rappresenta una matrice e una <xref:System.Collections.IList> matrice supporta i metodi.

In ognuno di questi concetti di raccolta, un processore `Add` XAML dei servizi XAML .NET prevede di chiamare il metodo su un'istanza specifica del tipo della proprietà della raccolta. In alternativa, in uno scenario di serializzazione, un processore XAML produce istanze di tipo XAML discrete per ogni elemento trovato nell'elenco, nel dizionario o nella matrice in base al concetto specifico di "Items" di ogni raccolta. Questi elementi <xref:System.Collections.IList.Item%2A?displayProperty=nameWithType>sono: ; <xref:System.Collections.IDictionary.Item%2A?displayProperty=nameWithType>; l'esplicito <xref:System.Array.System%23Collections%23IList%23Item%2A?displayProperty=nameWithType> per <xref:System.Array>.

## <a name="generic-collections"></a>Raccolte generiche

Le raccolte generiche possono essere utili per la programmazione generale .NET e possono essere usate anche per le proprietà della raccolta XAML. Tuttavia, le <xref:System.Collections.Generic.IList%601> interfacce generiche e <xref:System.Collections.Generic.IDictionary%602> non sono identificate dai processori <xref:System.Collections.IList> XAML <xref:System.Collections.IDictionary>dei servizi XAML .NET come equivalenti a quelle non generiche o . Anziché implementare le interfacce, un approccio consigliato per <xref:System.Collections.Generic.List%601> i <xref:System.Collections.Generic.Dictionary%602>tipi di proprietà di raccolta generici consiste nel derivare dalle classi o . Queste classi implementano le interfacce non generiche e pertanto includono il supporto previsto per le raccolte XAML nell'implementazione di base.

## <a name="read-only-collections-and-initialization-logic"></a>Raccolte di sola lettura e logica di inizializzazioneRead-Only Collections and Initialization Logic

Nella programmazione .NET, è un modello di progettazione comune per rendere qualsiasi proprietà che contiene un valore di una raccolta come raccolta di sola lettura. Questo modello consente all'istanza proprietaria della proprietà della raccolta di controllare meglio ciò che accade alla raccolta. In particolare, il modello impedisce la sostituzione accidentale dell'intera raccolta preesistente impostando la proprietà . In questo modello, qualsiasi accesso alla raccolta da parte dei chiamanti deve invece essere consentito chiamando metodi <xref:System.Collections.IList>o proprietà come supportato dal tipo di raccolta e/o dalle interfacce di raccolta pertinenti, ad esempio .

L'utilizzo di questo modello implica che qualsiasi classe che espone una proprietà della raccolta di sola lettura deve prima inizializzare tale proprietà per contenere una raccolta vuota. In genere l'inizializzazione viene eseguita come parte del comportamento di costruzione per la classe. Per essere utile per XAML, è importante che tale logica è sempre referenziata dal costruttore senza parametri, perché XAML chiama in genere il costruttore senza parametri prima di elaborare le proprietà (proprietà di raccolta o in altro modo).

## <a name="xaml-type-system-support-and-collections"></a>Supporto e raccolte del sistema di tipi XAMLXAML Type System Support and Collections

Oltre ai meccanismi di base dell'analisi XAML e del popolamento o della serializzazione delle proprietà delle raccolte, il sistema di tipi XAML implementato nei servizi XAML di .NET include diverse funzionalità di progettazione relative alle raccolte in XAML.

1. <xref:System.Xaml.XamlType.IsCollection%2A>restituisce true se il tipo XAML è supportato da un tipo che fornisce supporto per la raccolta XAML.

2. <xref:System.Xaml.XamlType.IsDictionary%2A>e <xref:System.Xaml.XamlType.IsArray%2A> può identificare ulteriormente la modalità di raccolta supportata dal tipo XAML. Per i processori XAML personalizzati basati sui servizi XAML di .NET e sul sistema di tipi XAML, ma non basati sulle implementazioni esistenti, <xref:System.Xaml.XamlWriter> potrebbe essere necessario sapere quale modalità di raccolta viene usata per sapere quale metodo richiamare per l'elaborazione della raccolta.

3. Ognuno dei valori di proprietà precedenti è <xref:System.Xaml.XamlType.LookupCollectionKind%2A> potenzialmente influenzato da override di su un tipo XAML.
