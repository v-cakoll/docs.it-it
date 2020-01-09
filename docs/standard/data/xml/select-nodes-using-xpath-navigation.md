---
title: Selezione di nodi utilizzando la navigazione XPath
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 8e4450dc-56b3-472b-b467-32f5694f83ad
ms.openlocfilehash: 8f4136683f13a52b84ab9e8bfd69f30c8914e029
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710180"
---
# <a name="select-nodes-using-xpath-navigation"></a>Selezione di nodi utilizzando la navigazione XPath
Il DOM (Document Object Model) XML contiene metodi che consentono di usare la navigazione XPath (XML Path Language) per eseguire query sulle informazioni del DOM. È possibile usare XPath per individuare un singolo nodo specifico o tutti i nodi che corrispondono a certi criteri.  
  
## <a name="xpath-select-methods"></a>Metodi di selezione XPath  
 Le classi DOM forniscono due metodi per la selezione XPath: il metodo <xref:System.Xml.XmlNode.SelectSingleNode%2A> e il metodo <xref:System.Xml.XmlNode.SelectNodes%2A>. Il metodo <xref:System.Xml.XmlNode.SelectSingleNode%2A> restituisce il primo nodo che corrisponde ai criteri di selezione. Il metodo <xref:System.Xml.XmlNode.SelectNodes%2A> restituisce un oggetto <xref:System.Xml.XmlNodeList> contenente i nodi corrispondenti.  
  
 Nell'esempio seguente viene usato il metodo <xref:System.Xml.XmlNode.SelectSingleNode%2A> per selezionare il primo nodo `book` nel quale il cognome dell'autore soddisfa i criteri specificati. Il file bookstore.xml, fornito alla fine di questo argomento, viene usato come file di input.  
  
```vb  
Dim doc As New XmlDocument()  
doc.Load("bookstore.xml")  
Dim root As XmlNode = doc.DocumentElement  
  
' Add the namespace.  
Dim nsmgr As New XmlNamespaceManager(doc.NameTable)  
nsmgr.AddNamespace("bk", "urn:newbooks-schema")  
  
' Select and display the first node in which the author's   
' last name is Kingsolver.  
Dim node As XmlNode = root.SelectSingleNode( _  
     "descendant::bk:book[bk:author/bk:last-name='Kingsolver']", nsmgr)  
Console.WriteLine(node.InnerXml)  
```  
  
```csharp  
// Load the document and set the root element.  
XmlDocument doc = new XmlDocument();  
doc.Load("bookstore.xml");  
XmlNode root = doc.DocumentElement;  
  
// Add the namespace.  
XmlNamespaceManager nsmgr = new XmlNamespaceManager(doc.NameTable);  
nsmgr.AddNamespace("bk", "urn:newbooks-schema");  
  
// Select and display the first node in which the author's   
// last name is Kingsolver.  
XmlNode node = root.SelectSingleNode(  
    "descendant::bk:book[bk:author/bk:last-name='Kingsolver']", nsmgr);  
Console.WriteLine(node.InnerXml);  
```  
  
 Nell'esempio successivo viene usato il metodo <xref:System.Xml.XmlNode.SelectNodes%2A> per selezionare tutti i nodi libro in cui il prezzo è maggiore di una quantità specificata. Il prezzo di ogni libro nell'elenco selezionato viene quindi ridotto a livello di codice del dieci percento. Infine, il file aggiornato viene scritto nella console. Il file bookstore.xml, fornito alla fine di questo argomento, viene usato come file di input.  
  
```vb  
' Load the document and set the root element.  
Dim doc As New XmlDocument()  
doc.Load("bookstore.xml")  
Dim root As XmlNode = doc.DocumentElement  
  
' Add the namespace.  
Dim nsmgr As New XmlNamespaceManager(doc.NameTable)  
nsmgr.AddNamespace("bk", "urn:newbooks-schema")  
  
' Select all nodes where the book price is greater than 10.00.  
Dim nodeList As XmlNodeList = root.SelectNodes( _  
     "descendant::bk:book[bk:price>10.00]", nsmgr)  
For Each book As XmlNode In nodeList  
     Dim price As Double  
     price = Math.Round(Convert.ToSingle( _  
          book.LastChild.InnerText) * 0.9, 2)  
     book.LastChild.InnerText = price.ToString()  
Next  
  
' Display the updated document.  
doc.Save(Console.Out)  
```  
  
