---
title: Creazione di documenti XML
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 877e9c62-b082-4bfb-bc5b-f47297eb30ef
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5a0806e34cfbf7c8e0b5ba995ca4876b8d10405e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="xml-document-creation"></a><span data-ttu-id="587f3-102">Creazione di documenti XML</span><span class="sxs-lookup"><span data-stu-id="587f3-102">XML Document Creation</span></span>
<span data-ttu-id="587f3-103">Sono disponibili due metodi per creare un documento XML:</span><span class="sxs-lookup"><span data-stu-id="587f3-103">There are two ways to create an XML document.</span></span> <span data-ttu-id="587f3-104">Un modo consiste nel creare un **XmlDocument** senza parametri.</span><span class="sxs-lookup"><span data-stu-id="587f3-104">One way is to create an **XmlDocument** with no parameters.</span></span> <span data-ttu-id="587f3-105">L'altro consiste nel creare un **XmlDocument** e passare al documento XmlNameTable come parametro.</span><span class="sxs-lookup"><span data-stu-id="587f3-105">The other way is to create an **XmlDocument** and pass it an XmlNameTable as a parameter.</span></span> <span data-ttu-id="587f3-106">Nell'esempio seguente viene illustrato come creare un nuovo oggetto vuoto **XmlDocument** senza parametri.</span><span class="sxs-lookup"><span data-stu-id="587f3-106">The following example shows how to create a new, empty **XmlDocument** using no parameters.</span></span>  
  
```vb  
Dim doc As New XmlDocument()  
```  
  
```csharp  
XmlDocument doc = new XmlDocument();  
```  
  
 <span data-ttu-id="587f3-107">Dopo aver creato un documento, è possibile caricare i dati da una stringa, flusso, un URL, il lettore di testo, o un **XmlReader** derivata della classe utilizzando il **caricare** metodo.</span><span class="sxs-lookup"><span data-stu-id="587f3-107">Once a document is created, you can load it with data from a string, stream, URL, text reader, or an **XmlReader** derived class using the **Load** method.</span></span> <span data-ttu-id="587f3-108">È inoltre disponibile un altro metodo di caricamento, la **LoadXML** metodo, che legge codice XML da una stringa.</span><span class="sxs-lookup"><span data-stu-id="587f3-108">There is also another load method, the **LoadXML** method, which reads XML from a string.</span></span> <span data-ttu-id="587f3-109">Per ulteriori informazioni sui vari **carico** metodi, vedere [lettura di un documento XML nel DOM](../../../../docs/standard/data/xml/reading-an-xml-document-into-the-dom.md).</span><span class="sxs-lookup"><span data-stu-id="587f3-109">For more information on the various **Load** methods, see [Reading an XML Document into the DOM](../../../../docs/standard/data/xml/reading-an-xml-document-into-the-dom.md).</span></span>  
  
 <span data-ttu-id="587f3-110">È una classe denominata la **XmlNameTable**.</span><span class="sxs-lookup"><span data-stu-id="587f3-110">There is a class called the **XmlNameTable**.</span></span> <span data-ttu-id="587f3-111">Questa è una tabella di oggetti stringa atomici.</span><span class="sxs-lookup"><span data-stu-id="587f3-111">This class is a table of atomized string objects.</span></span> <span data-ttu-id="587f3-112">Tale tabella fornisce al parser XML un mezzo efficiente per usare lo stesso oggetto stringa per tutti i nomi degli attributi e degli elementi ripetuti in un documento XML.</span><span class="sxs-lookup"><span data-stu-id="587f3-112">This table provides an efficient means for the XML parser to use the same string object for all repeated element and attribute names in an XML document.</span></span> <span data-ttu-id="587f3-113">Un **XmlNameTable** viene creata automaticamente quando un documento viene creato come illustrato in precedenza e viene caricato con i nomi di elemento e attributo quando il documento viene caricato.</span><span class="sxs-lookup"><span data-stu-id="587f3-113">An **XmlNameTable** is automatically created when a document is created as shown above and is loaded with attribute and element names when the document is loaded.</span></span> <span data-ttu-id="587f3-114">Se si dispone già di un documento con una tabella, di tali nomi utili in un altro documento, è possibile creare un nuovo documento usando il **carico** metodo che accetta un **XmlNameTable** come parametro.</span><span class="sxs-lookup"><span data-stu-id="587f3-114">If you already have a document with a name table, and those names would be useful in another document, you can create a new document using the **Load** method that takes an **XmlNameTable** as a parameter.</span></span> <span data-ttu-id="587f3-115">Quando il documento viene creato con questo metodo, utilizzerà il **XmlNameTable** con tutti gli attributi e gli elementi già caricati da altro documento.</span><span class="sxs-lookup"><span data-stu-id="587f3-115">When the document is created with this method, it uses the existing **XmlNameTable** with all the attributes and elements already loaded into it from the other document.</span></span> <span data-ttu-id="587f3-116">e questa potrà essere usata per paragonare i nomi di elementi e attributi in maniera efficiente.</span><span class="sxs-lookup"><span data-stu-id="587f3-116">It can be used for efficiently comparing element and attribute names.</span></span> <span data-ttu-id="587f3-117">Per ulteriori informazioni sul **XmlNameTable**, vedere [confronto di oggetti con XmlNameTable](../../../../docs/standard/data/xml/object-comparison-using-xmlnametable.md).</span><span class="sxs-lookup"><span data-stu-id="587f3-117">For more information on the **XmlNameTable**, see [Object Comparison Using XmlNameTable](../../../../docs/standard/data/xml/object-comparison-using-xmlnametable.md).</span></span> <span data-ttu-id="587f3-118">Per riferimento, vedere <xref:System.Xml.XmlNameTable>.</span><span class="sxs-lookup"><span data-stu-id="587f3-118">For reference, see <xref:System.Xml.XmlNameTable>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="587f3-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="587f3-119">See Also</span></span>  
 [<span data-ttu-id="587f3-120">XML Document Object Model (DOM)</span><span class="sxs-lookup"><span data-stu-id="587f3-120">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
