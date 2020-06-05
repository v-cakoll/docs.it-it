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
ms.openlocfilehash: c91061d49e22e648b7bf75a812071b352793abcb
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401342"
---
# <a name="extension-indexer-property-visual-basic"></a><span data-ttu-id="5481e-102">Proprietà dell'indicizzatore di estensione (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5481e-102">Extension Indexer Property (Visual Basic)</span></span>
<span data-ttu-id="5481e-103">Fornisce l'accesso ai singoli elementi di una raccolta.</span><span class="sxs-lookup"><span data-stu-id="5481e-103">Provides access to individual elements in a collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5481e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5481e-104">Syntax</span></span>  
  
```vb  
object(index)  
```  
  
## <a name="parts"></a><span data-ttu-id="5481e-105">Parti</span><span class="sxs-lookup"><span data-stu-id="5481e-105">Parts</span></span>  
  
|<span data-ttu-id="5481e-106">Termine</span><span class="sxs-lookup"><span data-stu-id="5481e-106">Term</span></span>|<span data-ttu-id="5481e-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="5481e-107">Definition</span></span>|  
|---|---|  
|`object`|<span data-ttu-id="5481e-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="5481e-108">Required.</span></span> <span data-ttu-id="5481e-109">Raccolta Queryable.</span><span class="sxs-lookup"><span data-stu-id="5481e-109">A queryable collection.</span></span> <span data-ttu-id="5481e-110">Ovvero una raccolta che implementa <xref:System.Collections.Generic.IEnumerable%601> o <xref:System.Linq.IQueryable%601> .</span><span class="sxs-lookup"><span data-stu-id="5481e-110">That is, a collection that implements <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Linq.IQueryable%601>.</span></span>|  
|<span data-ttu-id="5481e-111">(</span><span class="sxs-lookup"><span data-stu-id="5481e-111">(</span></span>|<span data-ttu-id="5481e-112">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="5481e-112">Required.</span></span> <span data-ttu-id="5481e-113">Indica l'inizio della proprietà dell'indicizzatore.</span><span class="sxs-lookup"><span data-stu-id="5481e-113">Denotes the start of the indexer property.</span></span>|  
|`index`|<span data-ttu-id="5481e-114">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="5481e-114">Required.</span></span> <span data-ttu-id="5481e-115">Espressione Integer che specifica la posizione in base zero di un elemento della raccolta.</span><span class="sxs-lookup"><span data-stu-id="5481e-115">An integer expression that specifies the zero-based position of an element of the collection.</span></span>|  
|<span data-ttu-id="5481e-116">)</span><span class="sxs-lookup"><span data-stu-id="5481e-116">)</span></span>|<span data-ttu-id="5481e-117">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="5481e-117">Required.</span></span> <span data-ttu-id="5481e-118">Indica la fine della proprietà dell'indicizzatore.</span><span class="sxs-lookup"><span data-stu-id="5481e-118">Denotes the end of the indexer property.</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="5481e-119">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="5481e-119">Return Value</span></span>  
 <span data-ttu-id="5481e-120">Oggetto dalla posizione specificata nella raccolta o `Nothing` se l'indice non è compreso nell'intervallo.</span><span class="sxs-lookup"><span data-stu-id="5481e-120">The object from the specified location in the collection, or `Nothing` if the index is out of range.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5481e-121">Commenti</span><span class="sxs-lookup"><span data-stu-id="5481e-121">Remarks</span></span>  
 <span data-ttu-id="5481e-122">È possibile usare la proprietà dell'indicizzatore di estensione per accedere ai singoli elementi di una raccolta.</span><span class="sxs-lookup"><span data-stu-id="5481e-122">You can use the extension indexer property to access individual elements in a collection.</span></span> <span data-ttu-id="5481e-123">Questa proprietà dell'indicizzatore viene in genere utilizzata nell'output delle proprietà Axis XML.</span><span class="sxs-lookup"><span data-stu-id="5481e-123">This indexer property is typically used on the output of XML axis properties.</span></span> <span data-ttu-id="5481e-124">Le proprietà dell'asse XML figlio e XML discendente restituiscono raccolte di <xref:System.Xml.Linq.XElement> oggetti o un valore di attributo.</span><span class="sxs-lookup"><span data-stu-id="5481e-124">The XML child and XML descendent axis properties return collections of <xref:System.Xml.Linq.XElement> objects or an attribute value.</span></span>  
  
 <span data-ttu-id="5481e-125">Il compilatore Visual Basic converte le proprietà dell'indicizzatore di estensione in chiamate al `ElementAtOrDefault` metodo.</span><span class="sxs-lookup"><span data-stu-id="5481e-125">The Visual Basic compiler converts extension indexer properties to calls to the `ElementAtOrDefault` method.</span></span> <span data-ttu-id="5481e-126">Diversamente da un indicizzatore di matrici, il `ElementAtOrDefault` metodo restituisce `Nothing` se l'indice non è compreso nell'intervallo.</span><span class="sxs-lookup"><span data-stu-id="5481e-126">Unlike an array indexer, the `ElementAtOrDefault` method returns `Nothing` if the index is out of range.</span></span> <span data-ttu-id="5481e-127">Questo comportamento è utile quando non è possibile determinare facilmente il numero di elementi in una raccolta.</span><span class="sxs-lookup"><span data-stu-id="5481e-127">This behavior is useful when you cannot easily determine the number of elements in a collection.</span></span>  
  
 <span data-ttu-id="5481e-128">Questa proprietà dell'indicizzatore è simile a una proprietà di estensione per le raccolte che implementano <xref:System.Collections.Generic.IEnumerable%601> o <xref:System.Linq.IQueryable%601> : viene utilizzata solo se la raccolta non dispone di un indicizzatore o di una proprietà predefinita.</span><span class="sxs-lookup"><span data-stu-id="5481e-128">This indexer property is like an extension property for collections that implement <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Linq.IQueryable%601>: it is used only if the collection does not have an indexer or a default property.</span></span>  
  
 <span data-ttu-id="5481e-129">Per accedere al valore del primo elemento in una raccolta di <xref:System.Xml.Linq.XElement> oggetti o <xref:System.Xml.Linq.XAttribute> , è possibile usare la proprietà XML `Value` .</span><span class="sxs-lookup"><span data-stu-id="5481e-129">To access the value of the first element in a collection of <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XAttribute> objects, you can use the XML `Value` property.</span></span> <span data-ttu-id="5481e-130">Per ulteriori informazioni, vedere [proprietà del valore XML](xml-value-property.md).</span><span class="sxs-lookup"><span data-stu-id="5481e-130">For more information, see [XML Value Property](xml-value-property.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5481e-131">Esempio</span><span class="sxs-lookup"><span data-stu-id="5481e-131">Example</span></span>  
 <span data-ttu-id="5481e-132">Nell'esempio seguente viene illustrato come utilizzare l'indicizzatore di estensione per accedere al secondo nodo figlio in una raccolta di <xref:System.Xml.Linq.XElement> oggetti.</span><span class="sxs-lookup"><span data-stu-id="5481e-132">The following example shows how to use the extension indexer to access the second child node in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="5481e-133">È possibile accedere alla raccolta utilizzando la proprietà Axis figlio, che ottiene tutti gli elementi figlio denominati `phone` nell' `contact` oggetto.</span><span class="sxs-lookup"><span data-stu-id="5481e-133">The collection is accessed by using the child axis property, which gets all child elements named `phone` in the `contact` object.</span></span>  
  
 [!code-vb[VbXMLSamples#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples11.vb#24)]  
  
 <span data-ttu-id="5481e-134">Questo codice visualizza il testo seguente:</span><span class="sxs-lookup"><span data-stu-id="5481e-134">This code displays the following text:</span></span>  
  
 `Second phone number: 425-555-0145`  
  
## <a name="see-also"></a><span data-ttu-id="5481e-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5481e-135">See also</span></span>

- <xref:System.Xml.Linq.XElement>
- [<span data-ttu-id="5481e-136">Proprietà Axis XML</span><span class="sxs-lookup"><span data-stu-id="5481e-136">XML Axis Properties</span></span>](index.md)
- [<span data-ttu-id="5481e-137">Valori letterali XML</span><span class="sxs-lookup"><span data-stu-id="5481e-137">XML Literals</span></span>](../xml-literals/index.md)
- [<span data-ttu-id="5481e-138">Creazione di XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5481e-138">Creating XML in Visual Basic</span></span>](../../programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="5481e-139">Proprietà Value XML</span><span class="sxs-lookup"><span data-stu-id="5481e-139">XML Value Property</span></span>](xml-value-property.md)
