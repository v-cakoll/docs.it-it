---
title: Creazione di nuovi attributi per gli elementi nel DOM
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
ms.assetid: dd6dc920-b011-418a-b3db-f1580a7d9251
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 6970ffc38e900c9b47c58c8ae4b81b9551f5589b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="creating-new-attributes-for-elements-in-the-dom"></a><span data-ttu-id="8000d-102">Creazione di nuovi attributi per gli elementi nel DOM</span><span class="sxs-lookup"><span data-stu-id="8000d-102">Creating New Attributes for Elements in the DOM</span></span>
<span data-ttu-id="8000d-103">Creazione di nuovi attributi è diversa dalla creazione di altri tipi di nodo, in quanto gli attributi non sono nodi, ma sono proprietà di un nodo di elemento e sono contenuti in un **XmlAttributeCollection** associato all'elemento.</span><span class="sxs-lookup"><span data-stu-id="8000d-103">Creating new attributes is different than creating other node types, because attributes are not nodes, but are properties of an element node and are contained in an **XmlAttributeCollection** associated with the element.</span></span> <span data-ttu-id="8000d-104">Sono disponibili diversi modi per creare un attributo e associarlo a un elemento:</span><span class="sxs-lookup"><span data-stu-id="8000d-104">There are multiple ways to create an attribute and attach it to an element:</span></span>  
  
-   <span data-ttu-id="8000d-105">Ottenere il nodo di elemento e utilizzare **SetAttribute** per aggiungere un attributo alla raccolta di attributi di quell'elemento.</span><span class="sxs-lookup"><span data-stu-id="8000d-105">Get the element node and use **SetAttribute** to add an attribute to the attribute collection of that element.</span></span>  
  
-   <span data-ttu-id="8000d-106">Creare un **XmlAttribute** nodo utilizzando il **CreateAttribute** (metodo), ottenere il nodo dell'elemento, quindi utilizzare **SetAttributeNode** per aggiungere il nodo alla raccolta di attributi di tale elemento.</span><span class="sxs-lookup"><span data-stu-id="8000d-106">Create an **XmlAttribute** node using the **CreateAttribute** method, get the element node, then use **SetAttributeNode** to add the node to the attribute collection of that element.</span></span>  
  
 <span data-ttu-id="8000d-107">Nell'esempio seguente viene illustrato come aggiungere un attributo a un elemento utilizzando il **SetAttribute** metodo.</span><span class="sxs-lookup"><span data-stu-id="8000d-107">The following example shows how to add an attribute to an element using the **SetAttribute** method.</span></span>  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Xml  
  
public class Sample  
  
  public shared sub Main()  
  
  Dim doc as XmlDocument = new XmlDocument()  
  doc.LoadXml("<book xmlns:bk='urn:samples' bk:ISBN='1-861001-57-5'>" & _  
              "<title>Pride And Prejudice</title>" & _  
              "</book>")  
  Dim root as XmlElement = doc.DocumentElement  
  
  'Add a new attribute.  
  root.SetAttribute("genre", "urn:samples", "novel")  
  
  Console.WriteLine("Display the modified XML...")  
  Console.WriteLine(doc.InnerXml)  
  
  end sub  
end class  
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
    doc.LoadXml("<book xmlns:bk='urn:samples' bk:ISBN='1-861001-57-5'>" +  
                "<title>Pride And Prejudice</title>" +  
                "</book>");  
    XmlElement root = doc.DocumentElement;  
  
    // Add a new attribute.  
    root.SetAttribute("genre", "urn:samples", "novel");  
  
    Console.WriteLine("Display the modified XML...");  
    Console.WriteLine(doc.InnerXml);  
  }  
