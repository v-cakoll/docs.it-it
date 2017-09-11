---
title: "Proprietà dell&quot;indicizzatore di estensione (Visual Basic) | Documenti di Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlPropertyExtensionIndexer
dev_langs:
- VB
helpviewer_keywords:
- Visual Basic code, accessing XML
- XML extension indexer [Visual Basic]
- extension indexer [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: a16a4b13-54be-432c-82b3-a87091464ada
caps.latest.revision: 22
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 71c16d3f1b93647154bdead4a85d1117b5f6c463
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="extension-indexer-property-visual-basic"></a><span data-ttu-id="42fb3-102">Proprietà dell'indicizzatore di estensione (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="42fb3-102">Extension Indexer Property (Visual Basic)</span></span>
<span data-ttu-id="42fb3-103">Fornisce l'accesso ai singoli elementi di una raccolta.</span><span class="sxs-lookup"><span data-stu-id="42fb3-103">Provides access to individual elements in a collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42fb3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="42fb3-104">Syntax</span></span>  
  
```  
  
object(index)  
```  
  
## <a name="parts"></a><span data-ttu-id="42fb3-105">Parti</span><span class="sxs-lookup"><span data-stu-id="42fb3-105">Parts</span></span>  
  
|<span data-ttu-id="42fb3-106">Termine</span><span class="sxs-lookup"><span data-stu-id="42fb3-106">Term</span></span>|<span data-ttu-id="42fb3-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="42fb3-107">Definition</span></span>|  
|---|---|  
|`object`|<span data-ttu-id="42fb3-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="42fb3-108">Required.</span></span> <span data-ttu-id="42fb3-109">Raccolta queryable.</span><span class="sxs-lookup"><span data-stu-id="42fb3-109">A queryable collection.</span></span> <span data-ttu-id="42fb3-110">Vale a dire, una raccolta che implementa <xref:System.Collections.Generic.IEnumerable%601>o <xref:System.Linq.IQueryable%601>.</xref:System.Linq.IQueryable%601> </xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="42fb3-110">That is, a collection that implements <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Linq.IQueryable%601>.</span></span>|  
|<span data-ttu-id="42fb3-111">(</span><span class="sxs-lookup"><span data-stu-id="42fb3-111">(</span></span>|<span data-ttu-id="42fb3-112">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="42fb3-112">Required.</span></span> <span data-ttu-id="42fb3-113">Indica l'inizio della proprietà dell'indicizzatore.</span><span class="sxs-lookup"><span data-stu-id="42fb3-113">Denotes the start of the indexer property.</span></span>|  
|`index`|<span data-ttu-id="42fb3-114">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="42fb3-114">Required.</span></span> <span data-ttu-id="42fb3-115">Espressione integer che specifica la posizione in base zero di un elemento della raccolta.</span><span class="sxs-lookup"><span data-stu-id="42fb3-115">An integer expression that specifies the zero-based position of an element of the collection.</span></span>|  
|<span data-ttu-id="42fb3-116">)</span><span class="sxs-lookup"><span data-stu-id="42fb3-116">)</span></span>|<span data-ttu-id="42fb3-117">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="42fb3-117">Required.</span></span> <span data-ttu-id="42fb3-118">Indica la fine della proprietà dell'indicizzatore.</span><span class="sxs-lookup"><span data-stu-id="42fb3-118">Denotes the end of the indexer property.</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="42fb3-119">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="42fb3-119">Return Value</span></span>  
 <span data-ttu-id="42fb3-120">L'oggetto dal percorso specificato nella raccolta, o `Nothing` se l'indice è compreso nell'intervallo.</span><span class="sxs-lookup"><span data-stu-id="42fb3-120">The object from the specified location in the collection, or `Nothing` if the index is out of range.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="42fb3-121">Note</span><span class="sxs-lookup"><span data-stu-id="42fb3-121">Remarks</span></span>  
 <span data-ttu-id="42fb3-122">È possibile utilizzare la proprietà dell'indicizzatore di estensione per accedere ai singoli elementi in una raccolta.</span><span class="sxs-lookup"><span data-stu-id="42fb3-122">You can use the extension indexer property to access individual elements in a collection.</span></span> <span data-ttu-id="42fb3-123">Questa proprietà dell'indicizzatore è in genere utilizzata nell'output di proprietà axis XML.</span><span class="sxs-lookup"><span data-stu-id="42fb3-123">This indexer property is typically used on the output of XML axis properties.</span></span> <span data-ttu-id="42fb3-124">L'elemento figlio XML e proprietà axis descendant XML restituiscono raccolte di <xref:System.Xml.Linq.XElement>oggetti o un valore di attributo.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="42fb3-124">The XML child and XML descendent axis properties return collections of <xref:System.Xml.Linq.XElement> objects or an attribute value.</span></span>  
  
 <span data-ttu-id="42fb3-125">Il [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compilatore converte le proprietà dell'indicizzatore di estensione per le chiamate al`ElementAtOrDefault` metodo.</span><span class="sxs-lookup"><span data-stu-id="42fb3-125">The [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler converts extension indexer properties to calls to the`ElementAtOrDefault` method.</span></span> <span data-ttu-id="42fb3-126">A differenza di un indicizzatore di matrice, il`ElementAtOrDefault` restituisce `Nothing` se l'indice è compreso nell'intervallo.</span><span class="sxs-lookup"><span data-stu-id="42fb3-126">Unlike an array indexer, the`ElementAtOrDefault` method returns `Nothing` if the index is out of range.</span></span> <span data-ttu-id="42fb3-127">Questo comportamento risulta utile quando non è facile determinare il numero di elementi in una raccolta.</span><span class="sxs-lookup"><span data-stu-id="42fb3-127">This behavior is useful when you cannot easily determine the number of elements in a collection.</span></span>  
  
 <span data-ttu-id="42fb3-128">Questa proprietà dell'indicizzatore è simile a una proprietà di estensione per le raccolte che implementano <xref:System.Collections.Generic.IEnumerable%601>o <xref:System.Linq.IQueryable%601>: viene utilizzata solo se la raccolta non dispone di un indicizzatore o una proprietà predefinita.</xref:System.Linq.IQueryable%601> </xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="42fb3-128">This indexer property is like an extension property for collections that implement <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Linq.IQueryable%601>: it is used only if the collection does not have an indexer or a default property.</span></span>  
  
 <span data-ttu-id="42fb3-129">Per accedere al valore del primo elemento in una raccolta di <xref:System.Xml.Linq.XElement>o <xref:System.Xml.Linq.XAttribute>oggetti, è possibile utilizzare il codice XML `Value` proprietà.</xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="42fb3-129">To access the value of the first element in a collection of <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XAttribute> objects, you can use the XML `Value` property.</span></span> <span data-ttu-id="42fb3-130">Per ulteriori informazioni, vedere [proprietà Value XML](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span><span class="sxs-lookup"><span data-stu-id="42fb3-130">For more information, see [XML Value Property](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="42fb3-131">Esempio</span><span class="sxs-lookup"><span data-stu-id="42fb3-131">Example</span></span>  
 <span data-ttu-id="42fb3-132">Nell'esempio seguente viene illustrato come utilizzare l'indicizzatore di estensione per accedere al secondo nodo figlio in una raccolta di <xref:System.Xml.Linq.XElement>oggetti.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="42fb3-132">The following example shows how to use the extension indexer to access the second child node in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="42fb3-133">La raccolta è accessibile tramite la proprietà di asse figlio, che ottiene tutti gli elementi figlio denominati `phone` nel `contact` oggetto.</span><span class="sxs-lookup"><span data-stu-id="42fb3-133">The collection is accessed by using the child axis property, which gets all child elements named `phone` in the `contact` object.</span></span>  
  
 <span data-ttu-id="42fb3-134">[!code-vb[VbXMLSamples&#24;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/extension-indexer-property_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="42fb3-134">[!code-vb[VbXMLSamples#24](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/extension-indexer-property_1.vb)]</span></span>  
  
 <span data-ttu-id="42fb3-135">Questo codice visualizza il testo seguente:</span><span class="sxs-lookup"><span data-stu-id="42fb3-135">This code displays the following text:</span></span>  
  
 `Second phone number: 425-555-0145`  
  
## <a name="see-also"></a><span data-ttu-id="42fb3-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="42fb3-136">See Also</span></span>  
 <span data-ttu-id="42fb3-137"><xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="42fb3-137"><xref:System.Xml.Linq.XElement></span></span>   
<span data-ttu-id="42fb3-138"> [Proprietà Axis XML](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md) </span><span class="sxs-lookup"><span data-stu-id="42fb3-138"> [XML Axis Properties](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md) </span></span>  
<span data-ttu-id="42fb3-139"> [Valori letterali XML](../../../visual-basic/language-reference/xml-literals/index.md) </span><span class="sxs-lookup"><span data-stu-id="42fb3-139"> [XML Literals](../../../visual-basic/language-reference/xml-literals/index.md) </span></span>  
<span data-ttu-id="42fb3-140"> [Creazione di XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md) </span><span class="sxs-lookup"><span data-stu-id="42fb3-140"> [Creating XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md) </span></span>  
<span data-ttu-id="42fb3-141"> [Proprietà Value XML](../../../visual-basic/language-reference/xml-axis/xml-value-property.md)</span><span class="sxs-lookup"><span data-stu-id="42fb3-141"> [XML Value Property](../../../visual-basic/language-reference/xml-axis/xml-value-property.md)</span></span>
