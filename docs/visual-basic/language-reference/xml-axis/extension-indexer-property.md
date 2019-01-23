---
title: Proprietà dell'indicizzatore di estensione (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlPropertyExtensionIndexer
helpviewer_keywords:
- Visual Basic code, accessing XML
- XML extension indexer [Visual Basic]
- extension indexer [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: a16a4b13-54be-432c-82b3-a87091464ada
ms.openlocfilehash: 25a868afded83f28f5f56a9f19e050bbd32b24c0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54490830"
---
# <a name="extension-indexer-property-visual-basic"></a><span data-ttu-id="824bc-102">Proprietà dell'indicizzatore di estensione (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="824bc-102">Extension Indexer Property (Visual Basic)</span></span>
<span data-ttu-id="824bc-103">Fornisce l'accesso ai singoli elementi di una raccolta.</span><span class="sxs-lookup"><span data-stu-id="824bc-103">Provides access to individual elements in a collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="824bc-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="824bc-104">Syntax</span></span>  
  
```  
object(index)  
```  
  
## <a name="parts"></a><span data-ttu-id="824bc-105">Parti</span><span class="sxs-lookup"><span data-stu-id="824bc-105">Parts</span></span>  
  
|<span data-ttu-id="824bc-106">Termine</span><span class="sxs-lookup"><span data-stu-id="824bc-106">Term</span></span>|<span data-ttu-id="824bc-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="824bc-107">Definition</span></span>|  
|---|---|  
|`object`|<span data-ttu-id="824bc-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="824bc-108">Required.</span></span> <span data-ttu-id="824bc-109">Una raccolta disponibile per query.</span><span class="sxs-lookup"><span data-stu-id="824bc-109">A queryable collection.</span></span> <span data-ttu-id="824bc-110">Vale a dire una raccolta che implementa <xref:System.Collections.Generic.IEnumerable%601> o <xref:System.Linq.IQueryable%601>.</span><span class="sxs-lookup"><span data-stu-id="824bc-110">That is, a collection that implements <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Linq.IQueryable%601>.</span></span>|  
|<span data-ttu-id="824bc-111">(</span><span class="sxs-lookup"><span data-stu-id="824bc-111">(</span></span>|<span data-ttu-id="824bc-112">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="824bc-112">Required.</span></span> <span data-ttu-id="824bc-113">Indica l'inizio della proprietà dell'indicizzatore.</span><span class="sxs-lookup"><span data-stu-id="824bc-113">Denotes the start of the indexer property.</span></span>|  
|`index`|<span data-ttu-id="824bc-114">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="824bc-114">Required.</span></span> <span data-ttu-id="824bc-115">Espressione integer che specifica la posizione in base zero di un elemento della raccolta.</span><span class="sxs-lookup"><span data-stu-id="824bc-115">An integer expression that specifies the zero-based position of an element of the collection.</span></span>|  
|<span data-ttu-id="824bc-116">)</span><span class="sxs-lookup"><span data-stu-id="824bc-116">)</span></span>|<span data-ttu-id="824bc-117">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="824bc-117">Required.</span></span> <span data-ttu-id="824bc-118">Indica la fine della proprietà dell'indicizzatore.</span><span class="sxs-lookup"><span data-stu-id="824bc-118">Denotes the end of the indexer property.</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="824bc-119">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="824bc-119">Return Value</span></span>  
 <span data-ttu-id="824bc-120">L'oggetto dalla posizione specificata nella raccolta, o `Nothing` se l'indice è compreso nell'intervallo.</span><span class="sxs-lookup"><span data-stu-id="824bc-120">The object from the specified location in the collection, or `Nothing` if the index is out of range.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="824bc-121">Note</span><span class="sxs-lookup"><span data-stu-id="824bc-121">Remarks</span></span>  
 <span data-ttu-id="824bc-122">È possibile usare la proprietà dell'indicizzatore di estensione per accedere ai singoli elementi in una raccolta.</span><span class="sxs-lookup"><span data-stu-id="824bc-122">You can use the extension indexer property to access individual elements in a collection.</span></span> <span data-ttu-id="824bc-123">Questa proprietà di indicizzatore viene utilizzata in genere sull'output della proprietà axis XML.</span><span class="sxs-lookup"><span data-stu-id="824bc-123">This indexer property is typically used on the output of XML axis properties.</span></span> <span data-ttu-id="824bc-124">L'elemento figlio XML e proprietà axis descendant XML restituire raccolte di <xref:System.Xml.Linq.XElement> oggetti o un valore di attributo.</span><span class="sxs-lookup"><span data-stu-id="824bc-124">The XML child and XML descendent axis properties return collections of <xref:System.Xml.Linq.XElement> objects or an attribute value.</span></span>  
  
 <span data-ttu-id="824bc-125">Il compilatore Visual Basic converte le proprietà dell'indicizzatore di estensione per le chiamate al `ElementAtOrDefault` (metodo).</span><span class="sxs-lookup"><span data-stu-id="824bc-125">The Visual Basic compiler converts extension indexer properties to calls to the `ElementAtOrDefault` method.</span></span> <span data-ttu-id="824bc-126">A differenza di un indicizzatore di matrice, il `ElementAtOrDefault` restituzione del metodo `Nothing` se l'indice è compreso nell'intervallo.</span><span class="sxs-lookup"><span data-stu-id="824bc-126">Unlike an array indexer, the `ElementAtOrDefault` method returns `Nothing` if the index is out of range.</span></span> <span data-ttu-id="824bc-127">Questo comportamento è utile quando non è possibile determinare facilmente il numero di elementi in una raccolta.</span><span class="sxs-lookup"><span data-stu-id="824bc-127">This behavior is useful when you cannot easily determine the number of elements in a collection.</span></span>  
  
 <span data-ttu-id="824bc-128">Questa proprietà dell'indicizzatore è simile a una proprietà di estensione per le raccolte che implementano <xref:System.Collections.Generic.IEnumerable%601> o <xref:System.Linq.IQueryable%601>: viene utilizzato solo se la raccolta non ha un indicizzatore o una proprietà predefinita.</span><span class="sxs-lookup"><span data-stu-id="824bc-128">This indexer property is like an extension property for collections that implement <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Linq.IQueryable%601>: it is used only if the collection does not have an indexer or a default property.</span></span>  
  
 <span data-ttu-id="824bc-129">Per accedere al valore del primo elemento in una raccolta di <xref:System.Xml.Linq.XElement> oppure <xref:System.Xml.Linq.XAttribute> oggetti, è possibile utilizzare il codice XML `Value` proprietà.</span><span class="sxs-lookup"><span data-stu-id="824bc-129">To access the value of the first element in a collection of <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XAttribute> objects, you can use the XML `Value` property.</span></span> <span data-ttu-id="824bc-130">Per altre informazioni, vedere [proprietà Value XML](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span><span class="sxs-lookup"><span data-stu-id="824bc-130">For more information, see [XML Value Property](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="824bc-131">Esempio</span><span class="sxs-lookup"><span data-stu-id="824bc-131">Example</span></span>  
 <span data-ttu-id="824bc-132">Nell'esempio seguente viene illustrato come usare l'indicizzatore di estensione per accedere al secondo nodo figlio in una raccolta di <xref:System.Xml.Linq.XElement> oggetti.</span><span class="sxs-lookup"><span data-stu-id="824bc-132">The following example shows how to use the extension indexer to access the second child node in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="824bc-133">La raccolta è accessibile tramite la proprietà di asse figlio, che ottiene tutti gli elementi figlio denominati `phone` nella `contact` oggetto.</span><span class="sxs-lookup"><span data-stu-id="824bc-133">The collection is accessed by using the child axis property, which gets all child elements named `phone` in the `contact` object.</span></span>  
  
 [!code-vb[VbXMLSamples#24](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/extension-indexer-property_1.vb)]  
  
 <span data-ttu-id="824bc-134">Questo codice visualizza il testo seguente:</span><span class="sxs-lookup"><span data-stu-id="824bc-134">This code displays the following text:</span></span>  
  
 `Second phone number: 425-555-0145`  
  
## <a name="see-also"></a><span data-ttu-id="824bc-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="824bc-135">See also</span></span>
- <xref:System.Xml.Linq.XElement>
- [<span data-ttu-id="824bc-136">Proprietà Axis XML</span><span class="sxs-lookup"><span data-stu-id="824bc-136">XML Axis Properties</span></span>](../../../visual-basic/language-reference/xml-axis/index.md)
- [<span data-ttu-id="824bc-137">Valori letterali XML</span><span class="sxs-lookup"><span data-stu-id="824bc-137">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="824bc-138">Creazione di XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="824bc-138">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="824bc-139">Proprietà Value XML</span><span class="sxs-lookup"><span data-stu-id="824bc-139">XML Value Property</span></span>](../../../visual-basic/language-reference/xml-axis/xml-value-property.md)
