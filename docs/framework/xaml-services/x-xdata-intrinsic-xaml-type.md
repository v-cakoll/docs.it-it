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
ms.openlocfilehash: c5f729837b9bb52ca7d232ca66b58e283a2bcefc
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053703"
---
# <a name="xxdata-intrinsic-xaml-type"></a><span data-ttu-id="40b81-102">Tipo XAML intrinseco x:XData</span><span class="sxs-lookup"><span data-stu-id="40b81-102">x:XData Intrinsic XAML Type</span></span>
<span data-ttu-id="40b81-103">Consente di posizionare le isole di dati XML all'interno di una produzione XAML.</span><span class="sxs-lookup"><span data-stu-id="40b81-103">Enables placement of XML data islands within a XAML production.</span></span> <span data-ttu-id="40b81-104">Gli elementi XML `x:XData` all'interno di non devono essere considerati da processori XAML come se facessero parte dello spazio dei nomi XAML predefinito di azione o di qualsiasi altro spazio dei nomi XAML.</span><span class="sxs-lookup"><span data-stu-id="40b81-104">XML elements within `x:XData` should not be treated by XAML processors as if they are a part of the acting default XAML namespace or any other XAML namespace.</span></span> <span data-ttu-id="40b81-105">`x:XData`può contenere XML ben formato arbitrario.</span><span class="sxs-lookup"><span data-stu-id="40b81-105">`x:XData` can contain arbitrary well-formed XML.</span></span>  
  
## <a name="xaml-object-element-usage"></a><span data-ttu-id="40b81-106">Utilizzo della sintassi XAML per gli elementi oggetto</span><span class="sxs-lookup"><span data-stu-id="40b81-106">XAML Object Element Usage</span></span>  
  
