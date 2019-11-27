---
title: Proprietà dell'indicizzatore di estensione
ms.date: 07/20/2015
f1_keywords:
- vb.XmlPropertyExtensionIndexer
helpviewer_keywords:
- Visual Basic code, accessing XML
- XML extension indexer [Visual Basic]
- extension indexer [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: a16a4b13-54be-432c-82b3-a87091464ada
ms.openlocfilehash: 5f91dc8a6b1a0d82daa4891cf826c16e2716839f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352691"
---
# <a name="extension-indexer-property-visual-basic"></a><span data-ttu-id="51c45-102">Proprietà dell'indicizzatore di estensione (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="51c45-102">Extension Indexer Property (Visual Basic)</span></span>
<span data-ttu-id="51c45-103">Fornisce l'accesso ai singoli elementi di una raccolta.</span><span class="sxs-lookup"><span data-stu-id="51c45-103">Provides access to individual elements in a collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51c45-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="51c45-104">Syntax</span></span>  
  
```vb  
object(index)  
```  
  
## <a name="parts"></a><span data-ttu-id="51c45-105">Parti</span><span class="sxs-lookup"><span data-stu-id="51c45-105">Parts</span></span>  
  
|<span data-ttu-id="51c45-106">Termine</span><span class="sxs-lookup"><span data-stu-id="51c45-106">Term</span></span>|<span data-ttu-id="51c45-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="51c45-107">Definition</span></span>|  
|---|---|  
|`object`|<span data-ttu-id="51c45-108">Obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="51c45-108">Required.</span></span> <span data-ttu-id="51c45-109">Raccolta Queryable.</span><span class="sxs-lookup"><span data-stu-id="51c45-109">A queryable collection.</span></span> <span data-ttu-id="51c45-110">Ovvero una raccolta che implementa <xref:System.Collections.Generic.IEnumerable%601> o <xref:System.Linq.IQueryable%601>.</span><span class="sxs-lookup"><span data-stu-id="51c45-110">That is, a collection that implements <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Linq.IQueryable%601>.</span></span>|  
|<span data-ttu-id="51c45-111">(</span><span class="sxs-lookup"><span data-stu-id="51c45-111">(</span></span>|<span data-ttu-id="51c45-112">Obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="51c45-112">Required.</span></span> <span data-ttu-id="51c45-113">Indica l'inizio della proprietà dell'indicizzatore.</span><span class="sxs-lookup"><span data-stu-id="51c45-113">Denotes the start of the indexer property.</span></span>|  
|`index`|<span data-ttu-id="51c45-114">Obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="51c45-114">Required.</span></span> <span data-ttu-id="51c45-115">Espressione Integer che specifica la posizione in base zero di un elemento della raccolta.</span><span class="sxs-lookup"><span data-stu-id="51c45-115">An integer expression that specifies the zero-based position of an element of the collection.</span></span>|  
|<span data-ttu-id="51c45-116">)</span><span class="sxs-lookup"><span data-stu-id="51c45-116">)</span></span>|<span data-ttu-id="51c45-117">Obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="51c45-117">Required.</span></span> <span data-ttu-id="51c45-118">Indica la fine della proprietà dell'indicizzatore.</span><span class="sxs-lookup"><span data-stu-id="51c45-118">Denotes the end of the indexer property.</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="51c45-119">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="51c45-119">Return Value</span></span>  
 <span data-ttu-id="51c45-120">Oggetto dalla posizione specificata nella raccolta o `Nothing` se l'indice non è compreso nell'intervallo.</span><span class="sxs-lookup"><span data-stu-id="51c45-120">The object from the specified location in the collection, or `Nothing` if the index is out of range.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="51c45-121">Note</span><span class="sxs-lookup"><span data-stu-id="51c45-121">Remarks</span></span>  
 <span data-ttu-id="51c45-122">È possibile usare la proprietà dell'indicizzatore di estensione per accedere ai singoli elementi di una raccolta.</span><span class="sxs-lookup"><span data-stu-id="51c45-122">You can use the extension indexer property to access individual elements in a collection.</span></span> <span data-ttu-id="51c45-123">Questa proprietà dell'indicizzatore viene in genere utilizzata nell'output delle proprietà Axis XML.</span><span class="sxs-lookup"><span data-stu-id="51c45-123">This indexer property is typically used on the output of XML axis properties.</span></span> <span data-ttu-id="51c45-124">Le proprietà dell'asse XML figlio e XML discendente restituiscono raccolte di oggetti <xref:System.Xml.Linq.XElement> o un valore di attributo.</span><span class="sxs-lookup"><span data-stu-id="51c45-124">The XML child and XML descendent axis properties return collections of <xref:System.Xml.Linq.XElement> objects or an attribute value.</span></span>  
  
 <span data-ttu-id="51c45-125">Il compilatore Visual Basic converte le proprietà dell'indicizzatore di estensione in chiamate al metodo `ElementAtOrDefault`.</span><span class="sxs-lookup"><span data-stu-id="51c45-125">The Visual Basic compiler converts extension indexer properties to calls to the `ElementAtOrDefault` method.</span></span> <span data-ttu-id="51c45-126">Diversamente da un indicizzatore di matrici, il metodo `ElementAtOrDefault` restituisce `Nothing` se l'indice non è compreso nell'intervallo.</span><span class="sxs-lookup"><span data-stu-id="51c45-126">Unlike an array indexer, the `ElementAtOrDefault` method returns `Nothing` if the index is out of range.</span></span> <span data-ttu-id="51c45-127">Questo comportamento è utile quando non è possibile determinare facilmente il numero di elementi in una raccolta.</span><span class="sxs-lookup"><span data-stu-id="51c45-127">This behavior is useful when you cannot easily determine the number of elements in a collection.</span></span>  
  
 <span data-ttu-id="51c45-128">Questa proprietà dell'indicizzatore è simile a una proprietà di estensione per le raccolte che implementano <xref:System.Collections.Generic.IEnumerable%601> o <xref:System.Linq.IQueryable%601>: viene utilizzata solo se la raccolta non dispone di un indicizzatore o di una proprietà predefinita.</span><span class="sxs-lookup"><span data-stu-id="51c45-128">This indexer property is like an extension property for collections that implement <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Linq.IQueryable%601>: it is used only if the collection does not have an indexer or a default property.</span></span>  
  
 <span data-ttu-id="51c45-129">Per accedere al valore del primo elemento in una raccolta di oggetti <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XAttribute>, è possibile utilizzare la proprietà `Value` XML.</span><span class="sxs-lookup"><span data-stu-id="51c45-129">To access the value of the first element in a collection of <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XAttribute> objects, you can use the XML `Value` property.</span></span> <span data-ttu-id="51c45-130">Per ulteriori informazioni, vedere [proprietà del valore XML](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span><span class="sxs-lookup"><span data-stu-id="51c45-130">For more information, see [XML Value Property](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="51c45-131">Esempio</span><span class="sxs-lookup"><span data-stu-id="51c45-131">Example</span></span>  
 <span data-ttu-id="51c45-132">Nell'esempio seguente viene illustrato come utilizzare l'indicizzatore di estensione per accedere al secondo nodo figlio in una raccolta di oggetti <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="51c45-132">The following example shows how to use the extension indexer to access the second child node in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="51c45-133">È possibile accedere alla raccolta utilizzando la proprietà Axis figlio, che ottiene tutti gli elementi figlio denominati `phone` nell'oggetto `contact`.</span><span class="sxs-lookup"><span data-stu-id="51c45-133">The collection is accessed by using the child axis property, which gets all child elements named `phone` in the `contact` object.</span></span>  
  
 [!code-vb[VbXMLSamples#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples11.vb#24)]  
  
 <span data-ttu-id="51c45-134">Questo codice visualizza il testo seguente:</span><span class="sxs-lookup"><span data-stu-id="51c45-134">This code displays the following text:</span></span>  
  
 `Second phone number: 425-555-0145`  
  
## <a name="see-also"></a><span data-ttu-id="51c45-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="51c45-135">See also</span></span>

- <xref:System.Xml.Linq.XElement>
- [<span data-ttu-id="51c45-136">Proprietà Axis XML</span><span class="sxs-lookup"><span data-stu-id="51c45-136">XML Axis Properties</span></span>](../../../visual-basic/language-reference/xml-axis/index.md)
- [<span data-ttu-id="51c45-137">Valori letterali XML</span><span class="sxs-lookup"><span data-stu-id="51c45-137">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="51c45-138">Creazione di XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="51c45-138">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="51c45-139">Proprietà Value XML</span><span class="sxs-lookup"><span data-stu-id="51c45-139">XML Value Property</span></span>](../../../visual-basic/language-reference/xml-axis/xml-value-property.md)
