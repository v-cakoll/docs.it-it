---
title: Confronto di oggetti con XmlNameTable
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 8d94e041-d340-4ddf-9a2c-d7319e3f4f86
ms.openlocfilehash: 63278f1aa1fe47377d2dae322a9d12338bbe45dd
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710531"
---
# <a name="object-comparison-using-xmlnametable"></a><span data-ttu-id="b23f0-102">Confronto di oggetti con XmlNameTable</span><span class="sxs-lookup"><span data-stu-id="b23f0-102">Object Comparison Using XmlNameTable</span></span>
<span data-ttu-id="b23f0-103">Al momento della creazione, ogni **XmlDocument** ha una tabella dei nomi creata specificamente per quel documento.</span><span class="sxs-lookup"><span data-stu-id="b23f0-103">**XmlDocuments**, when created, have a name table created specifically for that document.</span></span> <span data-ttu-id="b23f0-104">Quando il codice XML viene caricato nel documento o vengono creati nuovi elementi o attributi, i nomi di attributi ed elementi vengono inseriti nella **XmlNameTable**.</span><span class="sxs-lookup"><span data-stu-id="b23f0-104">When XML is loaded into the document, or new elements or attributes are created, the attribute and element names are put into the **XmlNameTable**.</span></span> <span data-ttu-id="b23f0-105">È anche possibile creare un **XmlDocument** usando una **NameTable** esistente di un altro documento.</span><span class="sxs-lookup"><span data-stu-id="b23f0-105">You can also create an **XmlDocument** using an existing **NameTable** from another document.</span></span> <span data-ttu-id="b23f0-106">Quando gli **XmlDocument** vengono creati con il costruttore che accetta un parametro **XmlNameTable**, il documento ha accesso ai nomi dei nodi, agli spazi dei nomi e ai prefissi già archiviati nella **XmlNameTable**.</span><span class="sxs-lookup"><span data-stu-id="b23f0-106">When **XmlDocuments** are created with the constructor that takes an **XmlNameTable** parameter, the document has access to the node names, namespaces, and prefixes already stored in the **XmlNameTable**.</span></span> <span data-ttu-id="b23f0-107">Indipendentemente da come viene caricata la tabella dei nomi, una volta che i nomi vengono archiviati nella tabella, potranno essere confrontati rapidamente, usando il confronto degli oggetti invece del confronto delle stringhe.</span><span class="sxs-lookup"><span data-stu-id="b23f0-107">Regardless of how the name table is loaded with names, once the names are stored in the table, names can be compared quickly using object comparison instead of string comparison.</span></span> <span data-ttu-id="b23f0-108">È anche possibile aggiungere stringhe alla tabella dei nomi usando <xref:System.Xml.NameTable.Add%2A>.</span><span class="sxs-lookup"><span data-stu-id="b23f0-108">Strings can also be added to the name table using the <xref:System.Xml.NameTable.Add%2A>.</span></span> <span data-ttu-id="b23f0-109">L'esempio di codice seguente illustra la creazione di una tabella dei nomi e l'aggiunta alla tabella della stringa **MyString**.</span><span class="sxs-lookup"><span data-stu-id="b23f0-109">The following code sample shows a name table being created and the string **MyString** being added to the table.</span></span> <span data-ttu-id="b23f0-110">Successivamente viene creato un **XmlDocument** usando quella tabella e i nomi degli elementi e degli attributi contenuti in **Myfile.xml** vengono aggiunti alla tabella dei nomi esistente.</span><span class="sxs-lookup"><span data-stu-id="b23f0-110">After that, an **XmlDocument** is created using that table, and the element and attribute names in **Myfile.xml** are added to the existing name table.</span></span>  
  
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
  
 <span data-ttu-id="b23f0-111">Nell'esempio di codice seguente viene illustrata la creazione di un documento, l'aggiunta di due nuovi elementi al documento, che implica anche l'aggiunta alla tabella dei nomi del documento, e il confronto degli oggetti in base ai nomi.</span><span class="sxs-lookup"><span data-stu-id="b23f0-111">The following code example shows the creation of a document, two new elements being added to the document, which also adds them to the document name table, and the object comparison on the names.</span></span>  
  
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
  
 <span data-ttu-id="b23f0-112">In genere, il passaggio di una tabella dei nomi tra due documenti si verifica quando lo stesso tipo di documento viene elaborato ripetutamente, come nel caso di documenti d'ordine in un sito Web di e-commerce, in modo conforme a uno schema XSD (XML Schema Definition Language) o a una DTD (Document Type Definition), dove si ripetono le stesse stringhe.</span><span class="sxs-lookup"><span data-stu-id="b23f0-112">The above scenario of a name table passed between two documents is typical when the same type of document is being processed repeatedly, such as order documents at an ecommerce site, which conform to an XML Schema definition language (XSD) schema or document type definition (DTD) and the same strings are repeated.</span></span> <span data-ttu-id="b23f0-113">Usando la stessa tabella dei nomi si ottengono migliori prestazioni in quanto lo stesso nome di elemento ricorre in più documenti.</span><span class="sxs-lookup"><span data-stu-id="b23f0-113">Using the same name table gives a performance improvement, as the same element name occurs in multiple documents.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b23f0-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b23f0-114">See also</span></span>

- [<span data-ttu-id="b23f0-115">Modello DOM (Document Object Mode) XML</span><span class="sxs-lookup"><span data-stu-id="b23f0-115">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
