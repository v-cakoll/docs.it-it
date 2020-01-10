---
title: Creazione di nuovi attributi per gli elementi nel DOM
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: dd6dc920-b011-418a-b3db-f1580a7d9251
ms.openlocfilehash: 79a3390933256ed862d35c90db0aab2177cdfc41
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75711012"
---
# <a name="creating-new-attributes-for-elements-in-the-dom"></a><span data-ttu-id="06e4c-102">Creazione di nuovi attributi per gli elementi nel DOM</span><span class="sxs-lookup"><span data-stu-id="06e4c-102">Creating New Attributes for Elements in the DOM</span></span>

<span data-ttu-id="06e4c-103">La creazione di nuovi attributi è diversa dalla creazione di altri tipi di nodi, perché gli attributi non sono nodi, ma proprietà di un nodo di elemento e sono contenuti in una classe **XmlAttributeCollection** associata all'elemento.</span><span class="sxs-lookup"><span data-stu-id="06e4c-103">Creating new attributes is different than creating other node types, because attributes are not nodes, but are properties of an element node and are contained in an **XmlAttributeCollection** associated with the element.</span></span> <span data-ttu-id="06e4c-104">Sono disponibili diversi modi per creare un attributo e associarlo a un elemento:</span><span class="sxs-lookup"><span data-stu-id="06e4c-104">There are multiple ways to create an attribute and attach it to an element:</span></span>

- <span data-ttu-id="06e4c-105">Ottenere il nodo dell'elemento e usare **SetAttribute** per aggiungere un attributo alla raccolta di attributi di tale elemento.</span><span class="sxs-lookup"><span data-stu-id="06e4c-105">Get the element node and use **SetAttribute** to add an attribute to the attribute collection of that element.</span></span>

- <span data-ttu-id="06e4c-106">Creare un nodo **XmlAttribute** usando il metodo **CreateAttribute**, ottenere il nodo dell'elemento, quindi usare **SetAttributeNode** per aggiungere il nodo alla raccolta di attributi di tale elemento.</span><span class="sxs-lookup"><span data-stu-id="06e4c-106">Create an **XmlAttribute** node using the **CreateAttribute** method, get the element node, then use **SetAttributeNode** to add the node to the attribute collection of that element.</span></span>

<span data-ttu-id="06e4c-107">Nell'esempio seguente viene illustrato come aggiungere un attributo a un elemento utilizzando il metodo **SetAttribute** :</span><span class="sxs-lookup"><span data-stu-id="06e4c-107">The following example shows how to add an attribute to an element using the **SetAttribute** method:</span></span>

```vb
Imports System.IO
Imports System.Xml

Public Class Sample

    Public Shared Sub Main()

        Dim doc As New XmlDocument()
        doc.LoadXml("<book xmlns:bk='urn:samples' bk:ISBN='1-861001-57-5'>" & _
                    "<title>Pride And Prejudice</title>" & _
                    "</book>")
        Dim root As XmlElement = doc.DocumentElement

        ' Add a new attribute.
        root.SetAttribute("genre", "urn:samples", "novel")

        Console.WriteLine("Display the modified XML...")
        Console.WriteLine(doc.InnerXml)
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
        var doc = new XmlDocument();
        doc.LoadXml("<book xmlns:bk='urn:samples' bk:ISBN='1-861001-57-5'>" +
                    "<title>Pride And Prejudice</title>" +
                    "</book>");
        XmlElement root = doc.DocumentElement;

        // Add a new attribute.
        root.SetAttribute("genre", "urn:samples", "novel");

        Console.WriteLine("Display the modified XML...");
        Console.WriteLine(doc.InnerXml);
    }
}
```

<span data-ttu-id="06e4c-108">Nell'esempio seguente viene illustrata la creazione di un nuovo attributo con il metodo **CreateAttribute**.</span><span class="sxs-lookup"><span data-stu-id="06e4c-108">The following example shows a new attribute being created using the **CreateAttribute** method.</span></span> <span data-ttu-id="06e4c-109">L'attributo viene quindi aggiunto alla raccolta di attributi dell'elemento **book** con il metodo **SetAttributeNode**.</span><span class="sxs-lookup"><span data-stu-id="06e4c-109">It then shows the attribute added to the attribute collection of the **book** element using the **SetAttributeNode** method.</span></span>

