---
title: Raccolte e tipi di raccolte per XAML
ms.date: 03/30/2017
ms.assetid: 58f8e7c6-9a41-4f25-8551-c042f1315baa
ms.openlocfilehash: 63f6346837f77dbdbdcb4a90ec5af725be69ee02
ms.sourcegitcommit: 30a83efb57c468da74e9e218de26cf88d3254597
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/20/2019
ms.locfileid: "68364332"
---
# <a name="collections-and-collection-types-for-xaml"></a>Raccolte e tipi di raccolte per XAML

In questo argomento viene descritto come definire le proprietà dei tipi destinati a supportare una raccolta e per supportare la sintassi XAML per la creazione di un'istanza di elementi della raccolta come elementi figlio di un elemento oggetto o elemento proprietà padre.

## <a name="xaml-collection-concepts"></a>Concetti relativi alla raccolta XAML

Dal punto di vista concettuale, qualsiasi relazione in XAML in cui sono presenti più elementi figlio all'interno dell'ambito di un elemento oggetto XAML o di una proprietà XAML deve essere implementata come raccolta. Tale raccolta deve essere associata a una particolare proprietà XAML del tipo XAML che rappresenta l'elemento padre in quella relazione. La proprietà deve essere una raccolta perché un processore XAML prevede di assegnare a ogni elemento del markup un elemento appena aggiunto della proprietà della raccolta sottostante.

A livello di linguaggio XAML, i requisiti esatti del supporto per la raccolta non sono completamente definiti. Il concetto che una raccolta può essere un elenco o un dizionario (ma non entrambi) viene definito a livello di linguaggio XAML, ma i tipi di supporto rappresentano elenchi o dizionari non sono definiti dal linguaggio XAML.

Nei servizi XAML .NET Framework il concetto di supporto della raccolta XAML è definito in modo più chiaro in termini di .NET Framework tipi di supporto. In particolare, il supporto XAML per le raccolte si basa su diversi concetti e API .NET Framework utilizzati per elenchi e dizionari in generale .NET Framework programmazione.

1. L' <xref:System.Collections.IList> interfaccia indica una raccolta di elenchi.

2. L' <xref:System.Collections.IDictionary> interfaccia indica una raccolta di dizionari.

3. <xref:System.Array>rappresenta una matrice e una matrice supporta <xref:System.Collections.IList> i metodi.

In ognuno di questi concetti di raccolta, un processore XAML dei servizi XAML .NET Framework prevede di chiamare `Add` il metodo su un'istanza specifica del tipo della proprietà della raccolta. In alternativa, in uno scenario di serializzazione, un processore XAML produce istanze discrete di tipo XAML per ogni elemento trovato nell'elenco, nel dizionario o nella matrice in base al concetto specifico di "Items" della raccolta. Sono: <xref:System.Collections.IList.Item%2A> ; esplicito <xref:System.Array.System%23Collections%23IList%23Item%2A> per <xref:System.Array>. <xref:System.Collections.IDictionary.Item%2A>

## <a name="generic-collections"></a>Raccolte generiche

Le raccolte generiche possono essere utili per la programmazione .NET Framework generale e possono essere usate anche per le proprietà della raccolta XAML. Tuttavia <xref:System.Collections.Generic.IList%601> , le interfacce generiche e <xref:System.Collections.Generic.IDictionary%602> non sono identificate da .NET Framework processori XAML dei servizi XAML come equivalenti all'oggetto <xref:System.Collections.IList> o <xref:System.Collections.IDictionary>non generico. Anziché implementare le interfacce, un approccio consigliato per i tipi di proprietà della raccolta generica consiste nel derivare <xref:System.Collections.Generic.Dictionary%602>dalle classi <xref:System.Collections.Generic.List%601> o. Queste classi implementano le interfacce non generiche e quindi includono il supporto previsto per le raccolte XAML nell'implementazione di base.

## <a name="read-only-collections-and-initialization-logic"></a>Raccolte di sola lettura e logica di inizializzazione

In .NET Framework programmazione, si tratta di un modello di progettazione comune per rendere qualsiasi proprietà che contenga un valore di una raccolta come raccolta di sola lettura. Questo modello consente all'istanza proprietaria della proprietà della raccolta di controllare meglio cosa accade alla raccolta. In particolare, il modello impedisce la sostituzione accidentale dell'intera raccolta preesistente impostando la proprietà. In questo modello, qualsiasi accesso alla raccolta da parte dei chiamanti deve essere eseguito chiamando metodi o proprietà come supportato dal tipo di raccolta e/o le interfacce di raccolta pertinenti, ad <xref:System.Collections.IList>esempio.

L'utilizzo di questo modello implica che qualsiasi classe che espone una proprietà di raccolta di sola lettura deve innanzitutto inizializzare tale proprietà in modo che contenga una raccolta vuota. In genere l'inizializzazione viene eseguita come parte del comportamento di costruzione per la classe. Per essere utile per XAML, è importante che tale logica faccia sempre riferimento al costruttore senza parametri, perché XAML chiama in genere il costruttore senza parametri prima di elaborare le proprietà (proprietà della raccolta o in caso contrario).

## <a name="xaml-type-system-support-and-collections"></a>Raccolte e supporto del sistema di tipi XAML

Oltre ai meccanismi di base per l'analisi di XAML e il popolamento o la serializzazione delle proprietà della raccolta, il sistema di tipi XAML implementato in .NET Framework servizi XAML include diverse funzionalità di progettazione relative alle raccolte in XAML.

1. <xref:System.Xaml.XamlType.IsCollection%2A>Restituisce true se il tipo XAML è supportato da un tipo che fornisce il supporto per la raccolta XAML.

2. <xref:System.Xaml.XamlType.IsDictionary%2A>e <xref:System.Xaml.XamlType.IsArray%2A> possono identificare ulteriormente la modalità di raccolta supportata dal tipo XAML. Per i processori XAML personalizzati basati sui servizi XAML .NET Framework e sul sistema di tipi XAML ma non sulla base delle <xref:System.Xaml.XamlWriter> implementazioni esistenti, è possibile sapere quale modalità di raccolta viene utilizzata per conoscere il metodo da richiamare elaborazione della raccolta.

3. Ognuno dei valori di proprietà precedenti è potenzialmente influenzato dalle sostituzioni <xref:System.Xaml.XamlType.LookupCollectionKind%2A> di in un tipo XAML.
