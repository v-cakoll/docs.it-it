---
title: Confronto di oggetti con XmlNameTable
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
ms.assetid: 8d94e041-d340-4ddf-9a2c-d7319e3f4f86
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 0cd1a3bad69499b4804299adecabad3a43b5eab1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="object-comparison-using-xmlnametable"></a>Confronto di oggetti con XmlNameTable
**XmlDocument**, quando creato, dispone di una tabella dei nomi creata specificamente per quel documento. Quando si carica il XML nel documento o vengono creati nuovi elementi o attributi, i nomi di attributi ed elementi vengono inseriti i **XmlNameTable**. È inoltre possibile creare un **XmlDocument** utilizzando una classe **NameTable** da un altro documento. Quando **XmlDocuments** vengono creati con il costruttore che accetta un **XmlNameTable** parametro, il documento ha accesso ai nomi dei nodi, spazi dei nomi e prefissi già archiviati nella  **XmlNameTable**. Indipendentemente da come viene caricata la tabella dei nomi, una volta che i nomi vengono archiviati nella tabella, potranno essere confrontati rapidamente, usando il confronto degli oggetti invece del confronto delle stringhe. Possono inoltre aggiungere stringhe alla tabella dei nomi usando il <xref:System.Xml.NameTable.Add%2A>. Esempio di codice seguente viene illustrata la creazione di una tabella di nome e la stringa **MyString** da aggiungere alla tabella. Successivamente, un **XmlDocument** viene creato utilizzando quella tabella e i nomi degli elementi e attributi in **Myfile.xml** vengono aggiunti alla tabella dei nomi esistente.  
  
```vb  
Dim nt As New NameTable()  
nt.Add("MyString")  
Dim doc As New XmlDocument(nt)  
doc.Load("Myfile.xml")  
```  
  
```csharp  
NameTable nt = new NameTable();  
nt.Add("MyString");  
XmlDocument doc = new XmlDocument(nt);  
doc.Load("Myfile.xml");  
```  
  
 Nell'esempio di codice seguente viene illustrata la creazione di un documento, l'aggiunta di due nuovi elementi al documento, che implica anche l'aggiunta alla tabella dei nomi del documento, e il confronto degli oggetti in base ai nomi.  
  
```vb  
Dim doc1 As XmlDocument = imp.CreateDocument()  
Dim node1 As XmlElement = doc.CreateElement("node1")  
Dim doc2 As XmlDocument = imp.CreateDocument()  
Dim node2 As XmlElement = doc.CreateElement("node2")  
if (CType(node1.Name, object) = CType(node2.Name, object))  
```  
  
```csharp  
XmlDocument doc1 = imp.CreateDocument();  
node1 = doc1.CreateElement ("node1");  
XmlDocument doc2 = imp.CreateDocument();  
node2 = doc2.CreateElement ("node1");  
if (((object)node1.Name) == ((object)node2.Name))  
{ ...  
```  
  
 In genere, il passaggio di una tabella dei nomi tra due documenti si verifica quando lo stesso tipo di documento viene elaborato ripetutamente, come nel caso di documenti d'ordine in un sito Web di e-commerce, in modo conforme a uno schema XSD (XML Schema Definition Language) o a una DTD (Document Type Definition), dove si ripetono le stesse stringhe. Usando la stessa tabella dei nomi si ottengono migliori prestazioni in quanto lo stesso nome di elemento ricorre in più documenti.  
  
## <a name="see-also"></a>Vedere anche  
 [XML Document Object Model (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
