---
title: Estensione del DOM
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
ms.assetid: b5489c96-4afd-439a-a25d-fc82eb4a148d
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 06cac8d76b17f3ef32931ea21d0556085f05d7b1
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="extending-the-dom"></a><span data-ttu-id="a9a0f-102">Estensione del DOM</span><span class="sxs-lookup"><span data-stu-id="a9a0f-102">Extending the DOM</span></span>
<span data-ttu-id="a9a0f-103">Microsoft .NET Framework comprende un set di classi di base che fornisce l'implementazione del modello DOM XML (Document Object Model).</span><span class="sxs-lookup"><span data-stu-id="a9a0f-103">The Microsoft .NET Framework includes a base set of classes that provides an implementation of the XML Document Object Model (DOM).</span></span> <span data-ttu-id="a9a0f-104">Tramite <xref:System.Xml.XmlNode> e le classi derivate vengono forniti metodi e proprietà che consentono di esplorare, eseguire query e modificare il contenuto e la struttura di un documento XML.</span><span class="sxs-lookup"><span data-stu-id="a9a0f-104">The <xref:System.Xml.XmlNode>, and its derived classes, provides methods and properties that allow you to navigate, query, and modify the content and structure of an XML document.</span></span>  
  
 <span data-ttu-id="a9a0f-105">Quando il contenuto dell'XML è caricato in memoria tramite il DOM, i nodi creati contengono informazioni quali il nome del nodo, il tipo di nodo e così via.</span><span class="sxs-lookup"><span data-stu-id="a9a0f-105">When XML content is loaded into memory using the DOM, the nodes created contain information such as node name, node type, and so on.</span></span> <span data-ttu-id="a9a0f-106">In alcuni casi è possibile che siano necessarie informazioni specifiche sul nodo che non vengono fornite dalle classi di base.</span><span class="sxs-lookup"><span data-stu-id="a9a0f-106">There may be occasions where you require specific node information that the base classes do not provide.</span></span> <span data-ttu-id="a9a0f-107">È possibile, ad esempio, che si desideri conoscere il numero di riga e la posizione del nodo.</span><span class="sxs-lookup"><span data-stu-id="a9a0f-107">For example, you may want to see the line number and position of the node.</span></span> <span data-ttu-id="a9a0f-108">In questo caso è possibile derivare nuove classi dalle classi esistenti del DOM e aggiungere ulteriori funzionalità.</span><span class="sxs-lookup"><span data-stu-id="a9a0f-108">In this case, you can derive new classes from the existing DOM classes and add additional functionality.</span></span>  
  
 <span data-ttu-id="a9a0f-109">La derivazione di nuove classi è soggetta a due linee guida generali:</span><span class="sxs-lookup"><span data-stu-id="a9a0f-109">There are two general guidelines when deriving new classes:</span></span>  
  
-   <span data-ttu-id="a9a0f-110">Si consiglia di non eseguire mai una derivazione dalla classe <xref:System.Xml.XmlNode>.</span><span class="sxs-lookup"><span data-stu-id="a9a0f-110">It is recommended that you never derive from the <xref:System.Xml.XmlNode> class.</span></span> <span data-ttu-id="a9a0f-111">Si consiglia invece di eseguire la derivazione delle classi dalla classe corrispondente al tipo di nodo a cui si è interessati.</span><span class="sxs-lookup"><span data-stu-id="a9a0f-111">Instead, it is recommended that you derive classes from the class corresponding to the node type that you are interested in.</span></span> <span data-ttu-id="a9a0f-112">Se ad esempio si desidera restituire ulteriori informazioni sui nodi degli attributi, è possibile eseguire la derivazione dalla classe <xref:System.Xml.XmlAttribute>.</span><span class="sxs-lookup"><span data-stu-id="a9a0f-112">For example, if you want to return additional information on attribute nodes, you can derive from the <xref:System.Xml.XmlAttribute> class.</span></span>  
  