```  
  
 <span data-ttu-id="8000d-108">Nell'esempio seguente viene illustrato un nuovo attributo con il **CreateAttribute** metodo.</span><span class="sxs-lookup"><span data-stu-id="8000d-108">The following example shows a new attribute being created using the **CreateAttribute** method.</span></span> <span data-ttu-id="8000d-109">Quindi l'attributo viene aggiunto alla raccolta di attributi del **book** elemento utilizzando il **SetAttributeNode** metodo.</span><span class="sxs-lookup"><span data-stu-id="8000d-109">It then shows the attribute added to the attribute collection of the **book** element using the **SetAttributeNode** method.</span></span>  
  
 <span data-ttu-id="8000d-110">Dato l'XML seguente:</span><span class="sxs-lookup"><span data-stu-id="8000d-110">Given the following XML:</span></span>  
  
```xml  
<book genre='novel' ISBN='1-861001-57-5'>  
<title>Pride And Prejudice</title>  
</book>  
```  
  
 <span data-ttu-id="8000d-111">Creare un nuovo attributo e assegnargli un valore:</span><span class="sxs-lookup"><span data-stu-id="8000d-111">create a new attribute and give it a value:</span></span>  
  
```vb  
Dim attr As XmlAttribute = doc.CreateAttribute("publisher")  
   attr.Value = "WorldWide Publishing"  