```xaml  
<x:XData>  
  <elementDataRoot>  
    [elementData]  
  </elementDataRoot>  
</x:XData>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="40b81-107">Valori XAML</span><span class="sxs-lookup"><span data-stu-id="40b81-107">XAML Values</span></span>  
  
|||  
|-|-|  
|`elementDataRoot`|<span data-ttu-id="40b81-108">Singolo elemento radice dell'isola di dati racchiusi.</span><span class="sxs-lookup"><span data-stu-id="40b81-108">The single root element of the enclosed data island.</span></span> <span data-ttu-id="40b81-109">Per la maggior parte degli utenti finali, il codice XML che non dispone di una singola radice viene considerato non valido.</span><span class="sxs-lookup"><span data-stu-id="40b81-109">For most eventual consumers, XML that does not have a single root is considered invalid.</span></span> <span data-ttu-id="40b81-110">In particolare, è necessaria una singola radice se `x:XData` è destinato a un'origine dati XML per WPF o a molte altre tecnologie che utilizzano origini XML per data binding.</span><span class="sxs-lookup"><span data-stu-id="40b81-110">In particular, a single root is required if the `x:XData` is intended as an XML data source for WPF or many other technologies that use XML sources for data binding.</span></span>|  
|`[elementData]`|<span data-ttu-id="40b81-111">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="40b81-111">Optional.</span></span> <span data-ttu-id="40b81-112">XML che rappresenta i dati XML.</span><span class="sxs-lookup"><span data-stu-id="40b81-112">XML that represents the XML data.</span></span> <span data-ttu-id="40b81-113">Un numero qualsiasi di elementi può essere contenuto come dati di elemento e gli elementi annidati possono essere contenuti in altri elementi; Tuttavia, vengono applicate le regole generali di XML.</span><span class="sxs-lookup"><span data-stu-id="40b81-113">Any number of elements can be contained as element data and nested elements can be contained in other elements; however, the general rules of XML apply.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="40b81-114">Note</span><span class="sxs-lookup"><span data-stu-id="40b81-114">Remarks</span></span>  
 <span data-ttu-id="40b81-115">Gli elementi XML all'interno `x:XData` di un oggetto possono dichiarare nuovamente tutti gli spazi dei nomi e i prefissi della classe che lo contiene XMLDOM all'interno dei dati.</span><span class="sxs-lookup"><span data-stu-id="40b81-115">The XML elements within an `x:XData` object can re-declare all possible namespaces and prefixes of the containing XMLDOM within the data.</span></span>  
  
 <span data-ttu-id="40b81-116">L'accesso a livello di codice ai `x:XData` dati XML e al tipo XAML intrinseco è possibile in <xref:System.Windows.Markup.XData> .NET Framework servizi XAML tramite la classe.</span><span class="sxs-lookup"><span data-stu-id="40b81-116">Programmatic access to XML data and the `x:XData` intrinsic XAML type is possible in .NET Framework XAML Services through the <xref:System.Windows.Markup.XData> class.</span></span>  
  
## <a name="wpf-usage-notes"></a><span data-ttu-id="40b81-117">Note sull'utilizzo di WPF</span><span class="sxs-lookup"><span data-stu-id="40b81-117">WPF Usage Notes</span></span>  
 <span data-ttu-id="40b81-118">L' `x:XData` oggetto viene principalmente usato come oggetto figlio di un <xref:System.Windows.Data.XmlDataProvider>oggetto o, in alternativa, come oggetto figlio della <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> proprietà (in XAML, questo viene in genere espresso nella sintassi dell'elemento Property).</span><span class="sxs-lookup"><span data-stu-id="40b81-118">The `x:XData` object is primarily used as a child object of an <xref:System.Windows.Data.XmlDataProvider>, or alternatively, as the child object of the <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> property (in XAML, this is typically expressed in property element syntax).</span></span>  
  
 <span data-ttu-id="40b81-119">I dati in genere ridefiniscono lo spazio dei nomi XML di base all'interno dell'isola di dati in modo che sia un nuovo spazio dei nomi XML predefinito (impostato su una stringa vuota).</span><span class="sxs-lookup"><span data-stu-id="40b81-119">The data should typically redefine the base XML namespace within the data island to be a new default XML namespace (set to an empty string).</span></span> <span data-ttu-id="40b81-120">Questa operazione è più semplice per le isole dati <xref:System.Windows.Data.Binding.XPath%2A> semplici perché le espressioni usate per fare riferimento ai dati e associarle possono evitare di includere i prefissi.</span><span class="sxs-lookup"><span data-stu-id="40b81-120">This is easiest for simple data islands because the <xref:System.Windows.Data.Binding.XPath%2A> expressions that are used to reference and bind to the data can avoid inclusion of prefixes.</span></span> <span data-ttu-id="40b81-121">Le isole dati più complesse potrebbero definire più prefissi per i dati e usare un prefisso specifico per lo spazio dei nomi XML nella radice.</span><span class="sxs-lookup"><span data-stu-id="40b81-121">More complex data islands might define multiple prefixes for the data and use a specific prefix for the XML namespace at the root.</span></span> <span data-ttu-id="40b81-122">In questo caso, tutti <xref:System.Windows.Data.Binding.XPath%2A> i riferimenti all'espressione devono includere il prefisso mappato allo spazio dei nomi appropriato.</span><span class="sxs-lookup"><span data-stu-id="40b81-122">In this case, all <xref:System.Windows.Data.Binding.XPath%2A> expression references should include the appropriate namespace-mapped prefix.</span></span> <span data-ttu-id="40b81-123">Per altre informazioni, vedere la [panoramica del data binding](../wpf/data/data-binding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="40b81-123">For more information, see [Data Binding Overview](../wpf/data/data-binding-overview.md).</span></span>  
  
 <span data-ttu-id="40b81-124">Tecnicamente, `x:XData` può essere usato come contenuto di qualsiasi proprietà di tipo <xref:System.Xml.Serialization.IXmlSerializable>.</span><span class="sxs-lookup"><span data-stu-id="40b81-124">Technically, `x:XData` can be used as the content of any property of type <xref:System.Xml.Serialization.IXmlSerializable>.</span></span> <span data-ttu-id="40b81-125">Tuttavia, <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> è l'unica implementazione prominente.</span><span class="sxs-lookup"><span data-stu-id="40b81-125">However, <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> is the only prominent implementation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40b81-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="40b81-126">See also</span></span>

- <xref:System.Windows.Data.XmlDataProvider>
- [<span data-ttu-id="40b81-127">Panoramica sul data binding</span><span class="sxs-lookup"><span data-stu-id="40b81-127">Data Binding Overview</span></span>](../wpf/data/data-binding-overview.md)
- [<span data-ttu-id="40b81-128">Estensione di markup Binding</span><span class="sxs-lookup"><span data-stu-id="40b81-128">Binding Markup Extension</span></span>](../wpf/advanced/binding-markup-extension.md)