```csharp  
// Load the document and set the root element.  
XmlDocument doc = new XmlDocument();  
doc.Load("bookstore.xml");  
XmlNode root = doc.DocumentElement;  
  
// Add the namespace.  
XmlNamespaceManager nsmgr = new XmlNamespaceManager(doc.NameTable);  
nsmgr.AddNamespace("bk", "urn:newbooks-schema");  
  
// Select all nodes where the book price is greater than 10.00.  
XmlNodeList nodeList = root.SelectNodes(  
     "descendant::bk:book[bk:price>10.00]", nsmgr);  
foreach (XmlNode book in nodeList)  
{  
     // Discount prices by 10%.  
     double price;  
     price = Math.Round(Convert.ToSingle(  
          book.LastChild.InnerText) * 0.9, 2);  
     book.LastChild.InnerText = price.ToString();  
}  
  
// Display the updated document.  
doc.Save(Console.Out);  
```  
  
 Negli esempi precedenti la query XPath inizia dall'elemento del documento. Impostando il punto iniziale per la query XPath si imposta il nodo di contesto, che è il punto da cui inizia la query XPath. Se non si desidera iniziare dall'elemento del documento, ma dal primo elemento figlio di tale elemento, è possibile codificare l'istruzione Select come segue:  
  
```vb  
doc.DocumentElement.FirstChild.SelectNodes(. . . )  
```  
  
```csharp  
this doc.DocumentElement.FirstChild.SelectNodes(. . .);  
```  
  
 Tutti gli oggetti <xref:System.Xml.XmlNodeList> sono sincronizzati con il documento sottostante. Per questo motivo, se si scorre l'elenco dei nodi e si modifica il valore di un nodo, quest'ultimo verrà aggiornato anche nel documento dal quale proviene. Si noti nell'esempio precedente che quando un nodo viene modificato nell'oggetto <xref:System.Xml.XmlNodeList> selezionato, viene modificato anche il documento sottostante.  
  
> [!NOTE]
> Quando si modifica il documento sottostante, è consigliabile eseguire nuovamente la selezione. Se il nodo modificato è un nodo che potrebbe causare l'aggiunta del nodo all'elenco dove non figurava in precedenza o la relativa rimozione dall'elenco di nodi, è possibile che tale elenco non sia preciso.  
  
## <a name="namespaces-in-xpath-expressions"></a>Spazi dei nomi nelle espressioni XPath  
 Le espressioni XPath possono includere spazi dei nomi. La risoluzione dello spazio dei nomi viene supportata usando il tipo <xref:System.Xml.XmlNamespaceManager>. Se l'espressione XPath include un prefisso, sarà necessario aggiungere la coppia costituita dal prefisso e dall'URI dello spazio dei nomi all'oggetto <xref:System.Xml.XmlNamespaceManager> e l'oggetto <xref:System.Xml.XmlNamespaceManager> verrà passato al metodo <xref:System.Xml.XmlNode.SelectNodes%28System.String%2CSystem.Xml.XmlNamespaceManager%29> o <xref:System.Xml.XmlNode.SelectSingleNode%28System.String%2CSystem.Xml.XmlNamespaceManager%29>. Si noti che negli esempi di codice precedenti viene usato l'oggetto <xref:System.Xml.XmlNamespaceManager> per risolvere lo spazio dei nomi del documento bookstore.xml.  
  
> [!NOTE]
> Se l'espressione XPath non include un prefisso, si presuppone che l'URI dello spazio dei nomi (Uniform Resource Identifier) sia lo spazio dei nomi vuoto. Se l'XML include uno spazio dei nomi predefinito, sarà necessario aggiungere un prefisso e un URI dello spazio dei nomi anche all'oggetto <xref:System.Xml.XmlNamespaceManager>. In caso contrario, non verrà selezionato alcun nodo.  
  
#### <a name="input-file"></a>File di input  
 Di seguito è riportato il file bookstore.xml usato come file di input negli esempi di questo argomento:  
  
```xml  
<?xml version='1.0'?>  
<bookstore xmlns="urn:newbooks-schema">  
  <book genre="novel" style="hardcover">  
    <title>The Handmaid's Tale</title>  
    <author>  
      <first-name>Margaret</first-name>  
      <last-name>Atwood</last-name>  
    </author>  
    <price>19.95</price>  
  </book>  
  <book genre="novel" style="other">  
    <title>The Poisonwood Bible</title>  
    <author>  
      <first-name>Barbara</first-name>  
      <last-name>Kingsolver</last-name>  
    </author>  
    <price>11.99</price>  
  </book>  
  <book genre="novel" style="paperback">  
    <title>The Bean Trees</title>  
    <author>  
      <first-name>Barbara</first-name>  
      <last-name>Kingsolver</last-name>  
    </author>  
    <price>5.99</price>  
  </book>  
</bookstore>  
```  
  
## <a name="see-also"></a>Vedere anche

- [Modello DOM (Document Object Mode) XML](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
