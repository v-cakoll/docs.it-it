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
# <a name="creating-new-attributes-for-elements-in-the-dom"></a>Creazione di nuovi attributi per gli elementi nel DOM
Creazione di nuovi attributi è diversa dalla creazione di altri tipi di nodo, in quanto gli attributi non sono nodi, ma sono proprietà di un nodo di elemento e sono contenuti in un **XmlAttributeCollection** associato all'elemento. Sono disponibili diversi modi per creare un attributo e associarlo a un elemento:  
  
-   Ottenere il nodo di elemento e utilizzare **SetAttribute** per aggiungere un attributo alla raccolta di attributi di quell'elemento.  
  
-   Creare un **XmlAttribute** nodo utilizzando il **CreateAttribute** (metodo), ottenere il nodo dell'elemento, quindi utilizzare **SetAttributeNode** per aggiungere il nodo alla raccolta di attributi di tale elemento.  
  
 Nell'esempio seguente viene illustrato come aggiungere un attributo a un elemento utilizzando il **SetAttribute** metodo.  
  
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
  
 Nell'esempio seguente viene illustrato un nuovo attributo con il **CreateAttribute** metodo. Quindi l'attributo viene aggiunto alla raccolta di attributi del **book** elemento utilizzando il **SetAttributeNode** metodo.  
  
 Dato l'XML seguente:  
  
```xml  
<book genre='novel' ISBN='1-861001-57-5'>  
<title>Pride And Prejudice</title>  
</book>  
```  
  
 Creare un nuovo attributo e assegnargli un valore:  
  
```vb  
Dim attr As XmlAttribute = doc.CreateAttribute("publisher")  
   attr.Value = "WorldWide Publishing"  
```  
  
```csharp  
XmlAttribute attr = doc.CreateAttribute("publisher");  
attr.Value = "WorldWide Publishing";  
```  
  
 Quindi associarlo all'elemento:  
  
```vb  
doc.DocumentElement.SetAttributeNode(attr)  
```  
  
```csharp  
doc.DocumentElement.SetAttributeNode(attr);  
```  
  
 **Output**  
  
```xml  
<book genre="novel" ISBN="1-861001-57-5" publisher="WorldWide Publishing">  
<title>Pride And Prejudice</title>  
</book>  
```  
  
 L'esempio di codice completo è reperibile in <xref:System.Xml.XmlDocument.CreateAttribute%2A>.  
  
 È inoltre possibile creare un **XmlAttribute** nodo e utilizzo di **InsertBefore** o **InsertAfter** metodi per inserirlo nella posizione appropriata all'interno della raccolta. Se un attributo con lo stesso nome è già presente nella raccolta di attributi, esistente **XmlAttribute** nodo viene rimosso dalla raccolta e il nuovo **XmlAttribute** nodo inserito. Viene eseguita nello stesso modo di **SetAttribute** metodo. Questi metodi accettano come parametro, un nodo esistente come punto di riferimento per eseguire il **InsertBefore** e **InsertAfter**. Se non si specifica un nodo di riferimento che indica dove inserire il nuovo nodo, il valore predefinito per il **InsertAfter** metodo consiste nell'inserire il nuovo nodo all'inizio della raccolta. La posizione predefinita per il **InsertBefore**, se non viene fornito alcun nodo di riferimento, si trova alla fine della raccolta.  
  
 Se è stato creato un **XmlNamedNodeMap** di attributi, è possibile aggiungere un attributo in base al nome utilizzando il <xref:System.Xml.XmlNamedNodeMap.SetNamedItem%2A>. Per ulteriori informazioni, vedere [raccolte di nodi in NamedNodeMaps e NodeLists](../../../../docs/standard/data/xml/node-collections-in-namednodemaps-and-nodelists.md).  
  
## <a name="default-attributes"></a>Attributi predefiniti  
 Se si crea un elemento in cui è dichiarato un attributo predefinito, nel DOM (Document Object Model) XML verrà creato e associato all'elemento un nuovo attributo predefinito con il relativo valore. Contemporaneamente verranno creati anche i nodi figlio dell'attributo predefinito.  
  
## <a name="attribute-child-nodes"></a>Nodi figlio degli attributi  
 Il valore del nodo di un attributo diviene i nodi figlio dell'attributo stesso. Sono disponibili solo due tipi di nodi figlio validi: **XmlText** , nodi e **XmlEntityReference** nodi. Questi sono i nodi figlio nel senso che metodi, ad esempio **FirstChild** e **LastChild** elaborarli come nodi figlio. Questa distinzione di un attributo con nodi figlio è importante quando si tenta di rimuovere attributi o nodi figlio degli attributi. Per ulteriori informazioni, vedere [rimozione di attributi da un nodo di elemento nel DOM](../../../../docs/standard/data/xml/removing-attributes-from-an-element-node-in-the-dom.md).  
  
## <a name="see-also"></a>Vedere anche  
 [XML Document Object Model (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