-   <span data-ttu-id="a9a0f-113">Ad eccezione dei metodi per la creazione dei nodi, se si esegue l'override di una funzione si consiglia di chiamare sempre la versione di base della funzione e di aggiungervi un'eventuale elaborazione aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="a9a0f-113">Except for the node creation methods, it is recommended that when overriding a function, you should always call the base version of the function and then add any additional processing.</span></span>  
  
## <a name="creating-your-own-node-instances"></a><span data-ttu-id="a9a0f-114">Creazione di istanze dei nodi</span><span class="sxs-lookup"><span data-stu-id="a9a0f-114">Creating Your Own Node Instances</span></span>  
 <span data-ttu-id="a9a0f-115">La classe <xref:System.Xml.XmlDocument> contiene i metodi per la creazione di nodi.</span><span class="sxs-lookup"><span data-stu-id="a9a0f-115">The <xref:System.Xml.XmlDocument> class contains node creation methods.</span></span> <span data-ttu-id="a9a0f-116">Quando viene caricato un file XML, questi metodi vengono chiamati per creare i nodi.</span><span class="sxs-lookup"><span data-stu-id="a9a0f-116">When an XML file is loaded, these methods are called to create the nodes.</span></span> <span data-ttu-id="a9a0f-117">È possibile eseguire l'override di questi metodi in modo che le istanze dei nodi vengano create quando viene caricato un documento.</span><span class="sxs-lookup"><span data-stu-id="a9a0f-117">You can override these methods so that your node instances are created when a document is loaded.</span></span> <span data-ttu-id="a9a0f-118">Se ad esempio è stata estesa la classe <xref:System.Xml.XmlElement>, viene ereditata la classe <xref:System.Xml.XmlDocument> e viene eseguito l'override del metodo <xref:System.Xml.XmlDocument.CreateElement%2A>.</span><span class="sxs-lookup"><span data-stu-id="a9a0f-118">For example, if you have extended the <xref:System.Xml.XmlElement> class, you would inherit the <xref:System.Xml.XmlDocument> class and override the <xref:System.Xml.XmlDocument.CreateElement%2A> method.</span></span>  
  
 <span data-ttu-id="a9a0f-119">Nell'esempio seguente viene illustrato come eseguire l'override del metodo <xref:System.Xml.XmlDocument.CreateElement%2A> per restituire l'implementazione della classe <xref:System.Xml.XmlElement>.</span><span class="sxs-lookup"><span data-stu-id="a9a0f-119">The following example shows how to override the <xref:System.Xml.XmlDocument.CreateElement%2A> method to return your implementation of the <xref:System.Xml.XmlElement> class.</span></span>  
  
```vb  
Class LineInfoDocument  
    Inherits XmlDocument  
        Public Overrides Function CreateElement(prefix As String, localname As String, nsURI As String) As XmlElement  
        Dim elem As New LineInfoElement(prefix, localname, nsURI, Me)  
        Return elem  
    End Function 'CreateElement  
End Class 'LineInfoDocument  
```  
  
```csharp  
class LineInfoDocument : XmlDocument {  
  public override XmlElement CreateElement(string prefix, string localname, string nsURI) {  
  LineInfoElement elem = new LineInfoElement(prefix, localname, nsURI, this);  
  return elem;  
  }  
```  
  
## <a name="extending-a-class"></a><span data-ttu-id="a9a0f-120">Estensione di una classe</span><span class="sxs-lookup"><span data-stu-id="a9a0f-120">Extending a Class</span></span>  
 <span data-ttu-id="a9a0f-121">Per estendere una classe, derivare la classe da una delle classi esistenti del DOM.</span><span class="sxs-lookup"><span data-stu-id="a9a0f-121">To extend a class, derive your class from one of the existing DOM classes.</span></span> <span data-ttu-id="a9a0f-122">È possibile quindi eseguire l'override dei metodi o delle proprietà virtuali nella classe di base oppure aggiungere quelli di propria creazione.</span><span class="sxs-lookup"><span data-stu-id="a9a0f-122">You can then override any of the virtual methods or properties in the base class, or add your own.</span></span>  
  
 <span data-ttu-id="a9a0f-123">Nell'esempio seguente viene creata una nuova classe, che implementa la classe <xref:System.Xml.XmlElement> e l'interfaccia <xref:System.Xml.IXmlLineInfo>.</span><span class="sxs-lookup"><span data-stu-id="a9a0f-123">In the following example, a new class is created, which implements the <xref:System.Xml.XmlElement> class and the <xref:System.Xml.IXmlLineInfo> interface.</span></span> <span data-ttu-id="a9a0f-124">Sono definiti metodi e proprietà aggiuntivi per consentire all'utente di raccogliere informazioni sulla riga.</span><span class="sxs-lookup"><span data-stu-id="a9a0f-124">Additional methods and properties are defined which allows users to gather line information.</span></span>  
  
