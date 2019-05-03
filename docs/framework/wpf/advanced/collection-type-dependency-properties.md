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
ms.openlocfilehash: 9ce0b70bfdd70b47857167ff14e62ed2bbda569d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62010696"
---
# <a name="collection-type-dependency-properties"></a>Proprietà di dipendenza di tipo raccolta
Questo argomento include linee guida e modelli consigliati per l'implementazione di una proprietà di dipendenza in cui la proprietà è di tipo raccolta.  

<a name="implementing"></a>   
## <a name="implementing-a-collection-type-dependency-property"></a>Implementazione di una proprietà di dipendenza di tipo raccolta  
 Per una proprietà di dipendenza in generale, il modello di implementazione è seguire è che si definisce una [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] wrapper della proprietà, in cui tale proprietà è supportata da un <xref:System.Windows.DependencyProperty> identificatore piuttosto che un campo o altro costrutto. Questo stesso modello viene seguito quando si implementa una proprietà di tipo raccolta. Tuttavia, una proprietà di tipo raccolta introduce alcune complessità, per il modello ogni volta che il tipo di contenuto all'interno della raccolta è a sua volta un <xref:System.Windows.DependencyObject> o <xref:System.Windows.Freezable> classe derivata.  
  
<a name="initializing"></a>   
## <a name="initializing-the-collection-beyond-the-default-value"></a>Inizializzazione della raccolta oltre il valore predefinito  
 Quando si crea una proprietà di dipendenza, non si specifica il valore predefinito della proprietà come valore iniziale del campo. Al contrario, viene specificato il valore predefinito tramite i metadati della proprietà di dipendenza. Se la proprietà è un tipo di riferimento, il valore predefinito specificato nei metadati della proprietà di dipendenza non è un valore predefinito per istanza, ma un valore predefinito che viene applicato a tutte le istanze del tipo. Pertanto, è necessario prestare attenzione a non usare la singola raccolta statica definita dai metadati della proprietà della raccolta come valore di lavoro predefinito per le istanze del tipo appena create. È invece necessario assicurarsi di impostare deliberatamente il valore della raccolta su un'unica raccolta (istanza), come parte della logica del costruttore di classi. In caso contrario, verrà creata una classe Singleton non intenzionale.  
  
 Si osservi l'esempio riportato di seguito. La sezione seguente dell'esempio descrive la definizione di una classe `Aquarium`. La classe definisce le proprietà di dipendenza di tipo raccolta `AquariumObjects`, che usa il tipo generico <xref:System.Collections.Generic.List%601> tipo con un <xref:System.Windows.FrameworkElement> vincolo di tipo. Nel <xref:System.Windows.DependencyProperty.Register%28System.String%2CSystem.Type%2CSystem.Type%2CSystem.Windows.PropertyMetadata%29> chiamata per la proprietà di dipendenza, i metadati stabilisce che il valore predefinito per un nuovo elemento generico <xref:System.Collections.Generic.List%601>.  
  
 [!code-csharp[PropertiesOvwSupport2#CollectionProblemDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport2/CSharp/page.xaml.cs#collectionproblemdefinition)]
 [!code-vb[PropertiesOvwSupport2#CollectionProblemDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport2/visualbasic/page.xaml.vb#collectionproblemdefinition)]  
  
 Tuttavia, se si lascia inalterato il codice, quel singolo valore predefinito dell'elenco viene condiviso per tutte le istanze di `Aquarium`. Se si esegue il codice di test riportato di seguito, destinato a mostrare la modalità di creazione di due istanze di `Aquarium` separate e si aggiunge un singolo oggetto `Fish` diverso a ciascuna di esse, il risultato è sorprendente:  
  
 [!code-csharp[PropertiesOvwSupport#CollectionProblemTestCode](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml.cs#collectionproblemtestcode)]
 [!code-vb[PropertiesOvwSupport#CollectionProblemTestCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page4.xaml.vb#collectionproblemtestcode)]  
  
 Invece di contenere un solo elemento, ogni raccolta ne contiene due. Questa situazione si verifica in quanto ciascun oggetto `Aquarium` ha aggiunto il proprio oggetto `Fish` alla raccolta dei valori predefiniti, generata da una singola chiamata al costruttore nei metadati e pertanto condivisa tra tutte le istanze. Si tratta di una situazione quasi mai auspicabile.  
  
 Per risolvere questo problema, è necessario reimpostare il valore della proprietà di dipendenza della raccolta su un'unica istanza, come parte della chiamata al costruttore di classe. Poiché la proprietà è una proprietà di dipendenza di sola lettura, si utilizza il <xref:System.Windows.DependencyObject.SetValue%28System.Windows.DependencyPropertyKey%2CSystem.Object%29> metodo impostarla, utilizzando il <xref:System.Windows.DependencyPropertyKey> che è accessibile solo all'interno della classe.  
  
 [!code-csharp[PropertiesOvwSupport#CollectionProblemCtor](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml.cs#collectionproblemctor)]
 [!code-vb[PropertiesOvwSupport#CollectionProblemCtor](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page4.xaml.vb#collectionproblemctor)]  
  
 A questo punto, se si esegue nuovamente questo stesso codice di test, è possibile ottenere i risultati previsti, in cui ciascun oggetto `Aquarium` supporta la propria raccolta univoca.  
  
 Se si sceglie una proprietà della raccolta con possibilità di accesso in lettura/scrittura, questo modello presenta una piccola variazione. In tal caso, è possibile chiamare la funzione di accesso set pubblica del costruttore per eseguire l'inizializzazione, che esegue la chiamata della firma non chiave della <xref:System.Windows.DependencyObject.SetValue%28System.Windows.DependencyProperty%2CSystem.Object%29> all'interno del wrapper impostato, con una pubblica <xref:System.Windows.DependencyProperty> identificatore.  
  
## <a name="reporting-binding-value-changes-from-collection-properties"></a>Segnalazione di modifiche dei valori di binding nelle proprietà della raccolta  
 Una proprietà della raccolta che costituisce essa stessa una proprietà di dipendenza non segnala automaticamente le modifiche per le relative sottoproprietà. La creazione di binding all'interno di una raccolta può impedire al binding di segnalare le modifiche, invalidando in tal modo alcuni scenari di data binding. Tuttavia, se si usa il tipo di raccolta <xref:System.Windows.FreezableCollection%601> come tipo di raccolta, quindi modifiche della sottoproprietà apportate agli elementi contenuti nella raccolta vengono segnalate correttamente e l'associazione funziona come previsto.  
  
 Per abilitare il binding di sottoproprietà in una raccolta di oggetti di dipendenza, creare la proprietà della raccolta come tipo <xref:System.Windows.FreezableCollection%601>, con un vincolo di tipo per la raccolta a qualsiasi <xref:System.Windows.DependencyObject> classe derivata.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.FreezableCollection%601>
- [Classi XAML e personalizzate per WPF](xaml-and-custom-classes-for-wpf.md)
- [Panoramica sul data binding](../data/data-binding-overview.md)
- [Panoramica sulle proprietà di dipendenza](dependency-properties-overview.md)
- [Proprietà di dipendenza personalizzate](custom-dependency-properties.md)
- [Metadati delle proprietà di dipendenza](dependency-property-metadata.md)