```  
  
```csharp  
XmlAttribute attr = doc.CreateAttribute("publisher");  
attr.Value = "WorldWide Publishing";  
```  
  
 <span data-ttu-id="8000d-112">Quindi associarlo all'elemento:</span><span class="sxs-lookup"><span data-stu-id="8000d-112">and attach it to the element:</span></span>  
  
```vb  
doc.DocumentElement.SetAttributeNode(attr)  
```  
  
```csharp  
doc.DocumentElement.SetAttributeNode(attr);  
```  
  
 <span data-ttu-id="8000d-113">**Output**</span><span class="sxs-lookup"><span data-stu-id="8000d-113">**Output**</span></span>  
  
```xml  
<book genre="novel" ISBN="1-861001-57-5" publisher="WorldWide Publishing">  
<title>Pride And Prejudice</title>  
</book>  
```  
  
 <span data-ttu-id="8000d-114">L'esempio di codice completo è reperibile in <xref:System.Xml.XmlDocument.CreateAttribute%2A>.</span><span class="sxs-lookup"><span data-stu-id="8000d-114">The full code sample can be found at <xref:System.Xml.XmlDocument.CreateAttribute%2A>.</span></span>  
  
 <span data-ttu-id="8000d-115">È inoltre possibile creare un **XmlAttribute** nodo e utilizzo di **InsertBefore** o **InsertAfter** metodi per inserirlo nella posizione appropriata all'interno della raccolta.</span><span class="sxs-lookup"><span data-stu-id="8000d-115">You can also create an **XmlAttribute** node and use the **InsertBefore** or **InsertAfter** methods to place it in the appropriate position in the collection.</span></span> <span data-ttu-id="8000d-116">Se un attributo con lo stesso nome è già presente nella raccolta di attributi, esistente **XmlAttribute** nodo viene rimosso dalla raccolta e il nuovo **XmlAttribute** nodo inserito.</span><span class="sxs-lookup"><span data-stu-id="8000d-116">If an attribute with the same name is already present in the attribute collection, the existing **XmlAttribute** node is removed from the collection and the new **XmlAttribute** node is inserted.</span></span> <span data-ttu-id="8000d-117">Viene eseguita nello stesso modo di **SetAttribute** metodo.</span><span class="sxs-lookup"><span data-stu-id="8000d-117">This performs the same way as the **SetAttribute** method.</span></span> <span data-ttu-id="8000d-118">Questi metodi accettano come parametro, un nodo esistente come punto di riferimento per eseguire il **InsertBefore** e **InsertAfter**.</span><span class="sxs-lookup"><span data-stu-id="8000d-118">These methods take, as a parameter, an existing node as a reference point to do the **InsertBefore** and **InsertAfter**.</span></span> <span data-ttu-id="8000d-119">Se non si specifica un nodo di riferimento che indica dove inserire il nuovo nodo, il valore predefinito per il **InsertAfter** metodo consiste nell'inserire il nuovo nodo all'inizio della raccolta.</span><span class="sxs-lookup"><span data-stu-id="8000d-119">If you do not provide a reference node indicating where to insert the new node, the default for the **InsertAfter** method is to insert the new node at the beginning of the collection.</span></span> <span data-ttu-id="8000d-120">La posizione predefinita per il **InsertBefore**, se non viene fornito alcun nodo di riferimento, si trova alla fine della raccolta.</span><span class="sxs-lookup"><span data-stu-id="8000d-120">The default position for the **InsertBefore**, if no reference node is provided, is at the end of the collection.</span></span>  
  
 <span data-ttu-id="8000d-121">Se è stato creato un **XmlNamedNodeMap** di attributi, è possibile aggiungere un attributo in base al nome utilizzando il <xref:System.Xml.XmlNamedNodeMap.SetNamedItem%2A>.</span><span class="sxs-lookup"><span data-stu-id="8000d-121">If you created an **XmlNamedNodeMap** of attributes, you can add an attribute by name using the <xref:System.Xml.XmlNamedNodeMap.SetNamedItem%2A>.</span></span> <span data-ttu-id="8000d-122">Per ulteriori informazioni, vedere [raccolte di nodi in NamedNodeMaps e NodeLists](../../../../docs/standard/data/xml/node-collections-in-namednodemaps-and-nodelists.md).</span><span class="sxs-lookup"><span data-stu-id="8000d-122">For more information, see [Node Collections in NamedNodeMaps and NodeLists](../../../../docs/standard/data/xml/node-collections-in-namednodemaps-and-nodelists.md).</span></span>  
  
## <a name="default-attributes"></a><span data-ttu-id="8000d-123">Attributi predefiniti</span><span class="sxs-lookup"><span data-stu-id="8000d-123">Default Attributes</span></span>  
 <span data-ttu-id="8000d-124">Se si crea un elemento in cui è dichiarato un attributo predefinito, nel DOM (Document Object Model) XML verrà creato e associato all'elemento un nuovo attributo predefinito con il relativo valore.</span><span class="sxs-lookup"><span data-stu-id="8000d-124">If you create an element that is declared to have a default attribute, then a new default attribute with its default value is created by the XML Document Object Model (DOM) and attached to the element.</span></span> <span data-ttu-id="8000d-125">Contemporaneamente verranno creati anche i nodi figlio dell'attributo predefinito.</span><span class="sxs-lookup"><span data-stu-id="8000d-125">The child nodes of the default attribute are also created at this time.</span></span>  
  
## <a name="attribute-child-nodes"></a><span data-ttu-id="8000d-126">Nodi figlio degli attributi</span><span class="sxs-lookup"><span data-stu-id="8000d-126">Attribute Child Nodes</span></span>  
 <span data-ttu-id="8000d-127">Il valore del nodo di un attributo diviene i nodi figlio dell'attributo stesso.</span><span class="sxs-lookup"><span data-stu-id="8000d-127">The value of an attribute node becomes its child nodes.</span></span> <span data-ttu-id="8000d-128">Sono disponibili solo due tipi di nodi figlio validi: **XmlText** , nodi e **XmlEntityReference** nodi.</span><span class="sxs-lookup"><span data-stu-id="8000d-128">There are only two types of valid child nodes: **XmlText** nodes, and **XmlEntityReference** nodes.</span></span> <span data-ttu-id="8000d-129">Questi sono i nodi figlio nel senso che metodi, ad esempio **FirstChild** e **LastChild** elaborarli come nodi figlio.</span><span class="sxs-lookup"><span data-stu-id="8000d-129">These are child nodes in the sense that methods such as **FirstChild** and **LastChild** process them as child nodes.</span></span> <span data-ttu-id="8000d-130">Questa distinzione di un attributo con nodi figlio è importante quando si tenta di rimuovere attributi o nodi figlio degli attributi.</span><span class="sxs-lookup"><span data-stu-id="8000d-130">This distinction of an attribute having child nodes is important when trying to remove attributes or attribute child nodes.</span></span> <span data-ttu-id="8000d-131">Per ulteriori informazioni, vedere [rimozione di attributi da un nodo di elemento nel DOM](../../../../docs/standard/data/xml/removing-attributes-from-an-element-node-in-the-dom.md).</span><span class="sxs-lookup"><span data-stu-id="8000d-131">For more information, see [Removing Attributes from an Element Node in the DOM](../../../../docs/standard/data/xml/removing-attributes-from-an-element-node-in-the-dom.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8000d-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8000d-132">See Also</span></span>  
 [<span data-ttu-id="8000d-133">XML Document Object Model (DOM)</span><span class="sxs-lookup"><span data-stu-id="8000d-133">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