```vb  
Class LineInfoElement  
   Inherits XmlElement  
   Implements IXmlLineInfo  
   Private lineNumber As Integer = 0  
   Private linePosition As Integer = 0  
  
   Friend Sub New(prefix As String, localname As String, nsURI As String, doc As XmlDocument)  
      MyBase.New(prefix, localname, nsURI, doc)  
      CType(doc, LineInfoDocument).IncrementElementCount()  
   End Sub 'New  
  
   Public Sub SetLineInfo(linenum As Integer, linepos As Integer)  
      lineNumber = linenum  
      linePosition = linepos  
   End Sub 'SetLineInfo  
  
   Public ReadOnly Property LineNumber() As Integer  
      Get  
         Return lineNumber  
      End Get  
   End Property  
  
   Public ReadOnly Property LinePosition() As Integer  
      Get  
         Return linePosition  
      End Get  
   End Property  
  
   Public Function HasLineInfo() As Boolean  
      Return True  
   End Function 'HasLineInfo  
End Class 'LineInfoElement ' End LineInfoElement class.  
```  
  
```csharp  
class LineInfoElement : XmlElement, IXmlLineInfo {  
   int lineNumber = 0;  
   int linePosition = 0;  
   internal LineInfoElement( string prefix, string localname, string nsURI, XmlDocument doc ) : base( prefix, localname, nsURI, doc ) {  
       ( (LineInfoDocument)doc ).IncrementElementCount();  
  }     
  public void SetLineInfo( int linenum, int linepos ) {  
      lineNumber = linenum;  
      linePosition = linepos;  
  }  
  public int LineNumber {  
     get {  
       return lineNumber;  
     }  
  }  
  public int LinePosition {  
      get {  
        return linePosition;  
      }  
  }  
  public bool HasLineInfo() {   
    return true;   
  }  
} // End LineInfoElement class.  
```  
  
### <a name="example"></a><span data-ttu-id="a9a0f-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="a9a0f-125">Example</span></span>  
 <span data-ttu-id="a9a0f-126">Nell'esempio seguente viene contato il numero di elementi in un documento XML.</span><span class="sxs-lookup"><span data-stu-id="a9a0f-126">The following example counts the number of elements in an XML document.</span></span>  
  
```vb  
Imports System  
Imports System.Xml  
Imports System.IO  
  
 _  
  
Class LineInfoDocument  
   Inherits XmlDocument  
  
   Private elementCount As Integer  
  
   Friend Sub New()  
      elementCount = 0  
   End Sub 'New  
  
   Public Overrides Function CreateElement(prefix As String, localname As String, nsURI As String) As XmlElement  
      Dim elem As New LineInfoElement(prefix, localname, nsURI, Me)  
      Return elem  
   End Function 'CreateElement  
  
   Public Sub IncrementElementCount()  
      elementCount += 1  
   End Sub 'IncrementElementCount  
  
   Public Function GetCount() As Integer  
      Return elementCount  
   End Function 'GetCount  
End Class 'LineInfoDocument  
 _ 'End LineInfoDocument class.  
  
Class LineInfoElement  
   Inherits XmlElement  
  
   Friend Sub New(prefix As String, localname As String, nsURI As String, doc As XmlDocument)  
      MyBase.New(prefix, localname, nsURI, doc)  
      CType(doc, LineInfoDocument).IncrementElementCount()  
   End Sub 'New  
End Class 'LineInfoElement  
 _ 'End LineInfoElement class.  
  
Public Class Test  
  
   Private filename As [String] = "book.xml"  
  
   Public Shared Sub Main()  
  
      Dim doc As New LineInfoDocument()  
      doc.Load(filename)  
      Console.WriteLine("Number of elements in {0}: {1}", filename, doc.GetCount())  
   End Sub 'Main   
End Class 'Test  
```  
  
