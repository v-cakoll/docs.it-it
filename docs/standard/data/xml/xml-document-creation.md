---
title: Creazione di documenti XML
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 877e9c62-b082-4bfb-bc5b-f47297eb30ef
ms.openlocfilehash: 577d353a30c986d198140b4596ae1a7e199ddd6e
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84291981"
---
# <a name="xml-document-creation"></a><span data-ttu-id="e0ded-102">Creazione di documenti XML</span><span class="sxs-lookup"><span data-stu-id="e0ded-102">XML Document Creation</span></span>
<span data-ttu-id="e0ded-103">Sono disponibili due metodi per creare un documento XML:</span><span class="sxs-lookup"><span data-stu-id="e0ded-103">There are two ways to create an XML document.</span></span> <span data-ttu-id="e0ded-104">uno di questi consiste nel creare un **XmlDocument** senza parametri;</span><span class="sxs-lookup"><span data-stu-id="e0ded-104">One way is to create an **XmlDocument** with no parameters.</span></span> <span data-ttu-id="e0ded-105">l'altro consiste nel creare un **XmlDocument** e passarlo al documento XmlNameTable come parametro.</span><span class="sxs-lookup"><span data-stu-id="e0ded-105">The other way is to create an **XmlDocument** and pass it an XmlNameTable as a parameter.</span></span> <span data-ttu-id="e0ded-106">Nell'esempio seguente viene illustrata la creazione di un nuovo **XmlDocument** vuoto senza l'uso di parametri.</span><span class="sxs-lookup"><span data-stu-id="e0ded-106">The following example shows how to create a new, empty **XmlDocument** using no parameters.</span></span>  
  
```vb  
Dim doc As New XmlDocument()  
```  
  
```csharp  
XmlDocument doc = new XmlDocument();  
```  
  
 <span data-ttu-id="e0ded-107">Una volta creato un documento, è possibile caricarlo con i dati da una stringa, un flusso, un URL, un lettore di testo o una classe derivata **XmlReader** usando il metodo **Load**.</span><span class="sxs-lookup"><span data-stu-id="e0ded-107">Once a document is created, you can load it with data from a string, stream, URL, text reader, or an **XmlReader** derived class using the **Load** method.</span></span> <span data-ttu-id="e0ded-108">È disponibile anche un altro metodo di caricamento, **LoadXML**, con il quale è possibile leggere il codice XML da una stringa.</span><span class="sxs-lookup"><span data-stu-id="e0ded-108">There is also another load method, the **LoadXML** method, which reads XML from a string.</span></span> <span data-ttu-id="e0ded-109">Per altre informazioni sui diversi metodi **Load**, vedere [Lettura di un documento XML nel DOM](reading-an-xml-document-into-the-dom.md).</span><span class="sxs-lookup"><span data-stu-id="e0ded-109">For more information on the various **Load** methods, see [Reading an XML Document into the DOM](reading-an-xml-document-into-the-dom.md).</span></span>  
  
 <span data-ttu-id="e0ded-110">È disponibile una classe denominata **XmlNameTable**.</span><span class="sxs-lookup"><span data-stu-id="e0ded-110">There is a class called the **XmlNameTable**.</span></span> <span data-ttu-id="e0ded-111">Questa è una tabella di oggetti stringa atomici.</span><span class="sxs-lookup"><span data-stu-id="e0ded-111">This class is a table of atomized string objects.</span></span> <span data-ttu-id="e0ded-112">Tale tabella fornisce al parser XML un mezzo efficiente per usare lo stesso oggetto stringa per tutti i nomi degli attributi e degli elementi ripetuti in un documento XML.</span><span class="sxs-lookup"><span data-stu-id="e0ded-112">This table provides an efficient means for the XML parser to use the same string object for all repeated element and attribute names in an XML document.</span></span> <span data-ttu-id="e0ded-113">Quando un documento viene creato nel modo illustrato in precedenza e caricato con i nomi di attributi ed elementi, viene creata automaticamente una **XmlNameTable**.</span><span class="sxs-lookup"><span data-stu-id="e0ded-113">An **XmlNameTable** is automatically created when a document is created as shown above and is loaded with attribute and element names when the document is loaded.</span></span> <span data-ttu-id="e0ded-114">Se è già disponibile un documento con una tabella di nomi utili in un altro documento, è possibile creare un nuovo documento usando il metodo **Load** che accetta **XmlNameTable** come parametro.</span><span class="sxs-lookup"><span data-stu-id="e0ded-114">If you already have a document with a name table, and those names would be useful in another document, you can create a new document using the **Load** method that takes an **XmlNameTable** as a parameter.</span></span> <span data-ttu-id="e0ded-115">Quando viene creato con questo metodo, il documento utilizzerà l'**XmlNameTable** disponibile con tutti gli attributi e gli elementi già caricati dall'altro documento</span><span class="sxs-lookup"><span data-stu-id="e0ded-115">When the document is created with this method, it uses the existing **XmlNameTable** with all the attributes and elements already loaded into it from the other document.</span></span> <span data-ttu-id="e0ded-116">e questa potrà essere usata per paragonare i nomi di elementi e attributi in maniera efficiente.</span><span class="sxs-lookup"><span data-stu-id="e0ded-116">It can be used for efficiently comparing element and attribute names.</span></span> <span data-ttu-id="e0ded-117">Per altre informazioni sull'**XmlNameTable**, vedere [Confronto di oggetti con XmlNameTable](object-comparison-using-xmlnametable.md).</span><span class="sxs-lookup"><span data-stu-id="e0ded-117">For more information on the **XmlNameTable**, see [Object Comparison Using XmlNameTable](object-comparison-using-xmlnametable.md).</span></span> <span data-ttu-id="e0ded-118">Per riferimento, vedere <xref:System.Xml.XmlNameTable>.</span><span class="sxs-lookup"><span data-stu-id="e0ded-118">For reference, see <xref:System.Xml.XmlNameTable>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0ded-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e0ded-119">See also</span></span>

- [<span data-ttu-id="e0ded-120">XML DOM (Document Object Model)</span><span class="sxs-lookup"><span data-stu-id="e0ded-120">XML Document Object Model (DOM)</span></span>](xml-document-object-model-dom.md)
