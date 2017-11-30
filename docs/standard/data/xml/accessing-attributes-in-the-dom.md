---
title: Accesso agli attributi nel DOM
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
ms.assetid: ce2df341-a1a4-4e97-8e1b-cd45b8e3e71e
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a433ec5f83a50aa4fe4b2017a0dac3d2a5e5710c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="accessing-attributes-in-the-dom"></a><span data-ttu-id="49d28-102">Accesso agli attributi nel DOM</span><span class="sxs-lookup"><span data-stu-id="49d28-102">Accessing Attributes in the DOM</span></span>
<span data-ttu-id="49d28-103">Gli attributi sono proprietà dell'elemento, non elementi figlio dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="49d28-103">Attributes are properties of the element, not children of the element.</span></span> <span data-ttu-id="49d28-104">Questa distinzione è importante, a causa dei metodi usati per navigare all'interno dei nodi di pari livello, dei nodi padre e dei nodi figlio nel DOM (Document Object Model) XML.</span><span class="sxs-lookup"><span data-stu-id="49d28-104">This distinction is important because of the methods used to navigate sibling, parent, and child nodes of the XML Document Object Model (DOM).</span></span> <span data-ttu-id="49d28-105">Ad esempio, il **PreviousSibling** e **NextSibling** metodi non vengono utilizzati per passare da un elemento a un attributo o tra gli attributi.</span><span class="sxs-lookup"><span data-stu-id="49d28-105">For example, the **PreviousSibling** and **NextSibling** methods are not used to navigate from an element to an attribute or between attributes.</span></span> <span data-ttu-id="49d28-106">Al contrario, un attributo è una proprietà di un elemento e appartiene a un elemento, ha un **OwnerElement** proprietà e non un **parentNode** proprietà, e dispone di metodi di navigazione distinti.</span><span class="sxs-lookup"><span data-stu-id="49d28-106">Instead, an attribute is a property of an element and is owned by an element, has an **OwnerElement** property and not a **parentNode** property, and has distinct methods of navigation.</span></span>  
  
 <span data-ttu-id="49d28-107">Quando il nodo corrente è un elemento, utilizzare il **HasAttribute** metodo per verificare se esistono eventuali attributi associati all'elemento.</span><span class="sxs-lookup"><span data-stu-id="49d28-107">When the current node is an element, use the **HasAttribute** method to see if there are any attributes associated with the element.</span></span> <span data-ttu-id="49d28-108">Una volta appurato che l'elemento dispone di attributi, sono disponibili diversi metodi per accedere agli attributi.</span><span class="sxs-lookup"><span data-stu-id="49d28-108">Once it is known that an element has attributes, there are multiple methods for accessing attributes.</span></span> <span data-ttu-id="49d28-109">Per recuperare un singolo attributo dall'elemento, è possibile utilizzare il **GetAttribute** e **GetAttributeNode** metodi il **XmlElement** o è possibile ottenere tutti gli attributi in una raccolta.</span><span class="sxs-lookup"><span data-stu-id="49d28-109">To retrieve a single attribute from the element, you can use the **GetAttribute** and **GetAttributeNode** methods of the **XmlElement** or you can obtain all the attributes into a collection.</span></span> <span data-ttu-id="49d28-110">Quest'ultimo metodo può rivelarsi utile quando è necessario scorrere la raccolta.</span><span class="sxs-lookup"><span data-stu-id="49d28-110">Obtaining the collection is useful if you need to iterate over the collection.</span></span> <span data-ttu-id="49d28-111">Se si desidera che tutti gli attributi dall'elemento, utilizzare il **attributi** proprietà dell'elemento da recuperare tutti gli attributi in una raccolta.</span><span class="sxs-lookup"><span data-stu-id="49d28-111">If you want all attributes from the element, use the **Attributes** property of the element to retrieve all the attributes into a collection.</span></span>  
  