```csharp  
using System;  
using System.Xml;  
using System.IO;  
  
class LineInfoDocument : XmlDocument {  
  
  int elementCount;  
  internal LineInfoDocument():base() {  
    elementCount = 0;  
  }  
  
  public override XmlElement CreateElement( string prefix, string localname, string nsURI) {  
    LineInfoElement elem = new LineInfoElement(prefix, localname, nsURI, this );  
    return elem;  
  }  
  
  public void IncrementElementCount() {  
     elementCount++;  
  }  
  
  public int GetCount() {  
     return elementCount;  
  }  
} // End LineInfoDocument class.  
  
class LineInfoElement:XmlElement {  
  
    internal LineInfoElement( string prefix, string localname, string nsURI, XmlDocument doc ):base( prefix,localname,nsURI, doc ){  
      ((LineInfoDocument)doc).IncrementElementCount();  
    }     
} // End LineInfoElement class.  
  
public class Test {  
  
  const String filename = "book.xml";  
  public static void Main() {  
  
     LineInfoDocument doc =new LineInfoDocument();  
     doc.Load(filename);      
     Console.WriteLine("Number of elements in {0}: {1}", filename, doc.GetCount());  
  
  }  
}   
```  
  
##### <a name="input"></a><span data-ttu-id="a9a0f-127">Input</span><span class="sxs-lookup"><span data-stu-id="a9a0f-127">Input</span></span>  
 <span data-ttu-id="a9a0f-128">books.xml</span><span class="sxs-lookup"><span data-stu-id="a9a0f-128">book.xml</span></span>  
  
```xml  
<!--sample XML fragment-->  
<book genre='novel' ISBN='1-861001-57-5' misc='sale-item'>  
  <title>The Handmaid's Tale</title>  
  <price>14.95</price>  
</book>  
```  
  
##### <a name="output"></a><span data-ttu-id="a9a0f-129">Output</span><span class="sxs-lookup"><span data-stu-id="a9a0f-129">Output</span></span>  
  
```  
Number of elements in book.xml: 3  
```  
  
 <span data-ttu-id="a9a0f-130">Un esempio in cui viene illustrato come estendere le classi del DOM XML (System.Xml) è riportato in www.gotdotnet.com/userfiles/XMLDom/extendDOM.zip.</span><span class="sxs-lookup"><span data-stu-id="a9a0f-130">For an example showing how to extend the XML DOM classes (System.Xml), see www.gotdotnet.com/userfiles/XMLDom/extendDOM.zip.</span></span>  
  