<span data-ttu-id="06e4c-110">Dato l'XML seguente:</span><span class="sxs-lookup"><span data-stu-id="06e4c-110">Given the following XML:</span></span>
  
```xml
<book genre='novel' ISBN='1-861001-57-5'>
<title>Pride And Prejudice</title>
</book>
```

<span data-ttu-id="06e4c-111">Creare un nuovo attributo e assegnargli un valore:</span><span class="sxs-lookup"><span data-stu-id="06e4c-111">create a new attribute and give it a value:</span></span>

```vb
Dim attr As XmlAttribute = doc.CreateAttribute("publisher")
attr.Value = "WorldWide Publishing"
```

```csharp
XmlAttribute attr = doc.CreateAttribute("publisher");
attr.Value = "WorldWide Publishing";
```

<span data-ttu-id="06e4c-112">Quindi associarlo all'elemento:</span><span class="sxs-lookup"><span data-stu-id="06e4c-112">and attach it to the element:</span></span>

```vb
doc.DocumentElement.SetAttributeNode(attr)
```

```csharp
doc.DocumentElement.SetAttributeNode(attr);
```

<span data-ttu-id="06e4c-113">**Output**</span><span class="sxs-lookup"><span data-stu-id="06e4c-113">**Output**</span></span>

```xml
<book genre="novel" ISBN="1-861001-57-5" publisher="WorldWide Publishing">
<title>Pride And Prejudice</title>
</book>
```

<span data-ttu-id="06e4c-114">L'esempio di codice completo è disponibile in <xref:System.Xml.XmlDocument.CreateAttribute%2A>.</span><span class="sxs-lookup"><span data-stu-id="06e4c-114">The full code sample can be found at <xref:System.Xml.XmlDocument.CreateAttribute%2A>.</span></span>

<span data-ttu-id="06e4c-115">È anche possibile creare un nodo **XmlAttribute** e usare i metodi **InsertBefore** o **InsertAfter** per inserirlo nella posizione appropriata nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="06e4c-115">You can also create an **XmlAttribute** node and use the **InsertBefore** or **InsertAfter** methods to place it in the appropriate position in the collection.</span></span> <span data-ttu-id="06e4c-116">Se è già presente un attributo con lo stesso nome nella raccolta di attributi, il nodo **XmlAttribute** esistente viene rimosso dalla raccolta e il nuovo nodo **XmlAttribute** viene inserito.</span><span class="sxs-lookup"><span data-stu-id="06e4c-116">If an attribute with the same name is already present in the attribute collection, the existing **XmlAttribute** node is removed from the collection and the new **XmlAttribute** node is inserted.</span></span> <span data-ttu-id="06e4c-117">Questa operazione viene eseguita come nel metodo **SetAttribute**.</span><span class="sxs-lookup"><span data-stu-id="06e4c-117">This performs the same way as the **SetAttribute** method.</span></span> <span data-ttu-id="06e4c-118">Questi metodi accettano come parametro un nodo esistente come punto di riferimento per eseguire **InsertBefore** e **InsertAfter**.</span><span class="sxs-lookup"><span data-stu-id="06e4c-118">These methods take, as a parameter, an existing node as a reference point to do the **InsertBefore** and **InsertAfter**.</span></span> <span data-ttu-id="06e4c-119">Se non viene fornito un nodo di riferimento che indica dove inserire il nuovo nodo, per impostazione predefinita il metodo **InsertAfter** inserirà il nuovo nodo all'inizio della raccolta.</span><span class="sxs-lookup"><span data-stu-id="06e4c-119">If you do not provide a reference node indicating where to insert the new node, the default for the **InsertAfter** method is to insert the new node at the beginning of the collection.</span></span> <span data-ttu-id="06e4c-120">Se non viene fornito alcun nodo di riferimento, la posizione predefinita di **InsertBefore** è alla fine della raccolta.</span><span class="sxs-lookup"><span data-stu-id="06e4c-120">The default position for the **InsertBefore**, if no reference node is provided, is at the end of the collection.</span></span>