## <a name="retrieving-all-attributes-into-a-collection"></a><span data-ttu-id="49d28-112">Recupero di tutti gli attributi in una raccolta</span><span class="sxs-lookup"><span data-stu-id="49d28-112">Retrieving All Attributes into a Collection</span></span>  
 <span data-ttu-id="49d28-113">Se si desidera tutti gli attributi di un nodo elemento inseriti in una raccolta, chiamare il **XmlElement** proprietà.</span><span class="sxs-lookup"><span data-stu-id="49d28-113">If you want all the attributes of an element node put into a collection, call the **XmlElement.Attributes** property.</span></span> <span data-ttu-id="49d28-114">Ottiene il **XmlAttributeCollection** che contiene tutti gli attributi di un elemento.</span><span class="sxs-lookup"><span data-stu-id="49d28-114">This gets the **XmlAttributeCollection** that contains all the attributes of an element.</span></span> <span data-ttu-id="49d28-115">Il **XmlAttributeCollection** classe eredita il **XmlNamedNode** mappa.</span><span class="sxs-lookup"><span data-stu-id="49d28-115">The **XmlAttributeCollection** class inherits from the **XmlNamedNode** map.</span></span> <span data-ttu-id="49d28-116">Di conseguenza, i metodi e proprietà disponibili nella raccolta sono inoltre inclusi quelli disponibili in una mappa di nodi denominata oltre ai metodi e proprietà specifiche di **XmlAttributeCollection** classe, ad esempio il **ItemOf**  proprietà o **Append** metodo.</span><span class="sxs-lookup"><span data-stu-id="49d28-116">Therefore, the methods and properties available on the collection include those available on a named node map in addition to methods and properties specific to the **XmlAttributeCollection** class, such as the **ItemOf** property or the **Append** method.</span></span> <span data-ttu-id="49d28-117">Ogni elemento nella raccolta di attributi rappresenta un **XmlAttribute** nodo.</span><span class="sxs-lookup"><span data-stu-id="49d28-117">Each item in the attribute collection represents an **XmlAttribute** node.</span></span> <span data-ttu-id="49d28-118">Per trovare il numero di attributi su un elemento, ottenere il **XmlAttributeCollection**e utilizzare il **conteggio** proprietà per visualizzare quanti **XmlAttribute** nodi presenti nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="49d28-118">To find the number of attributes on an element, get the **XmlAttributeCollection**, and use the **Count** property to see how many **XmlAttribute** nodes are in the collection.</span></span>  
  
 <span data-ttu-id="49d28-119">Esempio di codice seguente viene illustrato come recuperare un attributo raccolta e, utilizzando il **conteggio** scorrerla metodo per l'indice del ciclo.</span><span class="sxs-lookup"><span data-stu-id="49d28-119">The following code example shows how to retrieve an attribute collection and, using the **Count** method for the looping index, iterate over it.</span></span> <span data-ttu-id="49d28-120">Inoltre, nel codice viene illustrato come recuperare un singolo attributo dalla raccolta e visualizzarne il valore.</span><span class="sxs-lookup"><span data-stu-id="49d28-120">The code then shows how to retrieve a single attribute from the collection and display its value.</span></span>  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Xml  
  
Public Class Sample  
  
    Public Shared Sub Main()  
  
        Dim doc As XmlDocument = New XmlDocument()  
        doc.LoadXml("<book genre='novel' ISBN='1-861001-57-5' misc='sale item'>" & _  
               "<title>The Handmaid's Tale</title>" & _  
               "<price>14.95</price>" & _  
               "</book>")  
  
        ' Move to an element.   
        Dim myElement As XmlElement = doc.DocumentElement  
  
        ' Create an attribute collection from the element.  
        Dim attrColl As XmlAttributeCollection = myElement.Attributes  
  
        ' Show the collection by iterating over it.  
        Console.WriteLine("Display all the attributes in the collection...")  
        Dim i As Integer  
        For i = 0 To attrColl.Count - 1  
            Console.Write("{0} = ", attrColl.ItemOf(i).Name)  
            Console.Write("{0}", attrColl.ItemOf(i).Value)  
            Console.WriteLine()  
        Next  
  
        ' Retrieve a single attribute from the collection; specifically, the  
        ' attribute with the name "misc".  
        Dim attr As XmlAttribute = attrColl("misc")  
  
        ' Retrieve the value from that attribute.  
        Dim miscValue As String = attr.InnerXml  
  
        Console.WriteLine("Display the attribute information.")  
        Console.WriteLine(miscValue)  
  
    End Sub  
End Class  
```  
  
```csharp  
using System;  
using System.IO;  
using System.Xml;  
  
public class Sample  
{  
  