## <a name="node-event-handler"></a><span data-ttu-id="a9a0f-131">Gestore degli eventi dei nodi</span><span class="sxs-lookup"><span data-stu-id="a9a0f-131">Node Event Handler</span></span>  
 <span data-ttu-id="a9a0f-132">Nell'implementazione del DOM da parte di .NET Framework è compreso anche un sistema di eventi che consente di ricevere e gestire gli eventi quando i nodi di un documento XML vengono modificati.</span><span class="sxs-lookup"><span data-stu-id="a9a0f-132">The .NET Framework implementation of the DOM also includes an event system that enables you to receive and handle events when nodes in an XML document change.</span></span> <span data-ttu-id="a9a0f-133">Usando le classi <xref:System.Xml.XmlNodeChangedEventHandler> e <xref:System.Xml.XmlNodeChangedEventArgs>, è possibile acquisire gli eventi`NodeChanged`, `NodeChanging`, `NodeInserted`, `NodeInserting`, `NodeRemoved` e `NodeRemoving`.</span><span class="sxs-lookup"><span data-stu-id="a9a0f-133">Using the <xref:System.Xml.XmlNodeChangedEventHandler> and <xref:System.Xml.XmlNodeChangedEventArgs> classes, you can capture `NodeChanged`, `NodeChanging`, `NodeInserted`, `NodeInserting`, `NodeRemoved`, and `NodeRemoving` events.</span></span>  
  
 <span data-ttu-id="a9a0f-134">Il processo di gestione degli eventi nelle classi derivate è identico a quello nelle classi originali del DOM.</span><span class="sxs-lookup"><span data-stu-id="a9a0f-134">The event-handling process works exactly the same in derived classes as it would in the original DOM classes.</span></span>  
  
 <span data-ttu-id="a9a0f-135">Per altre informazioni sulla gestione degli eventi del nodo, vedere [Eventi](../../../../docs/standard/events/index.md) e <xref:System.Xml.XmlNodeChangedEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="a9a0f-135">For more information regarding node event handling, see [Events](../../../../docs/standard/events/index.md) and <xref:System.Xml.XmlNodeChangedEventHandler>.</span></span>  
  
## <a name="default-attributes-and-the-createelement-method"></a><span data-ttu-id="a9a0f-136">Attributi predefiniti e metodo CreateElement</span><span class="sxs-lookup"><span data-stu-id="a9a0f-136">Default Attributes and the CreateElement Method</span></span>  
 <span data-ttu-id="a9a0f-137">Se si esegue l'override del metodo <xref:System.Xml.XmlDocument.CreateElement%2A> in una classe derivata, gli attributi predefiniti non vengono aggiunti alla creazione di nuovi elementi durante la modifica del documento.</span><span class="sxs-lookup"><span data-stu-id="a9a0f-137">If you are overriding the <xref:System.Xml.XmlDocument.CreateElement%2A> method in a derived class, default attributes are not added when you are creating new elements while editing the document.</span></span> <span data-ttu-id="a9a0f-138">Questo problema si verifica solo durante la modifica.</span><span class="sxs-lookup"><span data-stu-id="a9a0f-138">This is only an issue while editing.</span></span> <span data-ttu-id="a9a0f-139">Poiché il metodo <xref:System.Xml.XmlDocument.CreateElement%2A> è responsabile dell'aggiunta di attributi predefiniti a un <xref:System.Xml.XmlDocument>, è necessario codificare questa funzionalità nel metodo <xref:System.Xml.XmlDocument.CreateElement%2A>.</span><span class="sxs-lookup"><span data-stu-id="a9a0f-139">Because the <xref:System.Xml.XmlDocument.CreateElement%2A> method is responsible for adding default attributes to an <xref:System.Xml.XmlDocument>, you must code this functionality in the <xref:System.Xml.XmlDocument.CreateElement%2A> method.</span></span> <span data-ttu-id="a9a0f-140">Se si carica un <xref:System.Xml.XmlDocument> in cui sono compresi attributi predefiniti, questi verranno gestiti correttamente.</span><span class="sxs-lookup"><span data-stu-id="a9a0f-140">If you are loading an <xref:System.Xml.XmlDocument> that includes default attributes, they will be handled correctly.</span></span> <span data-ttu-id="a9a0f-141">Per altre informazioni sugli attributi predefiniti, vedere [Creazione di nuovi attributi per gli elementi nel DOM](../../../../docs/standard/data/xml/creating-new-attributes-for-elements-in-the-dom.md).</span><span class="sxs-lookup"><span data-stu-id="a9a0f-141">For more information on default attributes, see [Creating New Attributes for Elements in the DOM](../../../../docs/standard/data/xml/creating-new-attributes-for-elements-in-the-dom.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9a0f-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a9a0f-142">See Also</span></span>  
 [<span data-ttu-id="a9a0f-143">Modello DOM (Document Object Mode) XML</span><span class="sxs-lookup"><span data-stu-id="a9a0f-143">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
