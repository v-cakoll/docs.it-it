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
# <a name="xxdata-intrinsic-xaml-type"></a><span data-ttu-id="4cbdc-102">Tipo XAML intrinseco x:XData</span><span class="sxs-lookup"><span data-stu-id="4cbdc-102">x:XData Intrinsic XAML Type</span></span>
<span data-ttu-id="4cbdc-103">Consente il posizionamento di isole di dati XML all'interno di una produzione XAML.</span><span class="sxs-lookup"><span data-stu-id="4cbdc-103">Enables placement of XML data islands within a XAML production.</span></span> <span data-ttu-id="4cbdc-104">Gli elementi `x:XData` XML all'interno non devono essere considerati dai processori XAML come se facessero parte dello spazio dei nomi XAML predefinito che agisce o di qualsiasi altro spazio dei nomi XAML.</span><span class="sxs-lookup"><span data-stu-id="4cbdc-104">XML elements within `x:XData` should not be treated by XAML processors as if they are a part of the acting default XAML namespace or any other XAML namespace.</span></span> <span data-ttu-id="4cbdc-105">`x:XData`può contenere codice XML arbitrario ben formato.</span><span class="sxs-lookup"><span data-stu-id="4cbdc-105">`x:XData` can contain arbitrary well-formed XML.</span></span>

## <a name="xaml-object-element-usage"></a><span data-ttu-id="4cbdc-106">Utilizzo della sintassi XAML per gli elementi oggetto</span><span class="sxs-lookup"><span data-stu-id="4cbdc-106">XAML Object Element Usage</span></span>

```xaml
<x:XData>
  <elementDataRoot>
    [elementData]
  </elementDataRoot>
</x:XData>
```

## <a name="xaml-values"></a><span data-ttu-id="4cbdc-107">Valori XAML</span><span class="sxs-lookup"><span data-stu-id="4cbdc-107">XAML Values</span></span>

|||
|-|-|
|`elementDataRoot`|<span data-ttu-id="4cbdc-108">Singolo elemento radice dell'isola di dati racchiusa.</span><span class="sxs-lookup"><span data-stu-id="4cbdc-108">The single root element of the enclosed data island.</span></span> <span data-ttu-id="4cbdc-109">Per la maggior parte dei consumer, XML che non dispone di una singola radice è considerato non valido.</span><span class="sxs-lookup"><span data-stu-id="4cbdc-109">For most eventual consumers, XML that does not have a single root is considered invalid.</span></span> <span data-ttu-id="4cbdc-110">In particolare, è necessaria una `x:XData` singola radice se l'oggetto è inteso come origine dati XML per WPFWPF o molte altre tecnologie che utilizzano origini XML per l'associazione dati.</span><span class="sxs-lookup"><span data-stu-id="4cbdc-110">In particular, a single root is required if the `x:XData` is intended as an XML data source for WPF or many other technologies that use XML sources for data binding.</span></span>|
|`[elementData]`|<span data-ttu-id="4cbdc-111">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="4cbdc-111">Optional.</span></span> <span data-ttu-id="4cbdc-112">XML che rappresenta i dati XML.</span><span class="sxs-lookup"><span data-stu-id="4cbdc-112">XML that represents the XML data.</span></span> <span data-ttu-id="4cbdc-113">Qualsiasi numero di elementi può essere contenuto come dati dell'elemento e gli elementi annidati possono essere contenuti in altri elementi; tuttavia, si applicano le regole generali di XML.</span><span class="sxs-lookup"><span data-stu-id="4cbdc-113">Any number of elements can be contained as element data and nested elements can be contained in other elements; however, the general rules of XML apply.</span></span>|

## <a name="remarks"></a><span data-ttu-id="4cbdc-114">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="4cbdc-114">Remarks</span></span>

<span data-ttu-id="4cbdc-115">Gli elementi XML `x:XData` all'interno di un oggetto possono dichiarare nuovamente tutti i possibili spazi dei nomi e prefissi del codice XMLDOM contenitore all'interno dei dati.</span><span class="sxs-lookup"><span data-stu-id="4cbdc-115">The XML elements within an `x:XData` object can re-declare all possible namespaces and prefixes of the containing XMLDOM within the data.</span></span>