    public static void Main()  
    {  
        XmlDocument doc = new XmlDocument();  
        doc.LoadXml("<book genre='novel' ISBN='1-861001-57-5' misc='sale item'>" +  
                      "<title>The Handmaid's Tale</title>" +  
                      "<price>14.95</price>" +  
                      "</book>");  
  
        // Move to an element.  
        XmlElement myElement = doc.DocumentElement;  
  
        // Create an attribute collection from the element.  
        XmlAttributeCollection attrColl = myElement.Attributes;  
  
        // Show the collection by iterating over it.  
        Console.WriteLine("Display all the attributes in the collection...");  
        for (int i = 0; i < attrColl.Count; i++)  
        {  
            Console.Write("{0} = ", attrColl[i].Name);  
            Console.Write("{0}", attrColl[i].Value);  
            Console.WriteLine();  
        }  
  
        // Retrieve a single attribute from the collection; specifically, the  
        // attribute with the name "misc".  
        XmlAttribute attr = attrColl["misc"];  
  
        // Retrieve the value from that attribute.  
        String miscValue = attr.InnerXml;  
  
        Console.WriteLine("Display the attribute information.");  
        Console.WriteLine(miscValue);  
  
    }  
}  
```  
  
 <span data-ttu-id="49d28-121">In questo esempio viene visualizzato il seguente l'output:</span><span class="sxs-lookup"><span data-stu-id="49d28-121">This example displays the following output:</span></span>  
  
 <span data-ttu-id="49d28-122">**Output**</span><span class="sxs-lookup"><span data-stu-id="49d28-122">**Output**</span></span>  
  
 <span data-ttu-id="49d28-123">Vengono visualizzati tutti gli attributi nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="49d28-123">Display all the attributes in the collection.</span></span>  
  
```  
genre = novel  
ISBN = 1-861001-57-5  
misc = sale item  
Display the attribute information.  
sale item  
```  
  
 <span data-ttu-id="49d28-124">È possibile recuperare le informazioni contenute in una raccolta di attributi in base al nome o al numero di indice.</span><span class="sxs-lookup"><span data-stu-id="49d28-124">The information in an attribute collection can be retrieved by name or index number.</span></span> <span data-ttu-id="49d28-125">Nell'esempio precedente è stato illustrato come recuperare i dati in base al nome.</span><span class="sxs-lookup"><span data-stu-id="49d28-125">The example above shows how to retrieve data by name.</span></span> <span data-ttu-id="49d28-126">Nell'esempio successivo viene illustrato come recuperare i dati in base al numero di indice.</span><span class="sxs-lookup"><span data-stu-id="49d28-126">The next example shows how to retrieve data by index number.</span></span>  
  
 <span data-ttu-id="49d28-127">Poiché il **XmlAttributeCollection** è una raccolta che è possibile scorrere per nome o indice, in questo esempio viene illustrato come selezionare il primo attributo della raccolta usando un indice in base zero e il seguente file **baseuri.xml**, come input.</span><span class="sxs-lookup"><span data-stu-id="49d28-127">Because the **XmlAttributeCollection** is a collection and can be iterated over by name or index, this example shows selecting the first attribute out of the collection using a zero-based index and using the following file, **baseuri.xml**, as input.</span></span>  
  
### <a name="input"></a><span data-ttu-id="49d28-128">Input</span><span class="sxs-lookup"><span data-stu-id="49d28-128">Input</span></span>  
  
```xml  
<!-- XML fragment -->  
<book genre="novel">  
  <title>Pride And Prejudice</title>  
</book>  
```  
  
```vb  
Option Explicit On  
Option Strict On  
  
Imports System  
Imports System.IO  
Imports System.Xml  
  
Public Class Sample  
  
    Public Shared Sub Main()  
        ' Create the XmlDocument.  
        Dim doc As New XmlDocument()  
        doc.Load("http://localhost/baseuri.xml")  
  
        ' Display information on the attribute node. The value  
        ' returned for BaseURI is 'http://localhost/baseuri.xml'.  
        Dim attr As XmlAttribute = doc.DocumentElement.Attributes(0)  
        Console.WriteLine("Name of the attribute:  {0}", attr.Name)  
        Console.WriteLine("Base URI of the attribute:  {0}", attr.BaseURI)  
        Console.WriteLine("The value of the attribtue:  {0}", attr.InnerText)  
    End Sub 'Main   
End Class 'Sample  
```  
  
```csharp  
using System;  
using System.IO;  
using System.Xml;  
  
