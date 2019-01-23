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
ms.openlocfilehash: 8b951b33242fa7e17a02133adb8fed4ce638e51e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54498047"
---
# <a name="xxdata-intrinsic-xaml-type"></a><span data-ttu-id="7dc17-102">Tipo XAML intrinseco x:XData</span><span class="sxs-lookup"><span data-stu-id="7dc17-102">x:XData Intrinsic XAML Type</span></span>
<span data-ttu-id="7dc17-103">Consente il posizionamento di isole di dati XML all'interno di una produzione XAML.</span><span class="sxs-lookup"><span data-stu-id="7dc17-103">Enables placement of XML data islands within a XAML production.</span></span> <span data-ttu-id="7dc17-104">Gli elementi XML presenti `x:XData` non devono essere considerati dai processori XAML come se facessero parte di spazio dei nomi XAML predefinito attivo o qualsiasi altro spazio dei nomi XAML.</span><span class="sxs-lookup"><span data-stu-id="7dc17-104">XML elements within `x:XData` should not be treated by XAML processors as if they are a part of the acting default XAML namespace or any other XAML namespace.</span></span> <span data-ttu-id="7dc17-105">`x:XData` può contenere codice XML ben formato arbitrario.</span><span class="sxs-lookup"><span data-stu-id="7dc17-105">`x:XData` can contain arbitrary well-formed XML.</span></span>  
  
## <a name="xaml-object-element-usage"></a><span data-ttu-id="7dc17-106">Utilizzo della sintassi XAML per gli elementi oggetto</span><span class="sxs-lookup"><span data-stu-id="7dc17-106">XAML Object Element Usage</span></span>  
  
