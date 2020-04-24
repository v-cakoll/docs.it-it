---
title: Recupero di nodi non ordinati in base al nome o all'indice
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 2038a90b-92af-4a0a-baaa-08e688d95194
ms.openlocfilehash: 55ea0e31bb8a2863dc0e0eb30f6ca5700c3110b8
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "78155737"
---
# <a name="unordered-node-retrieval-by-name-or-index"></a><span data-ttu-id="ec923-102">Recupero di nodi non ordinati in base al nome o all'indice</span><span class="sxs-lookup"><span data-stu-id="ec923-102">Unordered Node Retrieval by Name or Index</span></span>
<span data-ttu-id="ec923-103">**XmlNamedNodeMap** è descritto nella specifica W3C (World Wide Web Consortium) come NamedNodeMap. La sua funzione è quella di gestire un set di nodi non ordinato con la capacità di fare riferimento ai nodi in base al nome o all'indice.</span><span class="sxs-lookup"><span data-stu-id="ec923-103">The **XmlNamedNodeMap** is described in the World Wide Web Consortium (W3C) specification as the NamedNodeMap and is required to handle an unordered set of nodes with the ability to reference nodes by their name or index.</span></span> <span data-ttu-id="ec923-104">L'unico modo per accedere a un oggetto **XmlNamedNodeMap** è con la restituzione di un oggetto **XmlNamedNodeMap** tramite un metodo o una proprietà.</span><span class="sxs-lookup"><span data-stu-id="ec923-104">The only way you have access to an **XmlNamedNodeMap** is when an **XmlNamedNodeMap** is returned through a method or property.</span></span> <span data-ttu-id="ec923-105">Sono disponibili tre metodi o proprietà che restituiscono **XmlNamedNodeMap**:</span><span class="sxs-lookup"><span data-stu-id="ec923-105">There are three methods or properties that return an **XmlNamedNodeMap**:</span></span>  
  
- <span data-ttu-id="ec923-106">XmlElement.Attributes</span><span class="sxs-lookup"><span data-stu-id="ec923-106">XmlElement.Attributes</span></span>  
  
- <span data-ttu-id="ec923-107">XmlDocumentType.Entities</span><span class="sxs-lookup"><span data-stu-id="ec923-107">XmlDocumentType.Entities</span></span>  
  
- <span data-ttu-id="ec923-108">XmlDocumentType.Notations</span><span class="sxs-lookup"><span data-stu-id="ec923-108">XmlDocumentType.Notations</span></span>  
  
 <span data-ttu-id="ec923-109">La proprietà **XmlDocumentType.Entities**, ad esempio, consente di recuperare la raccolta di nodi **XmlEntity** presenti nella dichiarazione del tipo di documento.</span><span class="sxs-lookup"><span data-stu-id="ec923-109">For example, the **XmlDocumentType.Entities** property gets the collection of **XmlEntity** nodes declared in the document type declaration.</span></span> <span data-ttu-id="ec923-110">Questa raccolta viene restituita come **XmlNamedNodeMap** ed è possibile scorrerla con la proprietà **Count** e visualizzare le informazioni relative all'entità.</span><span class="sxs-lookup"><span data-stu-id="ec923-110">This collection is returned as an **XmlNamedNodeMap**, and you can iterate through the collection with the use of the **Count** property and display entity information.</span></span> <span data-ttu-id="ec923-111">Per un esempio di iterazione tramite **XmlNamedNodeMap**, vedere <xref:System.Xml.XmlDocumentType.Entities%2A>.</span><span class="sxs-lookup"><span data-stu-id="ec923-111">For an example of iterating through an **XmlNamedNodeMap**, see <xref:System.Xml.XmlDocumentType.Entities%2A>.</span></span>  
  
 <span data-ttu-id="ec923-112">**XmlAttributeCollection** deriva da **XmlNamedNodeMap** e solo gli attributi sono modificabili, mentre le notazioni e le entità sono in sola lettura.</span><span class="sxs-lookup"><span data-stu-id="ec923-112">The **XmlAttributeCollection** is derived from **XmlNamedNodeMap** and only attributes are modifiable, while notations and entities are read-only.</span></span> <span data-ttu-id="ec923-113">Usando **XmlNamedNodeMap** per gli attributi, è possibile ottenere nodi per quegli attributi in base ai relativi nomi XML.</span><span class="sxs-lookup"><span data-stu-id="ec923-113">Using the **XmlNamedNodeMap** for the attributes, you can get nodes for those attributes based on their XML names.</span></span> <span data-ttu-id="ec923-114">Questo rappresenta un metodo semplice per la modifica della raccolta di attributi su un nodo di elemento,</span><span class="sxs-lookup"><span data-stu-id="ec923-114">This provides an easy method for manipulating the collection of attributes on an element node.</span></span> <span data-ttu-id="ec923-115">a differenza di **XmlNodeList**, che implementa anch'esso l'interfaccia **IEnumerable**, ma con una funzione di accesso all'indice anziché una stringa.</span><span class="sxs-lookup"><span data-stu-id="ec923-115">This can be contrasted directly with **XmlNodeList**, which also implements the **IEnumerable** interface, but with an index accessor rather than a string.</span></span> <span data-ttu-id="ec923-116">I metodi **RemoveNamedItem** e **SetNamedItem** vengono usati solo in relazione a **XmlAttributeCollection**.</span><span class="sxs-lookup"><span data-stu-id="ec923-116">The **RemoveNamedItem** and **SetNamedItem** methods are only used against an **XmlAttributeCollection**.</span></span> <span data-ttu-id="ec923-117">L'aggiunta o la rimozione da una raccolta di attributi, sia tramite l'implementazione **AttributeCollection** o **XmlNamedNodeMap**, modifica la raccolta di attributi per l'elemento.</span><span class="sxs-lookup"><span data-stu-id="ec923-117">Adding or removing from an attribute collection, whether using the **AttributeCollection** or the **XmlNamedNodeMap** implementation, modifies the attribute collection on the element.</span></span> <span data-ttu-id="ec923-118">Nell'esempio di codice seguente viene illustrato come spostare un attributo e come crearne uno nuovo.</span><span class="sxs-lookup"><span data-stu-id="ec923-118">The following code example shows how to move an attribute and create a new attribute.</span></span>  
  
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
  
 <span data-ttu-id="ec923-119">Per un altro esempio di codice che illustra la rimozione di un attributo da **AttributeCollection**, vedere [Metodo XmlNamedNodeMap.RemoveNamedItem](xref:System.Xml.XmlNamedNodeMap.RemoveNamedItem%2A).</span><span class="sxs-lookup"><span data-stu-id="ec923-119">To see an additional code example which shows an attribute being removed from an **AttributeCollection**, see [XmlNamedNodeMap.RemoveNamedItem Method](xref:System.Xml.XmlNamedNodeMap.RemoveNamedItem%2A).</span></span> <span data-ttu-id="ec923-120">Per altre informazioni sui metodi e sulle proprietà, vedere [Membri XmlNamedNodeMap](xref:System.Xml.XmlNamedNodeMap).</span><span class="sxs-lookup"><span data-stu-id="ec923-120">For more information on the methods and properties, see [XmlNamedNodeMap Members](xref:System.Xml.XmlNamedNodeMap).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec923-121">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="ec923-121">See also</span></span>

- [<span data-ttu-id="ec923-122">XML DOM (Document Object Model)</span><span class="sxs-lookup"><span data-stu-id="ec923-122">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