public class Sample  
{  
  public static void Main()  
  {  
    // Create the XmlDocument.  
    XmlDocument doc = new XmlDocument();  
  
    doc.Load("http://localhost/baseuri.xml");  
  
    // Display information on the attribute node. The value  
    // returned for BaseURI is 'http://localhost/baseuri.xml'.  
    XmlAttribute attr = doc.DocumentElement.Attributes[0];  
    Console.WriteLine("Name of the attribute:  {0}", attr.Name);  
    Console.WriteLine("Base URI of the attribute:  {0}", attr.BaseURI);  
    Console.WriteLine("The value of the attribtue:  {0}", attr.InnerText);  
  }  
}  
```  
  
## <a name="retrieving-an-individual-attribute-node"></a><span data-ttu-id="49d28-129">Recupero di un singolo nodo Attribute</span><span class="sxs-lookup"><span data-stu-id="49d28-129">Retrieving an Individual Attribute Node</span></span>  
 <span data-ttu-id="49d28-130">Per rimuovere un singolo nodo di attributo da un elemento, viene usato il metodo <xref:System.Xml.XmlElement.GetAttributeNode%2A?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="49d28-130">To retrieve a single attribute node from an element, the <xref:System.Xml.XmlElement.GetAttributeNode%2A?displayProperty=nameWithType> method is used.</span></span> <span data-ttu-id="49d28-131">Restituisce un oggetto di tipo **XmlAttribute**.</span><span class="sxs-lookup"><span data-stu-id="49d28-131">It returns an object of type **XmlAttribute**.</span></span> <span data-ttu-id="49d28-132">Dopo aver creato un **XmlAttribute**, tutti i metodi e le proprietà disponibili nella <xref:System.Xml.XmlAttribute?displayProperty=nameWithType> classe sono disponibili in tale oggetto, ad esempio la ricerca di **OwnerElement**.</span><span class="sxs-lookup"><span data-stu-id="49d28-132">Once you have an **XmlAttribute**, all the methods and properties available in the <xref:System.Xml.XmlAttribute?displayProperty=nameWithType> class are available on that object, such as finding the **OwnerElement**.</span></span>  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Xml  
  
Public Class Sample  
  
    Public Shared Sub Main()  
  
        Dim doc As XmlDocument = New XmlDocument()  
        doc.LoadXml("<book genre='novel' ISBN='1-861001-57-5' misc='sale item'>" & _  
               "<title>The Handmaid's Tale</title>" & _  
               "<price>14.95</price>" & _  
               "</book>")  
  
        ' Move to an element.  
        Dim root As XmlElement  
        root = doc.DocumentElement  
  
        ' Get an attribute.  
        Dim attr As XmlAttribute  
        attr = root.GetAttributeNode("ISBN")  
  
        ' Display the value of the attribute.  
        Dim attrValue As String  
        attrValue = attr.InnerXml  
        Console.WriteLine(attrValue)  
  
    End Sub  
End Class  
```  
  
```csharp  
using System;  
using System.IO;  
using System.Xml;  
  
 public class Sample  
 {  
      public static void Main()  
      {  
    XmlDocument doc = new XmlDocument();  
     doc.LoadXml("<book genre='novel' ISBN='1-861003-78' misc='sale item'>" +  
                   "<title>The Handmaid's Tale</title>" +  
                   "<price>14.95</price>" +  
                   "</book>");   
  
    // Move to an element.  
     XmlElement root = doc.DocumentElement;  
  
    // Get an attribute.  
     XmlAttribute attr = root.GetAttributeNode("ISBN");  
  
    // Display the value of the attribute.  
     String attrValue = attr.InnerXml;  
     Console.WriteLine(attrValue);  
  
    }  
}  
```  
  
 <span data-ttu-id="49d28-133">È anche possibile riprodurre l'esempio precedente, in cui dalla raccolta di attributi viene recuperato un singolo nodo Attribute.</span><span class="sxs-lookup"><span data-stu-id="49d28-133">You can also do as shown in the previous example, where a single attribute node is retrieved from the attribute collection.</span></span> <span data-ttu-id="49d28-134">L'esempio di codice riportato di seguito viene illustrato come è possibile scrivere una sola riga di codice per recuperare un singolo attributo al numero di indice dalla radice del documento XML albero, nota anche come il **DocumentElement** proprietà.</span><span class="sxs-lookup"><span data-stu-id="49d28-134">The following code example shows how one line of code can be written to retrieve a single attribute by index number from the root of the XML document tree, also known as the **DocumentElement** property.</span></span>  
  
```  
XmlAttribute attr = doc.DocumentElement.Attributes[0];  
```  
  
## <a name="see-also"></a><span data-ttu-id="49d28-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="49d28-135">See Also</span></span>  
 [<span data-ttu-id="49d28-136">XML Document Object Model (DOM)</span><span class="sxs-lookup"><span data-stu-id="49d28-136">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