```  
<x:XData>  
  <elementDataRoot>  
    [elementData]  
  </elementDataRoot>  
</x:XData>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="7dc17-107">Valori XAML</span><span class="sxs-lookup"><span data-stu-id="7dc17-107">XAML Values</span></span>  
  
|||  
|-|-|  
|`elementDataRoot`|<span data-ttu-id="7dc17-108">Il singolo elemento radice dell'isola di dati racchiusi.</span><span class="sxs-lookup"><span data-stu-id="7dc17-108">The single root element of the enclosed data island.</span></span> <span data-ttu-id="7dc17-109">Per la maggior parte dei consumer finale, che non ha un solo nodo radice XML viene considerato non valido.</span><span class="sxs-lookup"><span data-stu-id="7dc17-109">For most eventual consumers, XML that does not have a single root is considered invalid.</span></span> <span data-ttu-id="7dc17-110">In particolare, un solo nodo radice è necessaria se la `x:XData` è concepito come un'origine dati XML per molte altre tecnologie che utilizzano origini XML per il data binding o WPF.</span><span class="sxs-lookup"><span data-stu-id="7dc17-110">In particular, a single root is required if the `x:XData` is intended as an XML data source for WPF or many other technologies that use XML sources for data binding.</span></span>|  
|`[elementData]`|<span data-ttu-id="7dc17-111">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="7dc17-111">Optional.</span></span> <span data-ttu-id="7dc17-112">File XML che rappresenta i dati XML.</span><span class="sxs-lookup"><span data-stu-id="7dc17-112">XML that represents the XML data.</span></span> <span data-ttu-id="7dc17-113">Qualsiasi numero di elementi può essere contenuto i dati dell'elemento e gli elementi annidati possono essere contenuti in altri elementi. Tuttavia, si applicano le regole generali di XML.</span><span class="sxs-lookup"><span data-stu-id="7dc17-113">Any number of elements can be contained as element data and nested elements can be contained in other elements; however, the general rules of XML apply.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7dc17-114">Note</span><span class="sxs-lookup"><span data-stu-id="7dc17-114">Remarks</span></span>  
 <span data-ttu-id="7dc17-115">Gli elementi XML all'interno di un `x:XData` oggetto possibile dichiarare di nuovo tutti i possibili degli spazi dei nomi e prefissi di XMLDOM all'interno dei dati.</span><span class="sxs-lookup"><span data-stu-id="7dc17-115">The XML elements within an `x:XData` object can re-declare all possible namespaces and prefixes of the containing XMLDOM within the data.</span></span>  
  
 <span data-ttu-id="7dc17-116">Accesso programmatico a dati XML e il `x:XData` tipo XAML intrinseco viene possibile nei servizi XAML di .NET Framework tramite il <xref:System.Windows.Markup.XData> classe.</span><span class="sxs-lookup"><span data-stu-id="7dc17-116">Programmatic access to XML data and the `x:XData` intrinsic XAML type is possible in .NET Framework XAML Services through the <xref:System.Windows.Markup.XData> class.</span></span>  
  
## <a name="wpf-usage-notes"></a><span data-ttu-id="7dc17-117">Note sull'utilizzo WPF</span><span class="sxs-lookup"><span data-stu-id="7dc17-117">WPF Usage Notes</span></span>  
 <span data-ttu-id="7dc17-118">Il `x:XData` oggetto viene utilizzato principalmente come un oggetto figlio di un <xref:System.Windows.Data.XmlDataProvider>, o in alternativa, l'oggetto figlio di <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> proprietà (in XAML, questo valore viene in genere espresso nella sintassi degli elementi di proprietà).</span><span class="sxs-lookup"><span data-stu-id="7dc17-118">The `x:XData` object is primarily used as a child object of an <xref:System.Windows.Data.XmlDataProvider>, or alternatively, as the child object of the <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> property (in XAML, this is typically expressed in property element syntax).</span></span>  
  
 <span data-ttu-id="7dc17-119">I dati in genere devono ridefinire lo spazio dei nomi XML di base all'interno dell'isola di dati da un nuovo spazio dei nomi XML predefinito (impostato su una stringa vuota).</span><span class="sxs-lookup"><span data-stu-id="7dc17-119">The data should typically redefine the base XML namespace within the data island to be a new default XML namespace (set to an empty string).</span></span> <span data-ttu-id="7dc17-120">Ciò è più semplice per le isole di dati semplici in quanto il <xref:System.Windows.Data.Binding.XPath%2A> espressioni che vengono usate per fare riferimento e associare ai dati possono evitare di includere i prefissi.</span><span class="sxs-lookup"><span data-stu-id="7dc17-120">This is easiest for simple data islands because the <xref:System.Windows.Data.Binding.XPath%2A> expressions that are used to reference and bind to the data can avoid inclusion of prefixes.</span></span> <span data-ttu-id="7dc17-121">Isole di dati più complesse potrebbero definire più prefissi per i dati e usare un prefisso specifico per lo spazio dei nomi XML in corrispondenza della radice.</span><span class="sxs-lookup"><span data-stu-id="7dc17-121">More complex data islands might define multiple prefixes for the data and use a specific prefix for the XML namespace at the root.</span></span> <span data-ttu-id="7dc17-122">In questo caso, tutti <xref:System.Windows.Data.Binding.XPath%2A> espressione che fa riferimento deve includere il prefisso di mapping dello spazio dei nomi appropriato.</span><span class="sxs-lookup"><span data-stu-id="7dc17-122">In this case, all <xref:System.Windows.Data.Binding.XPath%2A> expression references should include the appropriate namespace-mapped prefix.</span></span> <span data-ttu-id="7dc17-123">Per altre informazioni, vedere la [panoramica del data binding](../../../docs/framework/wpf/data/data-binding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="7dc17-123">For more information, see [Data Binding Overview](../../../docs/framework/wpf/data/data-binding-overview.md).</span></span>  
  
 <span data-ttu-id="7dc17-124">Tecnicamente `x:XData` può essere utilizzato come il contenuto di qualsiasi proprietà di tipo <xref:System.Xml.Serialization.IXmlSerializable>.</span><span class="sxs-lookup"><span data-stu-id="7dc17-124">Technically, `x:XData` can be used as the content of any property of type <xref:System.Xml.Serialization.IXmlSerializable>.</span></span> <span data-ttu-id="7dc17-125">Tuttavia, <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> è l'unica implementazione rilevante.</span><span class="sxs-lookup"><span data-stu-id="7dc17-125">However, <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> is the only prominent implementation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7dc17-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7dc17-126">See also</span></span>
- <xref:System.Windows.Data.XmlDataProvider>
- [<span data-ttu-id="7dc17-127">Panoramica sul data binding</span><span class="sxs-lookup"><span data-stu-id="7dc17-127">Data Binding Overview</span></span>](../../../docs/framework/wpf/data/data-binding-overview.md)
- [<span data-ttu-id="7dc17-128">Estensione di markup Binding</span><span class="sxs-lookup"><span data-stu-id="7dc17-128">Binding Markup Extension</span></span>](../../../docs/framework/wpf/advanced/binding-markup-extension.md)
