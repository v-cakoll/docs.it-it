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
# <a name="creating-new-attributes-for-elements-in-the-dom"></a>Creazione di nuovi attributi per gli elementi nel DOM

La creazione di nuovi attributi è diversa dalla creazione di altri tipi di nodi, perché gli attributi non sono nodi, ma proprietà di un nodo di elemento e sono contenuti in una classe **XmlAttributeCollection** associata all'elemento. Sono disponibili diversi modi per creare un attributo e associarlo a un elemento:

- Ottenere il nodo dell'elemento e usare **SetAttribute** per aggiungere un attributo alla raccolta di attributi di tale elemento.

- Creare un nodo **XmlAttribute** usando il metodo **CreateAttribute**, ottenere il nodo dell'elemento, quindi usare **SetAttributeNode** per aggiungere il nodo alla raccolta di attributi di tale elemento.

Nell'esempio seguente viene illustrato come aggiungere un attributo a un elemento utilizzando il metodo **SetAttribute** :

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

Nell'esempio seguente viene illustrata la creazione di un nuovo attributo con il metodo **CreateAttribute**. L'attributo viene quindi aggiunto alla raccolta di attributi dell'elemento **book** con il metodo **SetAttributeNode**.

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

L'esempio di codice completo è disponibile in <xref:System.Xml.XmlDocument.CreateAttribute%2A>.

È anche possibile creare un nodo **XmlAttribute** e usare i metodi **InsertBefore** o **InsertAfter** per inserirlo nella posizione appropriata nella raccolta. Se è già presente un attributo con lo stesso nome nella raccolta di attributi, il nodo **XmlAttribute** esistente viene rimosso dalla raccolta e il nuovo nodo **XmlAttribute** viene inserito. Questa operazione viene eseguita come nel metodo **SetAttribute**. Questi metodi accettano come parametro un nodo esistente come punto di riferimento per eseguire **InsertBefore** e **InsertAfter**. Se non viene fornito un nodo di riferimento che indica dove inserire il nuovo nodo, per impostazione predefinita il metodo **InsertAfter** inserirà il nuovo nodo all'inizio della raccolta. Se non viene fornito alcun nodo di riferimento, la posizione predefinita di **InsertBefore** è alla fine della raccolta.

Se è stato creato un **XmlNamedNodeMap** di attributi, è possibile aggiungere un attributo in base al nome usando il metodo <xref:System.Xml.XmlNamedNodeMap.SetNamedItem%2A>. Per altre informazioni, vedere [Raccolte di nodi in NamedNodeMaps e NodeLists](node-collections-in-namednodemaps-and-nodelists.md).

## <a name="default-attributes"></a>Attributi predefiniti

Se si crea un elemento in cui è dichiarato un attributo predefinito, nel DOM (Document Object Model) XML verrà creato e associato all'elemento un nuovo attributo predefinito con il relativo valore. Contemporaneamente verranno creati anche i nodi figlio dell'attributo predefinito.

## <a name="attribute-child-nodes"></a>Nodi figlio attributo

Il valore del nodo di un attributo diviene i nodi figlio dell'attributo stesso. Esistono solo due tipi di nodi figlio validi: i nodi **XmlText** e i nodi **XmlEntityReference** . Si tratta di nodi figlio perché vengono elaborati come tali da metodi come **FirstChild** e **LastChild**. Questa distinzione di un attributo con nodi figlio è importante quando si tenta di rimuovere attributi o nodi figlio degli attributi. Per altre informazioni, vedere [Rimozione di attributi da un nodo di elemento nel DOM](removing-attributes-from-an-element-node-in-the-dom.md).

## <a name="see-also"></a>Vedere anche

- [Modello DOM (Document Object Mode) XML](xml-document-object-model-dom.md)
