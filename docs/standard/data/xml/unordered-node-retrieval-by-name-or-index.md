---
title: Recupero di nodi non ordinati in base al nome o all'indice
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
ms.assetid: 2038a90b-92af-4a0a-baaa-08e688d95194
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a8bea8f373dced08fd7a2a828255a593533df9d7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="unordered-node-retrieval-by-name-or-index"></a><span data-ttu-id="954f7-102">Recupero di nodi non ordinati in base al nome o all'indice</span><span class="sxs-lookup"><span data-stu-id="954f7-102">Unordered Node Retrieval by Name or Index</span></span>
<span data-ttu-id="954f7-103">Il **XmlNamedNodeMap** è descritto nella specifica del World Wide Web Consortium (W3C) come NamedNodeMap che sia necessaria per gestire un set non ordinato di nodi con la possibilità di fare riferimento ai nodi tramite il nome o l'indice.</span><span class="sxs-lookup"><span data-stu-id="954f7-103">The **XmlNamedNodeMap** is described in the World Wide Web Consortium (W3C) specification as the NamedNodeMap and is required to handle an unordered set of nodes with the ability to reference nodes by their name or index.</span></span> <span data-ttu-id="954f7-104">L'unico modo si ha accesso a un **XmlNamedNodeMap** quando un **XmlNamedNodeMap** viene restituito tramite un metodo o proprietà.</span><span class="sxs-lookup"><span data-stu-id="954f7-104">The only way you have access to an **XmlNamedNodeMap** is when an **XmlNamedNodeMap** is returned through a method or property.</span></span> <span data-ttu-id="954f7-105">Sono disponibili tre metodi o proprietà che restituiscono un **XmlNamedNodeMap**:</span><span class="sxs-lookup"><span data-stu-id="954f7-105">There are three methods or properties that return an **XmlNamedNodeMap**:</span></span>  
  
-   <span data-ttu-id="954f7-106">XmlElement.Attributes</span><span class="sxs-lookup"><span data-stu-id="954f7-106">XmlElement.Attributes</span></span>  
  
-   <span data-ttu-id="954f7-107">XmlDocumentType.Entities</span><span class="sxs-lookup"><span data-stu-id="954f7-107">XmlDocumentType.Entities</span></span>  
  
