---
title: Gestione di spazi dei nomi in un documento XML
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 682643fc-b848-4e42-8c0d-50deeaeb5f2a
ms.openlocfilehash: 1b3e57c0a8a37574a92d23cf1d623301cc54b984
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "82796152"
---
# <a name="managing-namespaces-in-an-xml-document"></a>Gestione di spazi dei nomi in un documento XML
Tramite gli spazi dei nomi XML è possibile associare i nomi degli attributi e degli elementi di un documento XML a URI personalizzati e predefiniti. Per creare queste associazioni, è possibile definire i prefissi per gli URI dello spazio dei nomi e usare i prefissi in questione per qualificare i nomi degli attributi e degli elementi nei dati XML. Con gli spazi dei nomi è possibile evitare i conflitti tra i nomi degli elementi e degli attributi e consentire la gestione e la convalida degli elementi e degli attributi con lo stesso nome in modi diversi.  
  
<a name="declare"></a>
## <a name="declaring-namespaces"></a>Dichiarazione degli spazi dei nomi  
 Per dichiarare uno spazio dei nomi in un elemento, usare l'attributo `xmlns:` riportato di seguito.  
  
 `xmlns:<name>=<"uri">`  
  
 dove `<name>` è il prefisso dello spazio dei nomi e `<"uri">` è l'URI tramite cui viene identificato lo spazio dei nomi. Al termine della dichiarazione, il prefisso può essere usato per qualificare elementi e attributi in un documento XML e associarli all'URI dello spazio dei nomi. Poiché viene usato nell'intero documento, il prefisso dello spazio dei nomi deve essere breve.  
  
 Nell'esempio vengono definiti due elementi `BOOK`. Il primo elemento è qualificato dal prefisso `mybook`, mentre il secondo dal prefisso `bb`. Ogni prefisso è associato a un diverso URI dello spazio dei nomi:  
  
```xml  
<mybook:BOOK xmlns:mybook="http://www.contoso.com/books.dtd">  
<bb:BOOK xmlns:bb="urn:blueyonderairlines" />
</mybook>
```  
  
 Per indicare che un elemento fa parte di un determinato spazio dei nomi, aggiungervi il prefisso dello spazio dei nomi. Ad esempio, se un elemento `Author` appartiene allo spazio dei nomi `mybook`, viene dichiarato come `<mybook:Author>`.  
  
<a name="scope"></a>
## <a name="declaration-scope"></a>Ambito della dichiarazione  
 Uno spazio dei nomi entra in vigore dal punto della dichiarazione fino alla fine dell'elemento in cui è stato dichiarato. In questo esempio, lo spazio dei nomi definito nell'elemento `BOOK` non è applicabile agli elementi esterni all'elemento `BOOK`, come l'elemento `Publisher`:  
  
```xml  
<Author>Joe Smith</Author>  
<BOOK xmlns:book="http://www.contoso.com">  
    <title>My Wonderful Day</title>  
      <price>$3.95</price>  
</BOOK>  
<Publisher>  
    <Name>MSPress</Name>  
</Publisher>  
```  
  
 Uno spazio dei nomi deve essere dichiarato prima di poterlo usare, ma non deve trovarsi all'inizio del documento XML.  
  
 Quando si usano più spazi dei nomi in un documento XML, è possibile definire uno spazio dei nomi come spazio dei nomi predefinito per creare un documento più chiaro. Lo spazio dei nomi predefinito viene dichiarato nell'elemento radice e si applica a tutti gli elementi non qualificati nel documento. Gli spazi dei nomi predefiniti sono applicabili solo agli elementi, non agli attributi.  
  
 Per usare lo spazio dei nomi predefinito, omettere il prefisso e i due punti dalla dichiarazione nell'elemento:  
  
```xml  
<BOOK xmlns="http://www.contoso.com/books.dtd">  
...
</BOOK>
```  
  
## <a name="managing-namespaces"></a>Gestione degli spazi dei nomi  
 Tramite la classe <xref:System.Xml.XmlNamespaceManager> viene archiviata una raccolta di URI dello spazio dei nomi e i relativi prefissi consentendo all'utente di cercare, aggiungere e rimuovere spazi dei nomi da questa raccolta. In determinati contesti, questa classe viene richiesta per migliorare le prestazioni di elaborazione del codice XML. Ad esempio, la classe <xref:System.Xml.Xsl.XsltContext> usa <xref:System.Xml.XmlNamespaceManager> per fornire il supporto XPath.  
  
 Il gestore dello spazio dei nomi non esegue convalide sugli spazi dei nomi, ma si presuppone che i prefissi e gli spazi dei nomi siano già stati verificati e siano conformi alla specifica [W3C Namespaces](https://www.w3.org/TR/REC-xml-names/).  
  
> [!NOTE]
> LINQ to XML in [C#](../../../csharp/programming-guide/concepts/linq/linq-to-xml-overview.md) e [Visual Basic](../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md) non usano <xref:System.Xml.XmlNamespaceManager> per gestire gli spazi dei nomi. Per informazioni sulla gestione di spazi dei nomi quando si usa LINQ to XML, vedere [Uso degli spazi dei nomi XML (C#)](../../../csharp/programming-guide/concepts/linq/namespaces-overview-linq-to-xml.md) e [Uso degli spazi dei nomi XML (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md) nella documentazione di LINQ.  
  
 Di seguito sono riportate alcune attività di gestione e ricerca eseguibili con la classe <xref:System.Xml.XmlNamespaceManager>. Per altre informazioni ed esempi, seguire i collegamenti alla pagina di riferimento per ogni metodo o proprietà.  
  
|A|Uso|  
|--------|---------|  
|Aggiungere uno spazio dei nomi|Metodo <xref:System.Xml.XmlNamespaceManager.AddNamespace%2A>|  
|Rimuovere uno spazio dei nomi|Metodo <xref:System.Xml.XmlNamespaceManager.RemoveNamespace%2A>|  
|Trovare l'URI per lo spazio dei nomi predefinito|Proprietà <xref:System.Xml.XmlNamespaceManager.DefaultNamespace%2A>|  
|Trovare l'URI per un prefisso dello spazio dei nomi|Metodo <xref:System.Xml.XmlNamespaceManager.LookupNamespace%2A>|  
|Trovare il prefisso per un URI dello spazio dei nomi|Metodo <xref:System.Xml.XmlNamespaceManager.LookupPrefix%2A>|  
|Ottenere un elenco di spazi dei nomi nel nodo corrente|Metodo <xref:System.Xml.XmlNamespaceManager.GetNamespacesInScope%2A>|  
|Creare l'ambito di uno spazio dei nomi|Metodi <xref:System.Xml.XmlNamespaceManager.PushScope%2A> e <xref:System.Xml.XmlNamespaceManager.PopScope%2A>|  
|Verificare se un prefisso è definito nell'ambito corrente|Metodo <xref:System.Xml.XmlNamespaceManager.HasNamespace%2A>|  
|Ottenere la tabella dei nomi usata per ricercare i prefissi e gli URI|Proprietà <xref:System.Xml.XmlNamespaceManager.NameTable%2A>|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Xml.XmlNamespaceManager>
- [Documenti e dati XML](../../../../docs/standard/data/xml/index.md)
