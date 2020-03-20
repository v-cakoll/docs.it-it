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
ms.openlocfilehash: e783ce4b95b52b86671181dfe4b316d4b91d8fc6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141537"
---
# <a name="collection-type-dependency-properties"></a>Proprietà di dipendenza di tipo raccolta
Questo argomento include linee guida e modelli consigliati per l'implementazione di una proprietà di dipendenza in cui la proprietà è di tipo raccolta.  

<a name="implementing"></a>
## <a name="implementing-a-collection-type-dependency-property"></a>Implementazione di una proprietà di dipendenza di tipo raccolta  
 Per una proprietà di dipendenza in generale, il modello di implementazione seguito è che <xref:System.Windows.DependencyProperty> si definisce un wrapper di proprietà CLR, in cui tale proprietà è supportata da un identificatore anziché da un campo o un altro costrutto. Questo stesso modello viene seguito quando si implementa una proprietà di tipo raccolta. Tuttavia, una proprietà di tipo raccolta introduce una certa complessità al modello ogni <xref:System.Windows.DependencyObject> <xref:System.Windows.Freezable> volta che il tipo contenuto all'interno della raccolta è esso stesso una classe o una classe derivata.  
  
<a name="initializing"></a>
## <a name="initializing-the-collection-beyond-the-default-value"></a>Inizializzazione della raccolta oltre il valore predefinito  
 Quando si crea una proprietà di dipendenza, non si specifica il valore predefinito della proprietà come valore iniziale del campo. Al contrario, viene specificato il valore predefinito tramite i metadati della proprietà di dipendenza. Se la proprietà è un tipo di riferimento, il valore predefinito specificato nei metadati della proprietà di dipendenza non è un valore predefinito per istanza, ma un valore predefinito che viene applicato a tutte le istanze del tipo. Pertanto, è necessario prestare attenzione a non usare la singola raccolta statica definita dai metadati della proprietà della raccolta come valore di lavoro predefinito per le istanze del tipo appena create. È invece necessario assicurarsi di impostare deliberatamente il valore della raccolta su un'unica raccolta (istanza), come parte della logica del costruttore di classi. In caso contrario, verrà creata una classe Singleton non intenzionale.  
  
 Si consideri l'esempio seguente. Nella sezione seguente dell'esempio viene `Aquarium`illustrata la definizione per una classe , che contiene un difetto con il valore predefinito. La classe definisce la proprietà `AquariumObjects`di dipendenza <xref:System.Collections.Generic.List%601> del tipo <xref:System.Windows.FrameworkElement> di raccolta , che utilizza il tipo generico con un vincolo di tipo. Nella <xref:System.Windows.DependencyProperty.Register%28System.String%2CSystem.Type%2CSystem.Type%2CSystem.Windows.PropertyMetadata%29> chiamata per la proprietà di dipendenza, i metadati stabiliscono <xref:System.Collections.Generic.List%601>il valore predefinito come un nuovo oggetto generico.

> [!WARNING]
> Il codice seguente non si comporta correttamente.

 [!code-csharp[PropertiesOvwSupport2#CollectionProblemDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport2/CSharp/page.xaml.cs#collectionproblemdefinition)]
 [!code-vb[PropertiesOvwSupport2#CollectionProblemDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport2/visualbasic/page.xaml.vb#collectionproblemdefinition)]  
  
 Tuttavia, se si lascia inalterato il codice, quel singolo valore predefinito dell'elenco viene condiviso per tutte le istanze di `Aquarium`. Se si esegue il codice di test riportato di seguito, destinato a mostrare la modalità di creazione di due istanze di `Aquarium` separate e si aggiunge un singolo oggetto `Fish` diverso a ciascuna di esse, il risultato è sorprendente:  
  
 [!code-csharp[PropertiesOvwSupport#CollectionProblemTestCode](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml.cs#collectionproblemtestcode)]
 [!code-vb[PropertiesOvwSupport#CollectionProblemTestCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page4.xaml.vb#collectionproblemtestcode)]  
  
 Invece di contenere un solo elemento, ogni raccolta ne contiene due. Questa situazione si verifica in quanto ciascun oggetto `Aquarium` ha aggiunto il proprio oggetto `Fish` alla raccolta dei valori predefiniti, generata da una singola chiamata al costruttore nei metadati e pertanto condivisa tra tutte le istanze. Si tratta di una situazione quasi mai auspicabile.  
  
 Per risolvere questo problema, è necessario reimpostare il valore della proprietà di dipendenza della raccolta su un'unica istanza, come parte della chiamata al costruttore di classe. Poiché la proprietà è di sola lettura, <xref:System.Windows.DependencyObject.SetValue%28System.Windows.DependencyPropertyKey%2CSystem.Object%29> si usa il <xref:System.Windows.DependencyPropertyKey> metodo per impostarla, usando l'oggetto che è accessibile solo all'interno della classe.  
  
 [!code-csharp[PropertiesOvwSupport#CollectionProblemCtor](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml.cs#collectionproblemctor)]
 [!code-vb[PropertiesOvwSupport#CollectionProblemCtor](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page4.xaml.vb#collectionproblemctor)]  
  
 A questo punto, se si esegue nuovamente questo stesso codice di test, è possibile ottenere i risultati previsti, in cui ciascun oggetto `Aquarium` supporta la propria raccolta univoca.  
  
 Se si sceglie una proprietà della raccolta con possibilità di accesso in lettura/scrittura, questo modello presenta una piccola variazione. In tal caso, è possibile chiamare la funzione di accesso set pubblica dal costruttore <xref:System.Windows.DependencyObject.SetValue%28System.Windows.DependencyProperty%2CSystem.Object%29> per eseguire l'inizializzazione, che chiamerebbe comunque la firma non chiave di all'interno del wrapper di set, utilizzando un identificatore pubblico. <xref:System.Windows.DependencyProperty>  
  
## <a name="reporting-binding-value-changes-from-collection-properties"></a>Segnalazione di modifiche dei valori di binding nelle proprietà della raccolta  
 Una proprietà della raccolta che costituisce essa stessa una proprietà di dipendenza non segnala automaticamente le modifiche per le relative sottoproprietà. La creazione di binding all'interno di una raccolta può impedire al binding di segnalare le modifiche, invalidando in tal modo alcuni scenari di data binding. Tuttavia, se si <xref:System.Windows.FreezableCollection%601> utilizza il tipo di raccolta come tipo di raccolta, le modifiche delle sottoproprietà agli elementi contenuti nella raccolta vengono segnalate correttamente e l'associazione funziona come previsto.  
  
 Per abilitare l'associazione di sottoproprietà in un <xref:System.Windows.FreezableCollection%601>insieme di oggetti di dipendenza, creare la proprietà dell'insieme come tipo , con un vincolo di tipo per tale raccolta a qualsiasi <xref:System.Windows.DependencyObject> classe derivata.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.FreezableCollection%601>
- [Classi XAML e personalizzate per WPF](xaml-and-custom-classes-for-wpf.md)
- [Cenni preliminari sull'associazione dati](../../../desktop-wpf/data/data-binding-overview.md)
- [Cenni preliminari sulle proprietà di dipendenza](dependency-properties-overview.md)
- [Proprietà di dipendenza personalizzate](custom-dependency-properties.md)
- [Metadati della proprietà di dipendenza](dependency-property-metadata.md)
