---
title: Proprietà Value XML (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlPropertyExtensionValue
helpviewer_keywords:
- Value property [Visual Basic]
- Visual Basic code, accessing XML
- XML axis [Visual Basic], Value
- XML Value property [Visual Basic]
ms.assetid: 7ddd057a-a195-4e9b-ad8b-2ee0e615a20f
ms.openlocfilehash: 46f81e39686da30270cd67edeb4c9f2d43e048b3
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/28/2019
ms.locfileid: "71592009"
---
# <a name="xml-value-property-visual-basic"></a><span data-ttu-id="65acd-102">Proprietà Value XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="65acd-102">XML Value Property (Visual Basic)</span></span>

<span data-ttu-id="65acd-103">Consente di accedere al valore del primo elemento di una raccolta di oggetti <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="65acd-103">Provides access to the value of the first element of a collection of <xref:System.Xml.Linq.XElement> objects.</span></span>

## <a name="syntax"></a><span data-ttu-id="65acd-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="65acd-104">Syntax</span></span>

```vb
object.Value
```

## <a name="parts"></a><span data-ttu-id="65acd-105">Parti</span><span class="sxs-lookup"><span data-stu-id="65acd-105">Parts</span></span>

|<span data-ttu-id="65acd-106">Nome</span><span class="sxs-lookup"><span data-stu-id="65acd-106">Term</span></span>|<span data-ttu-id="65acd-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="65acd-107">Definition</span></span>|  
|---|---|  
|`object`|<span data-ttu-id="65acd-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="65acd-108">Required.</span></span> <span data-ttu-id="65acd-109">Raccolta di oggetti <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="65acd-109">Collection of <xref:System.Xml.Linq.XElement> objects.</span></span>|  

## <a name="return-value"></a><span data-ttu-id="65acd-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="65acd-110">Return Value</span></span>

 <span data-ttu-id="65acd-111">Oggetto `String` che contiene il valore del primo elemento della raccolta o `Nothing` se l'insieme è vuoto.</span><span class="sxs-lookup"><span data-stu-id="65acd-111">A `String` that contains the value of the first element of the collection, or `Nothing` if the collection is empty.</span></span>

## <a name="remarks"></a><span data-ttu-id="65acd-112">Note</span><span class="sxs-lookup"><span data-stu-id="65acd-112">Remarks</span></span>

 <span data-ttu-id="65acd-113">La proprietà <xref:System.Xml.Linq.XElement.Value%2A> consente di accedere facilmente al valore del primo elemento in una raccolta di oggetti <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="65acd-113">The <xref:System.Xml.Linq.XElement.Value%2A> property makes it easy to access the value of the first element in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="65acd-114">Questa proprietà verifica innanzitutto se la raccolta contiene almeno un oggetto.</span><span class="sxs-lookup"><span data-stu-id="65acd-114">This property first checks whether the collection contains at least one object.</span></span> <span data-ttu-id="65acd-115">Se la raccolta è vuota, questa proprietà restituisce `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="65acd-115">If the collection is empty, this property returns `Nothing`.</span></span> <span data-ttu-id="65acd-116">In caso contrario, questa proprietà restituisce il valore della proprietà <xref:System.Xml.Linq.XElement.Value%2A> del primo elemento nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="65acd-116">Otherwise, this property returns the value of the <xref:System.Xml.Linq.XElement.Value%2A> property of the first element in the collection.</span></span>

> [!NOTE]
> <span data-ttu-id="65acd-117">Quando si accede al valore di un attributo XML usando l'identificatore ' \@', il valore dell'attributo viene restituito come `String` e non è necessario specificare in modo esplicito la proprietà <xref:System.Xml.Linq.XAttribute.Value%2A>.</span><span class="sxs-lookup"><span data-stu-id="65acd-117">When you access the value of an XML attribute using the '\@' identifier, the attribute value is returned as a `String` and you do not need to explicitly specify the <xref:System.Xml.Linq.XAttribute.Value%2A> property.</span></span>

 <span data-ttu-id="65acd-118">Per accedere ad altri elementi di una raccolta, è possibile usare la proprietà dell'indicizzatore di estensione XML.</span><span class="sxs-lookup"><span data-stu-id="65acd-118">To access other elements in a collection, you can use the XML extension indexer property.</span></span> <span data-ttu-id="65acd-119">Per altre informazioni, vedere [Proprietà Indexer di estensione](extension-indexer-property.md).</span><span class="sxs-lookup"><span data-stu-id="65acd-119">For more information, see [Extension Indexer Property](extension-indexer-property.md).</span></span>

## <a name="inheritance"></a><span data-ttu-id="65acd-120">Ereditarietà</span><span class="sxs-lookup"><span data-stu-id="65acd-120">Inheritance</span></span>

 <span data-ttu-id="65acd-121">La maggior parte degli utenti non dovrà implementare <xref:System.Collections.Generic.IEnumerable%601> e pertanto può ignorare questa sezione.</span><span class="sxs-lookup"><span data-stu-id="65acd-121">Most users will not have to implement <xref:System.Collections.Generic.IEnumerable%601>, and can therefore ignore this section.</span></span>

 <span data-ttu-id="65acd-122">La proprietà <xref:System.Xml.Linq.XElement.Value%2A> è una proprietà di estensione per i tipi che implementano `IEnumerable(Of XElement)`.</span><span class="sxs-lookup"><span data-stu-id="65acd-122">The <xref:System.Xml.Linq.XElement.Value%2A> property is an extension property for types that implement `IEnumerable(Of XElement)`.</span></span> <span data-ttu-id="65acd-123">Il binding di questa proprietà di estensione è analogo all'associazione dei metodi di estensione: se un tipo implementa una delle interfacce e definisce una proprietà con il nome "value", la proprietà ha la precedenza sulla proprietà di estensione.</span><span class="sxs-lookup"><span data-stu-id="65acd-123">The binding of this extension property is like the binding of extension methods: if a type implements one of the interfaces and defines a property that has the name "Value", that property has precedence over the extension property.</span></span> <span data-ttu-id="65acd-124">In altre parole, è possibile eseguire l'override di questa proprietà <xref:System.Xml.Linq.XElement.Value%2A> definendo una nuova proprietà in una classe che implementa `IEnumerable(Of XElement)`.</span><span class="sxs-lookup"><span data-stu-id="65acd-124">In other words, this <xref:System.Xml.Linq.XElement.Value%2A> property can be overridden by defining a new property in a class that implements `IEnumerable(Of XElement)`.</span></span>

## <a name="example"></a><span data-ttu-id="65acd-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="65acd-125">Example</span></span>

 <span data-ttu-id="65acd-126">Nell'esempio seguente viene illustrato come utilizzare la proprietà <xref:System.Xml.Linq.XElement.Value%2A> per accedere al primo nodo di una raccolta di oggetti <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="65acd-126">The following example shows how to use the <xref:System.Xml.Linq.XElement.Value%2A> property to access the first node in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="65acd-127">Nell'esempio viene utilizzata la proprietà Axis Child per ottenere la raccolta di tutti i nodi figlio denominati `phone` presenti nell'oggetto `contact`.</span><span class="sxs-lookup"><span data-stu-id="65acd-127">The example uses the child axis property to get the collection of all child nodes named `phone` that are in the `contact` object.</span></span>

 [!code-vb[VbXMLSamples#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples7.vb#15)]

 <span data-ttu-id="65acd-128">Questo codice visualizza il testo seguente:</span><span class="sxs-lookup"><span data-stu-id="65acd-128">This code displays the following text:</span></span>

 `Phone number: 206-555-0144`

## <a name="example"></a><span data-ttu-id="65acd-129">Esempio</span><span class="sxs-lookup"><span data-stu-id="65acd-129">Example</span></span>

 <span data-ttu-id="65acd-130">Nell'esempio seguente viene illustrato come ottenere il valore di un attributo XML da una raccolta di oggetti <xref:System.Xml.Linq.XAttribute>.</span><span class="sxs-lookup"><span data-stu-id="65acd-130">The following example shows how to get the value of an XML attribute from a collection of <xref:System.Xml.Linq.XAttribute> objects.</span></span> <span data-ttu-id="65acd-131">Nell'esempio viene utilizzata la proprietà axis dell'attributo per visualizzare il valore dell'attributo `type` per tutti gli elementi `phone`.</span><span class="sxs-lookup"><span data-stu-id="65acd-131">The example uses the attribute axis property to display the value of the `type` attribute for all of the `phone` elements.</span></span>

 [!code-vb[VbXMLSamples#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples7.vb#16)]

 <span data-ttu-id="65acd-132">Questo codice visualizza il testo seguente:</span><span class="sxs-lookup"><span data-stu-id="65acd-132">This code displays the following text:</span></span>

 ```console
 home
 work
```

## <a name="see-also"></a><span data-ttu-id="65acd-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="65acd-133">See also</span></span>

- <xref:System.Xml.Linq.XElement>
- <xref:System.Collections.Generic.IEnumerable%601>
- [<span data-ttu-id="65acd-134">Proprietà Axis XML</span><span class="sxs-lookup"><span data-stu-id="65acd-134">XML Axis Properties</span></span>](index.md)
- [<span data-ttu-id="65acd-135">Valori letterali XML</span><span class="sxs-lookup"><span data-stu-id="65acd-135">XML Literals</span></span>](../xml-literals/index.md)
- [<span data-ttu-id="65acd-136">Creazione di XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="65acd-136">Creating XML in Visual Basic</span></span>](../../programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="65acd-137">Metodi di estensione</span><span class="sxs-lookup"><span data-stu-id="65acd-137">Extension Methods</span></span>](../../programming-guide/language-features/procedures/extension-methods.md)
- [<span data-ttu-id="65acd-138">Proprietà dell'indicizzatore di estensione</span><span class="sxs-lookup"><span data-stu-id="65acd-138">Extension Indexer Property</span></span>](extension-indexer-property.md)
- [<span data-ttu-id="65acd-139">Proprietà Child Axis XML</span><span class="sxs-lookup"><span data-stu-id="65acd-139">XML Child Axis Property</span></span>](xml-child-axis-property.md)
- [<span data-ttu-id="65acd-140">Proprietà axis dell'attributo XML</span><span class="sxs-lookup"><span data-stu-id="65acd-140">XML Attribute Axis Property</span></span>](xml-attribute-axis-property.md)