<span data-ttu-id="06e4c-121">Se è stato creato un **XmlNamedNodeMap** di attributi, è possibile aggiungere un attributo in base al nome usando il metodo <xref:System.Xml.XmlNamedNodeMap.SetNamedItem%2A>.</span><span class="sxs-lookup"><span data-stu-id="06e4c-121">If you created an **XmlNamedNodeMap** of attributes, you can add an attribute by name using the <xref:System.Xml.XmlNamedNodeMap.SetNamedItem%2A> method.</span></span> <span data-ttu-id="06e4c-122">Per altre informazioni, vedere [Raccolte di nodi in NamedNodeMaps e NodeLists](node-collections-in-namednodemaps-and-nodelists.md).</span><span class="sxs-lookup"><span data-stu-id="06e4c-122">For more information, see [Node Collections in NamedNodeMaps and NodeLists](node-collections-in-namednodemaps-and-nodelists.md).</span></span>

## <a name="default-attributes"></a><span data-ttu-id="06e4c-123">Attributi predefiniti</span><span class="sxs-lookup"><span data-stu-id="06e4c-123">Default attributes</span></span>

<span data-ttu-id="06e4c-124">Se si crea un elemento in cui è dichiarato un attributo predefinito, nel DOM (Document Object Model) XML verrà creato e associato all'elemento un nuovo attributo predefinito con il relativo valore.</span><span class="sxs-lookup"><span data-stu-id="06e4c-124">If you create an element that is declared to have a default attribute, then a new default attribute with its default value is created by the XML Document Object Model (DOM) and attached to the element.</span></span> <span data-ttu-id="06e4c-125">Contemporaneamente verranno creati anche i nodi figlio dell'attributo predefinito.</span><span class="sxs-lookup"><span data-stu-id="06e4c-125">The child nodes of the default attribute are also created at this time.</span></span>

## <a name="attribute-child-nodes"></a><span data-ttu-id="06e4c-126">Nodi figlio attributo</span><span class="sxs-lookup"><span data-stu-id="06e4c-126">Attribute child nodes</span></span>

<span data-ttu-id="06e4c-127">Il valore del nodo di un attributo diviene i nodi figlio dell'attributo stesso.</span><span class="sxs-lookup"><span data-stu-id="06e4c-127">The value of an attribute node becomes its child nodes.</span></span> <span data-ttu-id="06e4c-128">Esistono solo due tipi di nodi figlio validi: i nodi **XmlText** e i nodi **XmlEntityReference** .</span><span class="sxs-lookup"><span data-stu-id="06e4c-128">There are only two types of valid child nodes: **XmlText** nodes and **XmlEntityReference** nodes.</span></span> <span data-ttu-id="06e4c-129">Si tratta di nodi figlio perché vengono elaborati come tali da metodi come **FirstChild** e **LastChild**.</span><span class="sxs-lookup"><span data-stu-id="06e4c-129">These are child nodes in the sense that methods such as **FirstChild** and **LastChild** process them as child nodes.</span></span> <span data-ttu-id="06e4c-130">Questa distinzione di un attributo con nodi figlio è importante quando si tenta di rimuovere attributi o nodi figlio degli attributi.</span><span class="sxs-lookup"><span data-stu-id="06e4c-130">This distinction of an attribute having child nodes is important when trying to remove attributes or attribute child nodes.</span></span> <span data-ttu-id="06e4c-131">Per altre informazioni, vedere [Rimozione di attributi da un nodo di elemento nel DOM](removing-attributes-from-an-element-node-in-the-dom.md).</span><span class="sxs-lookup"><span data-stu-id="06e4c-131">For more information, see [Removing Attributes from an Element Node in the DOM](removing-attributes-from-an-element-node-in-the-dom.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="06e4c-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="06e4c-132">See also</span></span>

- [<span data-ttu-id="06e4c-133">Modello DOM (Document Object Mode) XML</span><span class="sxs-lookup"><span data-stu-id="06e4c-133">XML Document Object Model (DOM)</span></span>](xml-document-object-model-dom.md)