-   <span data-ttu-id="954f7-108">XmlDocumentType.Notations</span><span class="sxs-lookup"><span data-stu-id="954f7-108">XmlDocumentType.Notations</span></span>  
  
 <span data-ttu-id="954f7-109">Ad esempio, il **XmlDocumentType** proprietà ottiene la raccolta di **XmlEntity** nodi dichiarato nella dichiarazione del tipo di documento.</span><span class="sxs-lookup"><span data-stu-id="954f7-109">For example, the **XmlDocumentType.Entities** property gets the collection of **XmlEntity** nodes declared in the document type declaration.</span></span> <span data-ttu-id="954f7-110">Questa raccolta viene restituita come un **XmlNamedNodeMap**, ed è possibile scorrere la raccolta con l'uso del **conteggio** informazioni sulle entità di proprietà e la visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="954f7-110">This collection is returned as an **XmlNamedNodeMap**, and you can iterate through the collection with the use of the **Count** property and display entity information.</span></span> <span data-ttu-id="954f7-111">Per un esempio di un'iterazione attraverso un **XmlNamedNodeMap**, vedere <xref:System.Xml.XmlDocumentType.Entities%2A>.</span><span class="sxs-lookup"><span data-stu-id="954f7-111">For an example of iterating through an **XmlNamedNodeMap**, see <xref:System.Xml.XmlDocumentType.Entities%2A>.</span></span>  
  
 <span data-ttu-id="954f7-112">Il **XmlAttributeCollection** è derivato da **XmlNamedNodeMap** e solo gli attributi sono modificabili, mentre le notazioni e le entità sono di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="954f7-112">The **XmlAttributeCollection** is derived from **XmlNamedNodeMap** and only attributes are modifiable, while notations and entities are read-only.</span></span> <span data-ttu-id="954f7-113">Utilizzo di **XmlNamedNodeMap** per gli attributi, è possibile ottenere nodi per quegli attributi in base ai relativi nomi XML.</span><span class="sxs-lookup"><span data-stu-id="954f7-113">Using the **XmlNamedNodeMap** for the attributes, you can get nodes for those attributes based on their XML names.</span></span> <span data-ttu-id="954f7-114">Questo rappresenta un metodo semplice per la modifica della raccolta di attributi su un nodo di elemento,</span><span class="sxs-lookup"><span data-stu-id="954f7-114">This provides an easy method for manipulating the collection of attributes on an element node.</span></span> <span data-ttu-id="954f7-115">Questo può essere confrontato direttamente con **XmlNodeList**, che implementa anche il **IEnumerable** interfaccia, ma con una funzione di accesso di indice anziché una stringa.</span><span class="sxs-lookup"><span data-stu-id="954f7-115">This can be contrasted directly with **XmlNodeList**, which also implements the **IEnumerable** interface, but with an index accessor rather than a string.</span></span> <span data-ttu-id="954f7-116">Il **RemoveNamedItem** e **SetNamedItem** metodi vengono utilizzati solo con un **XmlAttributeCollection**.</span><span class="sxs-lookup"><span data-stu-id="954f7-116">The **RemoveNamedItem** and **SetNamedItem** methods are only used against an **XmlAttributeCollection**.</span></span> <span data-ttu-id="954f7-117">Aggiunta o rimozione da una raccolta di attributi, sia tramite la **AttributeCollection** o **XmlNamedNodeMap** implementazione, modifica la raccolta di attributi sull'elemento.</span><span class="sxs-lookup"><span data-stu-id="954f7-117">Adding or removing from an attribute collection, whether using the **AttributeCollection** or the **XmlNamedNodeMap** implementation, modifies the attribute collection on the element.</span></span> <span data-ttu-id="954f7-118">Nell'esempio di codice seguente viene illustrato come spostare un attributo e come crearne uno nuovo.</span><span class="sxs-lookup"><span data-stu-id="954f7-118">The following code example shows how to move an attribute and create a new attribute.</span></span>  
  
```vb  
Imports System  
Imports System.Xml  
  
Class test  
  
    Public Shared Sub Main()  
        Dim doc As New XmlDocument()  
        doc.LoadXml("<root> <child1 attr1='val1' attr2='val2'> text1 </child1> <child2 attr3='val3'> text2 </child2> </root> ")  
  
        ' Get the attributes of node "child2 "  
        Dim ac As XmlAttributeCollection = doc.DocumentElement.ChildNodes(1).Attributes  
  
        ' Print out the number of attributes and their names.  
        Console.WriteLine(("Number of Attributes: " + ac.Count))  
        Dim i As Integer  
        For i = 0 To ac.Count - 1  
            Console.WriteLine((i + 1 + ".  Attribute Name: '" + ac(i).Name + "'  Attribute Value:  '" + ac(i).Value + "'"))  
        Next i  
        ' Get the 'attr1' from child1.  
        Dim attr As XmlAttribute = doc.DocumentElement.ChildNodes(0).Attributes(0)  
  
        ' Add this attribute to the attributecollection "ac".  
        ac.SetNamedItem(attr)  
  
        ''attr1' will be removed from 'child1' and added to 'child2'.  
        ' Print out the number of attributes and their names.  
        Console.WriteLine(("Number of Attributes: " + ac.Count))  
  
        For i = 0 To ac.Count - 1  
            Console.WriteLine((i + 1 + ".  Attribute Name: '" + ac(i).Name + "'  Attribute Value:  '" + ac(i).Value + "'"))  
        Next i  
        ' Create a new attribute and add to the collection.  
        Dim attr2 As XmlAttribute = doc.CreateAttribute("attr4")  
        attr2.Value = "val4"  
        ac.SetNamedItem(attr2)  
  
        ' Print out the number of attributes and their names.  
        Console.WriteLine(("Number of Attributes: " + ac.Count))  
  
        For i = 0 To ac.Count - 1  
            Console.WriteLine((i + 1 + ".  Attribute Name: '" + ac(i).Name + "'  Attribute Value:  '" + ac(i).Value + "'"))  
        Next i  
    End Sub 'Main  
End Class 'test  
```  
  
