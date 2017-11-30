---
title: Recupero di nodi ordinati in base all'indice
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
ms.assetid: 5412c90f-2703-4aa8-a9c4-1b8a35183c37
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 13d3077b1536d4e96cb9e4f1f09313dd793a906e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="ordered-node-retrieval-by-index"></a><span data-ttu-id="eee67-102">Recupero di nodi ordinati in base all'indice</span><span class="sxs-lookup"><span data-stu-id="eee67-102">Ordered Node Retrieval by Index</span></span>
<span data-ttu-id="eee67-103">Il World Wide Web Consortium (W3C) XML oggetto modello DOM (Document) descrive anche un NodeList, che è in grado di gestire un elenco ordinato di nodi, mentre il set non ordinato di competenza di **XmlNamedNodeMap**.</span><span class="sxs-lookup"><span data-stu-id="eee67-103">The World Wide Web Consortium (W3C) XML Document Object Model (DOM) also describes a NodeList, which has the ability to handle an ordered list of nodes, as opposed to the unordered set handled by the **XmlNamedNodeMap**.</span></span> <span data-ttu-id="eee67-104">Viene chiamato il NodeList di Microsoft .NET Framework **XmlNodeList**.</span><span class="sxs-lookup"><span data-stu-id="eee67-104">The NodeList in the Microsoft .NET Framework is called **XmlNodeList**.</span></span> <span data-ttu-id="eee67-105">Metodi e proprietà che restituiscono un **XmlNodeList** sono:</span><span class="sxs-lookup"><span data-stu-id="eee67-105">Methods and properties that return an **XmlNodeList** are:</span></span>  
  
-   <span data-ttu-id="eee67-106">XmlNode.ChildNodes</span><span class="sxs-lookup"><span data-stu-id="eee67-106">XmlNode.ChildNodes</span></span>  
  
-   <span data-ttu-id="eee67-107">XmlDocument.GetElementsByTagName</span><span class="sxs-lookup"><span data-stu-id="eee67-107">XmlDocument.GetElementsByTagName</span></span>  
  
-   <span data-ttu-id="eee67-108">XmlElement.GetElementsByTagName</span><span class="sxs-lookup"><span data-stu-id="eee67-108">XmlElement.GetElementsByTagName</span></span>  
  
-   <span data-ttu-id="eee67-109">XmlNode.SelectNodes</span><span class="sxs-lookup"><span data-stu-id="eee67-109">XmlNode.SelectNodes</span></span>  
  
 <span data-ttu-id="eee67-110">Il **XmlNodeList** ha un **conteggio** proprietà che può essere usato per scrivere cicli per scorrere i nodi di **XmlNodeList**, come illustrato nell'esempio di codice seguente:</span><span class="sxs-lookup"><span data-stu-id="eee67-110">The **XmlNodeList** has a **Count** property that can be used to write loops to iterate over the nodes in the **XmlNodeList**, as shown in the following code sample:</span></span>  
  
```vb  
Dim doc as XmlDocument = new XmlDocument()  
   doc.Load("books.xml")  
  
    ' Retrieve all book titles.  
    Dim root as XmlElement = doc.DocumentElement  
    Dim elemList as XmlNodeList = root.GetElementsByTagName("title")  
    Dim i as integer  
    for i=0  to elemList.Count-1  
        ' Display all book titles in the Node List.  
        Console.WriteLine(elemList.ItemOf(i).InnerXml)  
    next  
```  
  
```csharp  
XmlDocument doc = new XmlDocument();  
doc.Load("books.xml");  
// Retrieve all book titles.  
XmlElement root = doc.DocumentElement;  
XmlNodeList elemList = root.GetElementsByTagName("title");  
for (int i=0; i < elemList.Count; i++)  
{     
   // Display all book titles in the Node List.  
   Console.WriteLine(elemList[i].InnerXml);  
}   
```  
  
 <span data-ttu-id="eee67-111">Oltre al **conteggio** proprietà, è presente un **GetEnumerator** metodo che fornisce, `foreach` sulla raccolta di nodi di iterazione di stile di **XmlNodeList**.</span><span class="sxs-lookup"><span data-stu-id="eee67-111">In addition to the **Count** property, there is a **GetEnumerator** method that provides a, `foreach` style iteration over the collection of nodes in the **XmlNodeList**.</span></span> <span data-ttu-id="eee67-112">Nell'esempio di codice seguente viene illustrato l'uso dell'istruzione `foreach`:</span><span class="sxs-lookup"><span data-stu-id="eee67-112">The following code example shows the use of the `foreach` statement.</span></span>  
  
```vb  
Dim doc As New XmlDocument()  
doc.Load("books.xml")  
  
' Get book titles.  
Dim root As XmlElement = doc.DocumentElement  
Dim elemList As XmlNodeList = root.GetElementsByTagName("title")  
Dim ienum As IEnumerator = elemList.GetEnumerator()  
' Loop over the XmlNodeList using the enumerator ienum          
While ienum.MoveNext()  
    ' Display the book title.  
    Dim title As XmlNode = CType(ienum.Current, XmlNode)  
    Console.WriteLine(title.InnerText)  
End While  
```  
  
```csharp  
{  
     XmlDocument doc = new XmlDocument();  
     doc.Load("books.xml");  
  
     // Get book titles.  
     XmlElement root = doc.DocumentElement;  
     XmlNodeList elemList = root.GetElementsByTagName("title");  
     IEnumerator ienum = elemList.GetEnumerator();    
     // Loop over the XmlNodeList using the enumerator ienum          
     while (ienum.MoveNext())  
     {  
          // Display the book title.  
           XmlNode title = (XmlNode) ienum.Current;  
           Console.WriteLine(title.InnerText);  
     }  
  }  
```  
  
 <span data-ttu-id="eee67-113">Per ulteriori informazioni sui metodi e proprietà disponibili sul **XmlNodeList**, vedere <xref:System.Xml.XmlNodeList>.</span><span class="sxs-lookup"><span data-stu-id="eee67-113">For more information on the methods and properties available on the **XmlNodeList**, see <xref:System.Xml.XmlNodeList>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eee67-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eee67-114">See Also</span></span>  
 [<span data-ttu-id="eee67-115">XML Document Object Model (DOM)</span><span class="sxs-lookup"><span data-stu-id="eee67-115">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
