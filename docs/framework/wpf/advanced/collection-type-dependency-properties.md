---
title: Proprietà di dipendenza di tipo raccolta
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- properties [WPF], dependency
- properties [WPF], collection-type
- dependency properties [WPF]
- collection-type properties [WPF]
ms.assetid: 99f96a42-3ab7-4f64-a16b-2e10d654e97c
ms.openlocfilehash: dd268c0c132f4ecefe7b2336432442d9569ca38f
ms.sourcegitcommit: 24a4a8eb6d8cfe7b8549fb6d823076d7c697e0c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2019
ms.locfileid: "68401563"
---
# <a name="collection-type-dependency-properties"></a>Proprietà di dipendenza di tipo raccolta
Questo argomento include linee guida e modelli consigliati per l'implementazione di una proprietà di dipendenza in cui la proprietà è di tipo raccolta.  

<a name="implementing"></a>   
## <a name="implementing-a-collection-type-dependency-property"></a>Implementazione di una proprietà di dipendenza di tipo raccolta  
 Per una proprietà di dipendenza in generale, il modello di implementazione che segue è la definizione di un wrapper della proprietà CLR, in cui tale proprietà è supportata <xref:System.Windows.DependencyProperty> da un identificatore anziché da un campo o da un altro costrutto. Questo stesso modello viene seguito quando si implementa una proprietà di tipo raccolta. Tuttavia, una proprietà di tipo raccolta introduce una certa complessità al modello ogni volta che il tipo contenuto all'interno della raccolta è a <xref:System.Windows.DependencyObject> sua <xref:System.Windows.Freezable> volta una classe derivata o.  
  
<a name="initializing"></a>   
## <a name="initializing-the-collection-beyond-the-default-value"></a>Inizializzazione della raccolta oltre il valore predefinito  
 Quando si crea una proprietà di dipendenza, non si specifica il valore predefinito della proprietà come valore iniziale del campo. Al contrario, viene specificato il valore predefinito tramite i metadati della proprietà di dipendenza. Se la proprietà è un tipo di riferimento, il valore predefinito specificato nei metadati della proprietà di dipendenza non è un valore predefinito per istanza, ma un valore predefinito che viene applicato a tutte le istanze del tipo. Pertanto, è necessario prestare attenzione a non usare la singola raccolta statica definita dai metadati della proprietà della raccolta come valore di lavoro predefinito per le istanze del tipo appena create. È invece necessario assicurarsi di impostare deliberatamente il valore della raccolta su un'unica raccolta (istanza), come parte della logica del costruttore di classi. In caso contrario, verrà creata una classe Singleton non intenzionale.  
  
 Si osservi l'esempio riportato di seguito. La sezione seguente dell'esempio descrive la definizione di una classe `Aquarium`. La classe definisce la proprietà `AquariumObjects`di dipendenza del tipo di raccolta, che usa il tipo generico <xref:System.Collections.Generic.List%601> con un <xref:System.Windows.FrameworkElement> vincolo di tipo. Nella chiamata per la proprietà di dipendenza, i metadati stabiliscono il valore predefinito come nuovo generico <xref:System.Collections.Generic.List%601>. <xref:System.Windows.DependencyProperty.Register%28System.String%2CSystem.Type%2CSystem.Type%2CSystem.Windows.PropertyMetadata%29>  
  
 [!code-csharp[PropertiesOvwSupport2#CollectionProblemDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport2/CSharp/page.xaml.cs#collectionproblemdefinition)]
 [!code-vb[PropertiesOvwSupport2#CollectionProblemDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport2/visualbasic/page.xaml.vb#collectionproblemdefinition)]  
  
 Tuttavia, se si lascia inalterato il codice, quel singolo valore predefinito dell'elenco viene condiviso per tutte le istanze di `Aquarium`. Se si esegue il codice di test riportato di seguito, destinato a mostrare la modalità di creazione di due istanze di `Aquarium` separate e si aggiunge un singolo oggetto `Fish` diverso a ciascuna di esse, il risultato è sorprendente:  
  
 [!code-csharp[PropertiesOvwSupport#CollectionProblemTestCode](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml.cs#collectionproblemtestcode)]
 [!code-vb[PropertiesOvwSupport#CollectionProblemTestCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page4.xaml.vb#collectionproblemtestcode)]  
  
 Invece di contenere un solo elemento, ogni raccolta ne contiene due. Questa situazione si verifica in quanto ciascun oggetto `Aquarium` ha aggiunto il proprio oggetto `Fish` alla raccolta dei valori predefiniti, generata da una singola chiamata al costruttore nei metadati e pertanto condivisa tra tutte le istanze. Si tratta di una situazione quasi mai auspicabile.  
  
 Per risolvere questo problema, è necessario reimpostare il valore della proprietà di dipendenza della raccolta su un'unica istanza, come parte della chiamata al costruttore di classe. Poiché la proprietà è una proprietà di dipendenza di sola lettura, si usa <xref:System.Windows.DependencyObject.SetValue%28System.Windows.DependencyPropertyKey%2CSystem.Object%29> il metodo per impostarla, usando <xref:System.Windows.DependencyPropertyKey> l'oggetto che è accessibile solo all'interno della classe.  
  
 [!code-csharp[PropertiesOvwSupport#CollectionProblemCtor](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml.cs#collectionproblemctor)]
 [!code-vb[PropertiesOvwSupport#CollectionProblemCtor](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page4.xaml.vb#collectionproblemctor)]  
  
 A questo punto, se si esegue nuovamente questo stesso codice di test, è possibile ottenere i risultati previsti, in cui ciascun oggetto `Aquarium` supporta la propria raccolta univoca.  
  
 Se si sceglie una proprietà della raccolta con possibilità di accesso in lettura/scrittura, questo modello presenta una piccola variazione. In tal caso, è possibile chiamare la funzione di accesso set pubblica dal costruttore per eseguire l'inizializzazione, che chiamerebbe comunque la firma colonne <xref:System.Windows.DependencyObject.SetValue%28System.Windows.DependencyProperty%2CSystem.Object%29> di all'interno del wrapper del set, <xref:System.Windows.DependencyProperty> usando un identificatore pubblico.  
  
## <a name="reporting-binding-value-changes-from-collection-properties"></a>Segnalazione di modifiche dei valori di binding nelle proprietà della raccolta  
 Una proprietà della raccolta che costituisce essa stessa una proprietà di dipendenza non segnala automaticamente le modifiche per le relative sottoproprietà. La creazione di binding all'interno di una raccolta può impedire al binding di segnalare le modifiche, invalidando in tal modo alcuni scenari di data binding. Tuttavia, se si usa il tipo <xref:System.Windows.FreezableCollection%601> di raccolta come tipo di raccolta, le modifiche alle sottoproprietà degli elementi contenuti nella raccolta vengono segnalate correttamente e il binding funziona come previsto.  
  
 Per abilitare l'associazione di sottoproprietà in una raccolta di oggetti di dipendenza, creare la <xref:System.Windows.FreezableCollection%601>proprietà della raccolta come tipo, con un vincolo <xref:System.Windows.DependencyObject> di tipo per tale raccolta in una classe derivata.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.FreezableCollection%601>
- [Classi XAML e personalizzate per WPF](xaml-and-custom-classes-for-wpf.md)
- [Panoramica sul data binding](../data/data-binding-overview.md)
- [Panoramica sulle proprietà di dipendenza](dependency-properties-overview.md)
- [Proprietà di dipendenza personalizzate](custom-dependency-properties.md)
- [Metadati delle proprietà di dipendenza](dependency-property-metadata.md)
