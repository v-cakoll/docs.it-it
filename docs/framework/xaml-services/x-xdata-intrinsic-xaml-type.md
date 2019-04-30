---
title: Tipo XAML intrinseco x:XData
ms.date: 03/30/2017
f1_keywords:
- x:XData
- XData
- xXData
helpviewer_keywords:
- XAML [XAML Services], x:XData directive element
- XData in XAML [XAML Services]
- x:XData XAML directive element [XAML Services]
ms.assetid: 7ce209c2-621b-4977-b643-565f7e663534
ms.openlocfilehash: c8044bc341ded6ef7b03bbdf701e724654460d54
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61938827"
---
# <a name="xxdata-intrinsic-xaml-type"></a>Tipo XAML intrinseco x:XData
Consente il posizionamento di isole di dati XML all'interno di una produzione XAML. Gli elementi XML presenti `x:XData` non devono essere considerati dai processori XAML come se facessero parte di spazio dei nomi XAML predefinito attivo o qualsiasi altro spazio dei nomi XAML. `x:XData` può contenere codice XML ben formato arbitrario.  
  
## <a name="xaml-object-element-usage"></a>Utilizzo della sintassi XAML per gli elementi oggetto  
  
```  
<x:XData>  
  <elementDataRoot>  
    [elementData]  
  </elementDataRoot>  
</x:XData>  
```  
  
## <a name="xaml-values"></a>Valori XAML  
  
|||  
|-|-|  
|`elementDataRoot`|Il singolo elemento radice dell'isola di dati racchiusi. Per la maggior parte dei consumer finale, che non ha un solo nodo radice XML viene considerato non valido. In particolare, un solo nodo radice è necessaria se la `x:XData` è concepito come un'origine dati XML per molte altre tecnologie che utilizzano origini XML per il data binding o WPF.|  
|`[elementData]`|Facoltativo. File XML che rappresenta i dati XML. Qualsiasi numero di elementi può essere contenuto i dati dell'elemento e gli elementi annidati possono essere contenuti in altri elementi. Tuttavia, si applicano le regole generali di XML.|  
  
## <a name="remarks"></a>Note  
 Gli elementi XML all'interno di un `x:XData` oggetto possibile dichiarare di nuovo tutti i possibili degli spazi dei nomi e prefissi di XMLDOM all'interno dei dati.  
  
 Accesso programmatico a dati XML e il `x:XData` tipo XAML intrinseco viene possibile nei servizi XAML di .NET Framework tramite il <xref:System.Windows.Markup.XData> classe.  
  
## <a name="wpf-usage-notes"></a>Note sull'utilizzo WPF  
 Il `x:XData` oggetto viene utilizzato principalmente come un oggetto figlio di un <xref:System.Windows.Data.XmlDataProvider>, o in alternativa, l'oggetto figlio di <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> proprietà (in XAML, questo valore viene in genere espresso nella sintassi degli elementi di proprietà).  
  
 I dati in genere devono ridefinire lo spazio dei nomi XML di base all'interno dell'isola di dati da un nuovo spazio dei nomi XML predefinito (impostato su una stringa vuota). Ciò è più semplice per le isole di dati semplici in quanto il <xref:System.Windows.Data.Binding.XPath%2A> espressioni che vengono usate per fare riferimento e associare ai dati possono evitare di includere i prefissi. Isole di dati più complesse potrebbero definire più prefissi per i dati e usare un prefisso specifico per lo spazio dei nomi XML in corrispondenza della radice. In questo caso, tutti <xref:System.Windows.Data.Binding.XPath%2A> espressione che fa riferimento deve includere il prefisso di mapping dello spazio dei nomi appropriato. Per altre informazioni, vedere la [panoramica del data binding](../wpf/data/data-binding-overview.md).  
  
 Tecnicamente `x:XData` può essere utilizzato come il contenuto di qualsiasi proprietà di tipo <xref:System.Xml.Serialization.IXmlSerializable>. Tuttavia, <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> è l'unica implementazione rilevante.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Data.XmlDataProvider>
- [Panoramica sul data binding](../wpf/data/data-binding-overview.md)
- [Estensione di markup Binding](../wpf/advanced/binding-markup-extension.md)