```csharp  
using System;  
using System.Xml;  
class test {  
    public static void Main() {  
        XmlDocument doc = new XmlDocument();  
        doc.LoadXml( "<root> <child1 attr1='val1' attr2='val2'> text1 </child1> <child2 attr3='val3'> text2 </child2> </root> " );  
  
        // Get the attributes of node "child2"  
        XmlAttributeCollection ac = doc.DocumentElement.ChildNodes[1].Attributes;  
  
        // Print out the number of attributes and their names.  
        Console.WriteLine( "Number of Attributes: "+ac.Count );  
        for( int i = 0; i < ac.Count; i++ )  
            Console.WriteLine( (i+1) + ".  Attribute Name: '" +ac[i].Name+ "'  Attribute Value:  '"+ ac[i].Value +"'" );   
  
        // Get the 'attr1' from child1.  
        XmlAttribute attr = doc.DocumentElement.ChildNodes[0].Attributes[0];  
  
        // Add this attribute to the attributecollection "ac".  
        ac.SetNamedItem( attr );  
  
        // 'attr1' will be removed from 'child1' and added to 'child2'.  
        // Print out the number of attributes and their names.  
        Console.WriteLine( "Number of Attributes: "+ac.Count );          
        for( int i = 0; i < ac.Count; i++ )  
            Console.WriteLine( (i+1) + ".  Attribute Name: '" +ac[i].Name+ "'  Attribute Value:  '"+ ac[i].Value +"'" );   
  
        // Create a new attribute and add to the collection.  
        XmlAttribute attr2 = doc.CreateAttribute( "attr4" );  
        attr2.Value = "val4";  
        ac.SetNamedItem( attr2 );  
  
        // Print out the number of attributes and their names.  
        Console.WriteLine( "Number of Attributes: "+ac.Count );          
        for( int i = 0; i < ac.Count; i++ )  
            Console.WriteLine( (i+1) + ".  Attribute Name: '" +ac[i].Name+ "'  Attribute Value:  '"+ ac[i].Value +"'" );           
  
    }  
}  
```  
  
 <span data-ttu-id="954f7-119">Per vedere un esempio di codice aggiuntivo che illustra un attributo da rimuovere da un **AttributeCollection**, vedere [metodo XmlNamedNodeMap RemoveNamedItem](Overload:System.Xml.XmlNamedNodeMap.RemoveNamedItem).</span><span class="sxs-lookup"><span data-stu-id="954f7-119">To see an additional code example which shows an attribute being removed from an **AttributeCollection**, see [XmlNamedNodeMap.RemoveNamedItem Method](Overload:System.Xml.XmlNamedNodeMap.RemoveNamedItem).</span></span> <span data-ttu-id="954f7-120">Per ulteriori informazioni sui metodi e proprietà, vedere [membri XmlNameNodeMap](AllMembers.T:System.Xml.XmlNamedNodeMap).</span><span class="sxs-lookup"><span data-stu-id="954f7-120">For more information on the methods and properties, see [XmlNamedNodeMap Members](AllMembers.T:System.Xml.XmlNamedNodeMap).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="954f7-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="954f7-121">See Also</span></span>  
 [<span data-ttu-id="954f7-122">XML Document Object Model (DOM)</span><span class="sxs-lookup"><span data-stu-id="954f7-122">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
