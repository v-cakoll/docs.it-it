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
ms.openlocfilehash: b7f0954158988db107feb4a6c51ba81d5db11dcb
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/27/2020
ms.locfileid: "82071542"
---
# <a name="xxdata-intrinsic-xaml-type"></a>Tipo XAML intrinseco x:XData
Consente il posizionamento di isole di dati XML all'interno di una produzione XAML. Gli elementi `x:XData` XML all'interno non devono essere considerati dai processori XAML come se facessero parte dello spazio dei nomi XAML predefinito che agisce o di qualsiasi altro spazio dei nomi XAML. `x:XData`può contenere codice XML arbitrario ben formato.

## <a name="xaml-object-element-usage"></a>Utilizzo della sintassi XAML per gli elementi oggetto

```xaml
<x:XData>
  <elementDataRoot>
    [elementData]
  </elementDataRoot>
</x:XData>
```

## <a name="xaml-values"></a>Valori XAML

|||
|-|-|
|`elementDataRoot`|Singolo elemento radice dell'isola di dati racchiusa. Per la maggior parte dei consumer, XML che non dispone di una singola radice è considerato non valido. In particolare, è necessaria una `x:XData` singola radice se l'oggetto è inteso come origine dati XML per WPFWPF o molte altre tecnologie che utilizzano origini XML per l'associazione dati.|
|`[elementData]`|Facoltativa. XML che rappresenta i dati XML. Qualsiasi numero di elementi può essere contenuto come dati dell'elemento e gli elementi annidati possono essere contenuti in altri elementi; tuttavia, si applicano le regole generali di XML.|

## <a name="remarks"></a>Osservazioni

Gli elementi XML `x:XData` all'interno di un oggetto possono dichiarare nuovamente tutti i possibili spazi dei nomi e prefissi del codice XMLDOM contenitore all'interno dei dati.

L'accesso a livello `x:XData` di codice ai dati XML e <xref:System.Windows.Markup.XData> al tipo XAML intrinseco è possibile nei servizi XAML .NET tramite la classe .

## <a name="wpf-usage-notes"></a>Note sull'utilizzo di WPF

L'oggetto `x:XData` viene utilizzato principalmente come <xref:System.Windows.Data.XmlDataProvider>oggetto figlio di un oggetto , <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> o in alternativa, come l'oggetto figlio della proprietà (in XAML, questo è in genere espresso nella sintassi degli elementi proprietà).

I dati devono in genere ridefinire lo spazio dei nomi XML di base all'interno dell'isola di dati in modo che sia un nuovo spazio dei nomi XML predefinito (impostato su una stringa vuota). Questa operazione è più semplice <xref:System.Windows.Data.Binding.XPath%2A> per le isole di dati semplici perché le espressioni utilizzate per fare riferimento e associare ai dati possono evitare l'inclusione di prefissi. Le isole di dati più complesse potrebbero definire più prefissi per i dati e usare un prefisso specifico per lo spazio dei nomi XML nella radice. In questo caso, tutti i <xref:System.Windows.Data.Binding.XPath%2A> riferimenti alle espressioni devono includere il prefisso appropriato mappato allo spazio dei nomi. Per ulteriori informazioni, vedere [Cenni preliminari sull'associazione dati](../data/data-binding-overview.md).

Tecnicamente, `x:XData` può essere utilizzato come contenuto <xref:System.Xml.Serialization.IXmlSerializable>di qualsiasi proprietà di tipo . Tuttavia, <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> è l'unica attuazione di primo piano.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Data.XmlDataProvider>
- [Cenni preliminari sull'associazione dati](../data/data-binding-overview.md)
- [Associazione dell'estensione di markup](../../framework/wpf/advanced/binding-markup-extension.md)