<span data-ttu-id="4cbdc-116">L'accesso a livello `x:XData` di codice ai dati XML e <xref:System.Windows.Markup.XData> al tipo XAML intrinseco è possibile nei servizi XAML .NET tramite la classe .</span><span class="sxs-lookup"><span data-stu-id="4cbdc-116">Programmatic access to XML data and the `x:XData` intrinsic XAML type is possible in .NET XAML Services through the <xref:System.Windows.Markup.XData> class.</span></span>

## <a name="wpf-usage-notes"></a><span data-ttu-id="4cbdc-117">Note sull'utilizzo di WPF</span><span class="sxs-lookup"><span data-stu-id="4cbdc-117">WPF Usage Notes</span></span>

<span data-ttu-id="4cbdc-118">L'oggetto `x:XData` viene utilizzato principalmente come <xref:System.Windows.Data.XmlDataProvider>oggetto figlio di un oggetto , <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> o in alternativa, come l'oggetto figlio della proprietà (in XAML, questo è in genere espresso nella sintassi degli elementi proprietà).</span><span class="sxs-lookup"><span data-stu-id="4cbdc-118">The `x:XData` object is primarily used as a child object of an <xref:System.Windows.Data.XmlDataProvider>, or alternatively, as the child object of the <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> property (in XAML, this is typically expressed in property element syntax).</span></span>

<span data-ttu-id="4cbdc-119">I dati devono in genere ridefinire lo spazio dei nomi XML di base all'interno dell'isola di dati in modo che sia un nuovo spazio dei nomi XML predefinito (impostato su una stringa vuota).</span><span class="sxs-lookup"><span data-stu-id="4cbdc-119">The data should typically redefine the base XML namespace within the data island to be a new default XML namespace (set to an empty string).</span></span> <span data-ttu-id="4cbdc-120">Questa operazione è più semplice <xref:System.Windows.Data.Binding.XPath%2A> per le isole di dati semplici perché le espressioni utilizzate per fare riferimento e associare ai dati possono evitare l'inclusione di prefissi.</span><span class="sxs-lookup"><span data-stu-id="4cbdc-120">This is easiest for simple data islands because the <xref:System.Windows.Data.Binding.XPath%2A> expressions that are used to reference and bind to the data can avoid inclusion of prefixes.</span></span> <span data-ttu-id="4cbdc-121">Le isole di dati più complesse potrebbero definire più prefissi per i dati e usare un prefisso specifico per lo spazio dei nomi XML nella radice.</span><span class="sxs-lookup"><span data-stu-id="4cbdc-121">More complex data islands might define multiple prefixes for the data and use a specific prefix for the XML namespace at the root.</span></span> <span data-ttu-id="4cbdc-122">In questo caso, tutti i <xref:System.Windows.Data.Binding.XPath%2A> riferimenti alle espressioni devono includere il prefisso appropriato mappato allo spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="4cbdc-122">In this case, all <xref:System.Windows.Data.Binding.XPath%2A> expression references should include the appropriate namespace-mapped prefix.</span></span> <span data-ttu-id="4cbdc-123">Per ulteriori informazioni, vedere [Cenni preliminari sull'associazione dati](../data/data-binding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="4cbdc-123">For more information, see [Data Binding Overview](../data/data-binding-overview.md).</span></span>

<span data-ttu-id="4cbdc-124">Tecnicamente, `x:XData` può essere utilizzato come contenuto <xref:System.Xml.Serialization.IXmlSerializable>di qualsiasi proprietà di tipo .</span><span class="sxs-lookup"><span data-stu-id="4cbdc-124">Technically, `x:XData` can be used as the content of any property of type <xref:System.Xml.Serialization.IXmlSerializable>.</span></span> <span data-ttu-id="4cbdc-125">Tuttavia, <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> è l'unica attuazione di primo piano.</span><span class="sxs-lookup"><span data-stu-id="4cbdc-125">However, <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> is the only prominent implementation.</span></span>

## <a name="see-also"></a><span data-ttu-id="4cbdc-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4cbdc-126">See also</span></span>

- <xref:System.Windows.Data.XmlDataProvider>
- [<span data-ttu-id="4cbdc-127">Cenni preliminari sull'associazione dati</span><span class="sxs-lookup"><span data-stu-id="4cbdc-127">Data Binding Overview</span></span>](../data/data-binding-overview.md)
- [<span data-ttu-id="4cbdc-128">Associazione dell'estensione di markup</span><span class="sxs-lookup"><span data-stu-id="4cbdc-128">Binding Markup Extension</span></span>](../../framework/wpf/advanced/binding-markup-extension.md)
