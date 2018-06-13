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
ms.openlocfilehash: 31c9ce2774d6c6182403885a4438c4aa6bf143ad
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604185"
---
# <a name="xml-value-property-visual-basic"></a><span data-ttu-id="cb1f5-102">Proprietà Value XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cb1f5-102">XML Value Property (Visual Basic)</span></span>
<span data-ttu-id="cb1f5-103">Fornisce l'accesso al valore del primo elemento di una raccolta di <xref:System.Xml.Linq.XElement> oggetti.</span><span class="sxs-lookup"><span data-stu-id="cb1f5-103">Provides access to the value of the first element of a collection of <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb1f5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cb1f5-104">Syntax</span></span>  
  
```  
object.Value  
```  
  
## <a name="parts"></a><span data-ttu-id="cb1f5-105">Parti</span><span class="sxs-lookup"><span data-stu-id="cb1f5-105">Parts</span></span>  
  
|<span data-ttu-id="cb1f5-106">Termine</span><span class="sxs-lookup"><span data-stu-id="cb1f5-106">Term</span></span>|<span data-ttu-id="cb1f5-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="cb1f5-107">Definition</span></span>|  
|---|---|  
|`object`|<span data-ttu-id="cb1f5-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="cb1f5-108">Required.</span></span> <span data-ttu-id="cb1f5-109">Raccolta di oggetti <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="cb1f5-109">Collection of <xref:System.Xml.Linq.XElement> objects.</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="cb1f5-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="cb1f5-110">Return Value</span></span>  
 <span data-ttu-id="cb1f5-111">Oggetto `String` che contiene il valore del primo elemento della raccolta, o `Nothing` se la raccolta è vuota.</span><span class="sxs-lookup"><span data-stu-id="cb1f5-111">A `String` that contains the value of the first element of the collection, or `Nothing` if the collection is empty.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cb1f5-112">Note</span><span class="sxs-lookup"><span data-stu-id="cb1f5-112">Remarks</span></span>  
 <span data-ttu-id="cb1f5-113">Il <xref:System.Xml.Linq.XElement.Value%2A> proprietà rende più semplice accedere al valore del primo elemento in una raccolta di <xref:System.Xml.Linq.XElement> oggetti.</span><span class="sxs-lookup"><span data-stu-id="cb1f5-113">The <xref:System.Xml.Linq.XElement.Value%2A> property makes it easy to access the value of the first element in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="cb1f5-114">Questa proprietà controlla innanzitutto se la raccolta contiene almeno un oggetto.</span><span class="sxs-lookup"><span data-stu-id="cb1f5-114">This property first checks whether the collection contains at least one object.</span></span> <span data-ttu-id="cb1f5-115">Se la raccolta è vuota, questa proprietà restituisce `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="cb1f5-115">If the collection is empty, this property returns `Nothing`.</span></span> <span data-ttu-id="cb1f5-116">In caso contrario, questa proprietà restituisce il valore di <xref:System.Xml.Linq.XElement.Value%2A> proprietà del primo elemento nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="cb1f5-116">Otherwise, this property returns the value of the <xref:System.Xml.Linq.XElement.Value%2A> property of the first element in the collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cb1f5-117">Quando si accede al valore di un attributo XML utilizzando il ' @' identificatore, il valore dell'attributo viene restituito come un `String` e non è necessario specificare in modo esplicito il <xref:System.Xml.Linq.XAttribute.Value%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="cb1f5-117">When you access the value of an XML attribute using the '@' identifier, the attribute value is returned as a `String` and you do not need to explicitly specify the <xref:System.Xml.Linq.XAttribute.Value%2A> property.</span></span>  
  
 <span data-ttu-id="cb1f5-118">Per accedere agli altri elementi in una raccolta, è possibile utilizzare la proprietà dell'indicizzatore di estensione XML.</span><span class="sxs-lookup"><span data-stu-id="cb1f5-118">To access other elements in a collection, you can use the XML extension indexer property.</span></span> <span data-ttu-id="cb1f5-119">Per ulteriori informazioni, vedere [proprietà dell'indicizzatore di estensione](../../../visual-basic/language-reference/xml-axis/extension-indexer-property.md).</span><span class="sxs-lookup"><span data-stu-id="cb1f5-119">For more information, see [Extension Indexer Property](../../../visual-basic/language-reference/xml-axis/extension-indexer-property.md).</span></span>  
  
## <a name="inheritance"></a><span data-ttu-id="cb1f5-120">Ereditarietà</span><span class="sxs-lookup"><span data-stu-id="cb1f5-120">Inheritance</span></span>  
 <span data-ttu-id="cb1f5-121">La maggior parte degli utenti non dovrà implementare <xref:System.Collections.Generic.IEnumerable%601>ed è pertanto possibile ignorare questa sezione.</span><span class="sxs-lookup"><span data-stu-id="cb1f5-121">Most users will not have to implement <xref:System.Collections.Generic.IEnumerable%601>, and can therefore ignore this section.</span></span>  
  
 <span data-ttu-id="cb1f5-122">Il <xref:System.Xml.Linq.XElement.Value%2A> proprietà è una proprietà di estensione per tipi che implementano `IEnumerable(Of XElement)`.</span><span class="sxs-lookup"><span data-stu-id="cb1f5-122">The <xref:System.Xml.Linq.XElement.Value%2A> property is an extension property for types that implement `IEnumerable(Of XElement)`.</span></span> <span data-ttu-id="cb1f5-123">L'associazione di questa proprietà di estensione è simile all'associazione di metodi di estensione: se un tipo implementa una delle interfacce e definisce una proprietà con il nome "Value", tale proprietà ha la precedenza sulla proprietà di estensione.</span><span class="sxs-lookup"><span data-stu-id="cb1f5-123">The binding of this extension property is like the binding of extension methods: if a type implements one of the interfaces and defines a property that has the name "Value", that property has precedence over the extension property.</span></span> <span data-ttu-id="cb1f5-124">In altre parole, questo <xref:System.Xml.Linq.XElement.Value%2A> può eseguire l'override di proprietà mediante la definizione di una nuova proprietà in una classe che implementa `IEnumerable(Of XElement)`.</span><span class="sxs-lookup"><span data-stu-id="cb1f5-124">In other words, this <xref:System.Xml.Linq.XElement.Value%2A> property can be overridden by defining a new property in a class that implements `IEnumerable(Of XElement)`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cb1f5-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="cb1f5-125">Example</span></span>  
 <span data-ttu-id="cb1f5-126">Nell'esempio seguente viene illustrato come utilizzare il <xref:System.Xml.Linq.XElement.Value%2A> proprietà per accedere al primo nodo in una raccolta di <xref:System.Xml.Linq.XElement> oggetti.</span><span class="sxs-lookup"><span data-stu-id="cb1f5-126">The following example shows how to use the <xref:System.Xml.Linq.XElement.Value%2A> property to access the first node in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="cb1f5-127">Nell'esempio viene utilizzata la proprietà di asse figlio per ottenere la raccolta di tutti i nodi figlio denominati `phone` che si trovano i `contact` oggetto.</span><span class="sxs-lookup"><span data-stu-id="cb1f5-127">The example uses the child axis property to get the collection of all child nodes named `phone` that are in the `contact` object.</span></span>  
  
 [!code-vb[VbXMLSamples#15](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-value-property_1.vb)]  
  
 <span data-ttu-id="cb1f5-128">Questo codice visualizza il testo seguente:</span><span class="sxs-lookup"><span data-stu-id="cb1f5-128">This code displays the following text:</span></span>  
  
 `Phone number: 206-555-0144`  
  
## <a name="example"></a><span data-ttu-id="cb1f5-129">Esempio</span><span class="sxs-lookup"><span data-stu-id="cb1f5-129">Example</span></span>  
 <span data-ttu-id="cb1f5-130">Nell'esempio seguente viene illustrato come ottenere il valore di un attributo XML da una raccolta di <xref:System.Xml.Linq.XAttribute> oggetti.</span><span class="sxs-lookup"><span data-stu-id="cb1f5-130">The following example shows how to get the value of an XML attribute from a collection of <xref:System.Xml.Linq.XAttribute> objects.</span></span> <span data-ttu-id="cb1f5-131">Nell'esempio viene utilizzata la proprietà axis dell'attributo per visualizzare il valore del `type` attributo per tutti i `phone` elementi.</span><span class="sxs-lookup"><span data-stu-id="cb1f5-131">The example uses the attribute axis property to display the value of the `type` attribute for all of the `phone` elements.</span></span>  
  
 [!code-vb[VbXMLSamples#16](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-value-property_2.vb)]  
  
 <span data-ttu-id="cb1f5-132">Questo codice visualizza il testo seguente:</span><span class="sxs-lookup"><span data-stu-id="cb1f5-132">This code displays the following text:</span></span>  
  
 `home`  
  
 `work`  
  
## <a name="see-also"></a><span data-ttu-id="cb1f5-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cb1f5-133">See Also</span></span>  
 <xref:System.Xml.Linq.XElement>  
 <xref:System.Collections.Generic.IEnumerable%601>  
 [<span data-ttu-id="cb1f5-134">Proprietà Axis XML</span><span class="sxs-lookup"><span data-stu-id="cb1f5-134">XML Axis Properties</span></span>](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)  
 [<span data-ttu-id="cb1f5-135">Valori letterali XML</span><span class="sxs-lookup"><span data-stu-id="cb1f5-135">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)  
 [<span data-ttu-id="cb1f5-136">Creazione di XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="cb1f5-136">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [<span data-ttu-id="cb1f5-137">Metodi di estensione</span><span class="sxs-lookup"><span data-stu-id="cb1f5-137">Extension Methods</span></span>](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)  
 [<span data-ttu-id="cb1f5-138">Proprietà dell'indicizzatore di estensione</span><span class="sxs-lookup"><span data-stu-id="cb1f5-138">Extension Indexer Property</span></span>](../../../visual-basic/language-reference/xml-axis/extension-indexer-property.md)  
 [<span data-ttu-id="cb1f5-139">Proprietà Child Axis XML</span><span class="sxs-lookup"><span data-stu-id="cb1f5-139">XML Child Axis Property</span></span>](../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md)  
 [<span data-ttu-id="cb1f5-140">Proprietà axis dell'attributo XML</span><span class="sxs-lookup"><span data-stu-id="cb1f5-140">XML Attribute Axis Property</span></span>](../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md)
