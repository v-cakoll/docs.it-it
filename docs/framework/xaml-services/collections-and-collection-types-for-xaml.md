---
title: Raccolte e tipi di raccolte per XAML
ms.date: 03/30/2017
ms.assetid: 58f8e7c6-9a41-4f25-8551-c042f1315baa
ms.openlocfilehash: 5605c97b13503e18e2f698f2a19f715663052b08
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33562976"
---
# <a name="collections-and-collection-types-for-xaml"></a>Raccolte e tipi di raccolte per XAML
In questo argomento viene descritto come definire le proprietà dei tipi che servono per supportare una raccolta e per supportare la sintassi XAML per creare un'istanza di elementi della raccolta come elementi figlio di un elemento oggetto padre o un elemento di proprietà.  
  
## <a name="xaml-collection-concepts"></a>Concetti di raccolta XAML  
 Concettualmente, tutte le relazioni nel codice XAML in cui sono presenti più elementi figlio all'interno dell'ambito di un elemento oggetto XAML o elemento proprietà XAML deve essere implementata come una raccolta. Tale raccolta deve essere associata a una proprietà XAML specifica del tipo XAML che rappresenta l'elemento padre nella relazione. La proprietà deve essere una raccolta perché un processore XAML prevede di assegnare a ogni elemento nel markup per un elemento appena aggiunto il supporto della proprietà di raccolta.  
  
 A livello di linguaggio XAML, i requisiti specifici di supporto delle raccolte non completamente definiti. Il concetto che può essere una raccolta di un elenco o un dizionario (ma non entrambi) è definito a livello di linguaggio XAML, ma i tipi di supporto rappresentano entrambi gli elenchi o dizionari non è definito dal linguaggio XAML.  
  
 Nei servizi XAML di .NET Framework, il concetto di supporto delle raccolte XAML viene definito in modo più chiaro in termini di tipi di supporto di .NET Framework. In particolare, il supporto XAML per raccolte si basa su diversi concetti di .NET Framework e le API che vengono utilizzate per elenchi e dizionari nella programmazione generale di .NET Framework.  
  
1.  Il <xref:System.Collections.IList> interfaccia indica una raccolta di elenchi.  
  
2.  Il <xref:System.Collections.IDictionary> interfaccia indica un insieme di dicionary.  
  
3.  <xref:System.Array> rappresenta una matrice e una matrice supporta <xref:System.Collections.IList> metodi.  
  
 In ognuno di questi concetti di raccolta, un processore XAML dei servizi XAML di .NET Framework prevede di chiamare il `Add` metodo in un'istanza specifica del tipo della proprietà di raccolta. In alternativa, in uno scenario di serializzazione, un processore XAML produce istanze di tipo XAML discrete per ogni elemento nell'elenco, dizionario o della matrice basata sul concetto di specifiche di ogni raccolta di "Elementi". Questi sono: <xref:System.Collections.IList.Item%2A>; <xref:System.Collections.IDictionary.Item%2A>; esplicita <xref:System.Array.System%23Collections%23IList%23Item%2A> per <xref:System.Array>.  
  
## <a name="generic-collections"></a>Raccolte generiche  
 Raccolte generiche possono essere utile per la programmazione generale di .NET Framework e utilizzabili per le proprietà di raccolta XAML. Tuttavia, il generico interfacce <xref:System.Collections.Generic.IList%601> e <xref:System.Collections.Generic.IDictionary%602> non sono identificate dai processori XAML dei servizi XAML di .NET Framework equivalenti al non generico <xref:System.Collections.IList> o <xref:System.Collections.IDictionary>. Anziché implementare le interfacce, un approccio consigliato per i tipi di proprietà di raccolta generica è derivano dalle classi <xref:System.Collections.Generic.List%601> o <xref:System.Collections.Generic.Dictionary%602>. Queste classi implementano le interfacce non generiche e pertanto includono il supporto previsto per le raccolte XAML nell'implementazione di base.  
  
## <a name="read-only-collections-and-initialization-logic"></a>Le raccolte di sola lettura e la logica di inizializzazione  
 In .NET Framework di programmazione, è un modello di progettazione comune per qualsiasi proprietà che contiene un valore di un insieme come una raccolta di sola lettura. Questo modello consente l'istanza che possiede la proprietà di raccolta per controllare meglio cosa accade alla raccolta... In particolare, il modello impedisce la sostituzione accidentale dell'intera raccolta di pre-esistente impostando la proprietà. In questo modello, qualsiasi accesso alla raccolta da parte dei chiamanti invece prevedere chiamando metodi o proprietà supportata dal tipo di raccolta e/o le interfacce di raccolta rilevanti, ad esempio <xref:System.Collections.IList>.  
  
 Mediante questo pattern implica che qualsiasi classe che espone una proprietà della raccolta di sola lettura prima di tutto necessario inizializzare tale proprietà per contenere una raccolta vuota. In genere l'inizializzazione viene eseguita come parte del comportamento della costruzione della classe. Per essere utile per XAML, è importante che tale logica viene sempre fatto riferimento dal costruttore predefinito, poiché XAML è in genere chiama il costruttore predefinito prima di elaborare le proprietà (proprietà della raccolta o in caso contrario).  
  
## <a name="xaml-type-system-support-and-collections"></a>Raccolte e supporto di sistema di tipo XAML  
 Oltre il meccanismo di base per l'analisi XAML e la compilazione o la serializzazione delle proprietà della raccolta, il sistema di tipi XAML implementati nei servizi XAML di .NET Framework include diverse funzionalità di progettazione relativi alle raccolte in XAML.  
  
1.  <xref:System.Xaml.XamlType.IsCollection%2A> Restituisce true se il tipo XAML viene eseguito da un tipo che fornisce supporto delle raccolte XAML.  
  
2.  <xref:System.Xaml.XamlType.IsDictionary%2A> e <xref:System.Xaml.XamlType.IsArray%2A> può identificare ulteriormente la modalità di raccolta supporta il tipo XAML. Per XAML personalizzato processori che si basano su servizi XAML di .NET Framework e il codice XAML, sistema di tipi ma non basato su esistente <xref:System.Xaml.XamlWriter> implementazioni di conoscere la modalità di raccolta utilizzata potrebbe essere necessario per sapere quale metodo da richiamare per elaborazione della raccolta.  
  
3.  Ognuno dei valori di proprietà precedente sono potenzialmente influenzate dalle sostituzioni di <xref:System.Xaml.XamlType.LookupCollectionKind%2A> su un tipo XAML.
