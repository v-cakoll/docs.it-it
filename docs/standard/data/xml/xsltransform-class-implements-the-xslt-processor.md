---
title: Implementazione del processore XSLT da parte della classe XslTransform
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 88373fe2-4a6b-44f9-8a62-8a3e348e3a46
ms.openlocfilehash: 73a432db9a3fcb6587184e27e6dfe9ba49010e92
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709608"
---
# <a name="xsltransform-class-implements-the-xslt-processor"></a>Implementazione del processore XSLT da parte della classe XslTransform

> [!NOTE]
> La classe <xref:System.Xml.Xsl.XslTransform> è obsoleta in .NET Framework 2.0. È possibile eseguire le trasformazioni XSLT (Extensible Stylesheet Language for Transformations) usando la classe <xref:System.Xml.Xsl.XslCompiledTransform>. Per altre informazioni, vedere [Utilizzo della classe XslCompiledTransform](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) e [Migrazione dalla classe XslTransform](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md).

La classe <xref:System.Xml.Xsl.XslTransform> è un processore XSLT che implementa la raccomandazione XSL Transformations (XSLT) Version 1.0. Il metodo <xref:System.Xml.Xsl.XslTransform.Load%2A> individua e legge i fogli di stile, mentre il metodo <xref:System.Xml.Xsl.XslTransform.Transform%2A> trasforma il documento di origine. Come documento di origine per <xref:System.Xml.XPath.IXPathNavigable> può essere usato qualsiasi archivio che implementi l'interfaccia <xref:System.Xml.Xsl.XslTransform>. Poiché .NET Framework attualmente implementa l'interfaccia <xref:System.Xml.XPath.IXPathNavigable> nelle classi <xref:System.Xml.XmlDocument>, <xref:System.Xml.XmlDataDocument> e <xref:System.Xml.XPath.XPathDocument>, è possibile usare uno qualsiasi di questi elementi come documento di origine di input per una trasformazione.

L'oggetto <xref:System.Xml.Xsl.XslTransform> in .NET Framework supporta solo la specifica XSLT 1.0, definita con lo spazio dei nomi seguente:

```xml
<xsl:stylesheet xmlns:xsl="http://www.w3.org/1999/XSL/Transform" version="1.0">
```

Usando il metodo <xref:System.Xml.Xsl.XslTransform.Load%2A>, è possibile caricare il foglio di stile da una delle seguenti classi:

- XPathNavigator

- XmlReader

- Una stringa che rappresenta un URL

Per ognuna delle classi di input sopra riportate, esiste un diverso metodo <xref:System.Xml.Xsl.XslTransform.Load%2A>. Alcuni metodi richiedono come argomento una combinazione di una di queste classi con la classe <xref:System.Xml.XmlResolver>. L'oggetto <xref:System.Xml.XmlResolver> consente di individuare le risorse a cui `<xsl:import>` o `<xsl:include>` fa riferimento nel foglio di stile. Per i metodi seguenti, viene usata come input una stringa <xref:System.Xml.XmlReader> o <xref:System.Xml.XPath.XPathNavigator>.

```vb
Overloads Public Sub Load(String)
```

```csharp
public void Load(string);
```

```vb
Overloads Public Sub Load(String, XmlResolver)
```

```csharp
public void Load(string, XmlResolver);
```

```vb
Overloads Public Sub Load(XmlReader, XmlResolver, Evidence)
```

```csharp
public void Load(XmlReader, XmlResolver, Evidence);
```

```vb
Overloads Public Sub Load(XPathNavigator, XmlResolver, Evidence)
```

```csharp
public void Load(XPathNavigator, XmlResolver, Evidence);
```

Molti dei metodi <xref:System.Xml.Xsl.XslTransform.Load%2A> sopra descritti accettano come parametro <xref:System.Xml.XmlResolver>. L'oggetto <xref:System.Xml.XmlResolver> consente di caricare il foglio di stile e qualsiasi altro eventuale foglio di stile a cui viene fatto riferimento negli elementi xsl:import e xsl:include.

Molti dei metodi <xref:System.Xml.Xsl.XslTransform.Load%2A> accettano come parametro anche Evidence, Evidence è il parametro <xref:System.Security.Policy.Evidence> associato al foglio di stile. Il livello di sicurezza del foglio di stile influenza il livello di sicurezza delle eventuali risorse a cui esso fa riferimento successivamente, quali lo script contenuto, le funzioni `document()` usate e gli oggetti di estensione usati da <xref:System.Xml.Xsl.XsltArgumentList>.

Se il foglio di stile viene caricato usando il metodo <xref:System.Xml.Xsl.XslTransform.Load%2A> contenente un parametro URL e nessun parametro evidence, l'evidenza del foglio di stile viene calcolata combinando l'URL con il sito e la zona relativi.

Se i parametri URI ed Evidence non vengono forniti, il parametro Evidence impostato per il foglio di stile è completamente attendibile. Non caricare fogli di stile da origini non attendibili né aggiungere a <xref:System.Xml.Xsl.XsltArgumentList> oggetti di estensione non attendibili.

Per altre informazioni sui livelli di sicurezza, sul parametro Evidence e su come questi influiscono sugli script, vedere [Scripting dei fogli di stile XSLT con \<msxsl:script>](../../../../docs/standard/data/xml/xslt-stylesheet-scripting-using-msxsl-script.md). Per altre informazioni sui livelli di sicurezza, sul parametro Evidence e su come questi influiscono sugli oggetti di estensione, vedere [XsltArgumentList per i parametri dei fogli di stile e gli oggetti di estensione](../../../../docs/standard/data/xml/xsltargumentlist-for-style-sheet-parameters-and-extension-objects.md).

Per altre informazioni sui livelli di sicurezza, sul parametro Evidence e su come questi influiscono sulla funzione `document()`, vedere [Risoluzione di fogli di stile e documenti XSLT esterni](../../../../docs/standard/data/xml/resolving-external-xslt-style-sheets-and-documents.md).

Insieme al foglio di stile è possibile fornire vari parametri di input. È inoltre possibile usare il foglio di stile per chiamare le funzioni sugli oggetti di estensione. Sia i parametri che gli oggetti di estensione vengono forniti al foglio di stile mediante la classe <xref:System.Xml.Xsl.XsltArgumentList>. Per altre informazioni sul <xref:System.Xml.Xsl.XsltArgumentList>, vedere <xref:System.Xml.Xsl.XsltArgumentList>.

## <a name="recommended-secure-use-of-xsltransform-class"></a>Uso protetto consigliato per la classe XslTransform

I privilegi di sicurezza del foglio di stile dipendono dal parametro Evidence fornito. Nella tabella seguente vengono riportate la provenienza del foglio di stile e una spiegazione relativa al tipo di evidenza da fornire.

- Il foglio di stile XSLT non ha riferimenti esterni oppure proviene da un codebase attendibile.

  - Fornire l'evidenza dall'assembly:

    ```vb
    Dim xslt = New XslTransform() xslt.Load(stylesheet, resolver, Me.GetType().Assembly.Evidence)

    XsltTransform xslt = new XslTransform();  xslt.Load(stylesheet, resolver, this.GetType().Assembly.Evidence);
    ```

- Il foglio di stile XSLT proviene da un'origine esterna. conosciuta e con un URI verificabile.

  - Fornire l'evidenza usando l'URI.

    ```vb
    Dim xslt As New XslTransform() Dim ev As Evidence = XmlSecureResolver.CreateEvidenceForUrl(stylesheetUri) xslt.Load(stylesheet, resolver, evidence)

    XslTransform xslt = new XslTransform(); Evidence ev = XmlSecureResolver.CreateEvidenceForUrl(stylesheetUri); xslt.Load(stylesheet, resolver, evidence);
    ```

- Il foglio di stile XSLT proviene da un'origine esterna. Tale origine non è nota.

  - Impostare evidence su `null`. I blocchi di script non verranno elaborati, la funzione XSLT `document()` non è supportata e gli oggetti estensioni privilegiati verranno disattivati.

    Inoltre, è possibile impostare anche il parametro `resolver` su `null`, in modo tale che gli elementi `xsl:import` e `xsl:include` non vengano elaborati.

- Il foglio di stile XSLT proviene da un'origine esterna. Tale origine non è nota, ma è necessario il supporto degli script.

  - Richiedere l'evidenza dal chiamante.

## <a name="transformation-of-xml-data"></a>Trasformazione dei dati XML

Una volta caricato il foglio di stile, la trasformazione viene avviata chiamando uno dei metodi <xref:System.Xml.Xsl.XslTransform.Transform%2A> e fornendo un documento di origine di input. Viene eseguito l'overload del metodo <xref:System.Xml.Xsl.XslTransform.Transform%2A> per fornire output di trasformazione diversi. La trasformazione può dare luogo ai seguenti formati di output:

- <xref:System.Xml.XmlReader>

- <xref:System.Xml.XmlWriter>

- <xref:System.IO.TextWriter>

- <xref:System.IO.Stream>

- URL di stringa del file

Quest'ultimo formato, l'URL di stringa, è utile in uno scenario comunemente usato in cui un documento di input situato in un URL viene trasformato e scritto nell'URL di output. Questo metodo <xref:System.Xml.Xsl.XslTransform.Transform%2A> è pratico quando si tratta di caricare un documento XML da un file, eseguire la trasformazione XSLT e scrivere l'output in un file. Questo evita all'utente di dover creare e caricare il documento di origine di input e quindi scrivere in un flusso di file. Nell'esempio di codice seguente viene illustrato l'uso del metodo <xref:System.Xml.Xsl.XslTransform.Transform%2A> con l'URL di stringa come input e output:

```vb
Dim xsltransform As XslTransform = New XslTransform()
xsltransform.Load("favorite.xsl")
xsltransform.Transform("MyDocument.Xml", "TransformResult.xml", Nothing)
```

```csharp
XslTransform xsltransform = new XslTransform();
xsltransform.Load("favorite.xsl");
xsltransform.Transform("MyDocument.xml", "TransformResult.xml", null);
```

## <a name="transforming-a-section-of-an-xml-document"></a>Trasformazione di una sezione di un documento XML

Le trasformazioni si applicano all'intero documento. In altre parole, se viene passato un nodo diverso dal nodo radice del documento, il processo di trasformazione accederà comunque a tutti i nodi nel documento caricato. Per trasformare un frammento di albero risultato, è necessario creare un <xref:System.Xml.XmlDocument> contenente solo il frammento di nodo e passare tale <xref:System.Xml.XmlDocument> al metodo <xref:System.Xml.Xsl.XslTransform.Transform%2A>. Nell'esempio seguente viene eseguita una trasformazione in un frammento di albero risultato.

```vb
Dim xslt As New XslTransform()
xslt.Load("print_root.xsl")
Dim doc As New XmlDocument()
doc.Load("library.xml")
' Create a new document containing just the result tree fragment.
Dim testNode As XmlNode = doc.DocumentElement.FirstChild
Dim tmpDoc As New XmlDocument()
tmpDoc.LoadXml(testNode.OuterXml)
' Pass the document containing the result tree fragment
' to the Transform method.
Console.WriteLine(("Passing " + tmpDoc.OuterXml + " to print_root.xsl"))
xslt.Transform(tmpDoc, Nothing, Console.Out, Nothing)
```

```csharp
XslTransform xslt = new XslTransform();
xslt.Load("print_root.xsl");
XmlDocument doc = new XmlDocument();
doc.Load("library.xml");
// Create a new document containing just the result tree fragment.
XmlNode testNode = doc.DocumentElement.FirstChild;
XmlDocument tmpDoc = new XmlDocument();
tmpDoc.LoadXml(testNode.OuterXml);
// Pass the document containing the result tree fragment
// to the Transform method.
Console.WriteLine("Passing " + tmpDoc.OuterXml + " to print_root.xsl");
xslt.Transform(tmpDoc, null, Console.Out, null);
```

Nell'esempio vengono utilizzati i file Library. XML e print_root. xsl come input e viene restituito quanto segue alla console:

```console
Passing <book genre="novel" ISBN="1-861001-57-5"><title>Pride And Prejudice</title></book> to print_root.xsl
Root node is book.
```

library.xml

```xml
<library>
  <book genre='novel' ISBN='1-861001-57-5'>
     <title>Pride And Prejudice</title>
  </book>
  <book genre='novel' ISBN='1-81920-21-2'>
     <title>Hook</title>
  </book>
</library>
```

print_root.xsl

```xml
<stylesheet version="1.0" xmlns="http://www.w3.org/1999/XSL/Transform" >
  <output method="text" />
  <template match="/">
     Root node is  <value-of select="local-name(//*[position() = 1])" />
  </template>
</stylesheet>
```

## <a name="migration-of-xslt-from-net-framework-version-10-to-net-framework-version-11"></a>Migrazione di XSLT da .NET Framework versione 1.0 a .NET Framework versione 1.1

La tabella seguente illustra i metodi obsoleti di .NET Framework versione 1.0 e quelli nuovi di .NET Framework versione 1.1 per il metodo <xref:System.Xml.Xsl.XslTransform.Load%2A>. I nuovi metodi consentono di limitare le autorizzazioni del foglio di stile specificando il parametro Evidence.

|Metodi Load obsoleti di .NET Framework versione 1.0|Metodi Load sostitutivi di .NET Framework versione 1.1|
|------------------------------------------------------|---------------------------------------------------------|
|Load(input XPathNavigator);<br /><br /> Load(input XPathNavigator, sistema di risoluzione XmlResolver);|Load(foglio di stile XPathNavigator, sistema di risoluzione XmlResolver, evidenza Evidence);|
|Load(foglio di stile IXPathNavigable);<br /><br /> Load(foglio di stile IXPathNavigable, sistema di risoluzione XmlResolver);|Load(foglio di stile IXPathNavigable, sistema di risoluzione XmlResolver, evidenza Evidence);|
|Load(foglio di stile XmlReader);<br /><br /> Load(foglio di stile XmlReader, sistema di risoluzione XmlResolver);|Load(foglio di stile XmlReader, sistema di risoluzione XmlResolver, evidenza Evidence);|

Nella tabella seguente vengono illustrati i metodi obsoleti e quelli nuovi per il metodo <xref:System.Xml.Xsl.XslTransform.Transform%2A>. I nuovi metodi accettano un oggetto <xref:System.Xml.XmlResolver>.

|Metodi Transform di .NET Framework versione 1.0|Metodi Transform sostitutivi di .NET Framework versione 1.1|
|-----------------------------------------------------------|--------------------------------------------------------------|
|XmlReader Transform(input XPathNavigator, argomenti XsltArgumentList)|XmlReader Transform(input XPathNavigator, argomenti XsltArgumentList, sistema di risoluzione XmlResolver)|
|XmlReader Transform(input IXPathNavigable, argomenti XsltArgumentList)|XmlReader Transform(input IXPathNavigable, arg XsltArgumentList, sistema di risoluzione XmlResolver)|
|Void Transform(input XPathNavigator, argomenti XsltArgumentList, output XmlWriter)|Void Transform(input XPathNavigator, argomenti XsltArgumentList, output XmlWriter, sistema di risoluzione XmlResolver)|
|Void Transform(input IXPathNavigable, arg XsltArgumentList, output XmlWriter)|Void Transform(input IXpathNavigable, argomenti XsltArgumentList, output XmlWriter, sistema di risoluzione XmlResolver)|
|Void Transform(input XPathNavigator, argomenti XsltArgumentList, output TextWriter)|Void Transform(input XPathNavigator, argomenti XsltArgumentList, output TextWriter, sistema di risoluzione XmlResolver)|
|Void Transform(input IXPathNavigable, argomenti XsltArgumentList, output TextWriter)|Void Transform(input IXPathNavigable, argomenti XsltArgumentList, output TextWriter, sistema di risoluzione XmlResolver)|
|Void Transform(input XPathNavigator, argomenti XsltArgumentList, output Stream)|Void Transform(input XPathNavigator, arg XsltArgumentList, output Stream, sistema di risoluzione XmlResolver)|
|Void Transform(input IXPathNavigable, arg XsltArgumentList, output Stream)|Void Transform(input IXPathNavigable, argomenti XsltArgumentList, output Stream, sistema di risoluzione XmlResolver)|
|Void Transform(input String, output String)|Void Transform(input String, output String, sistema di risoluzione XmlResolver)|

La proprietà <xref:System.Xml.Xsl.XslTransform.XmlResolver%2A?displayProperty=nameWithType> è obsoleta in .NET Framework versione 1.1. Al suo posto è possibile usare i nuovi overload <xref:System.Xml.Xsl.XslTransform.Transform%2A> con un oggetto <xref:System.Xml.XmlResolver>.

## <a name="see-also"></a>Vedere anche

- <xref:System.Xml.Xsl.XslTransform>
- [Trasformazioni XSLT con la classe XslTransform](../../../../docs/standard/data/xml/xslt-transformations-with-the-xsltransform-class.md)
- [XPathNavigator nelle trasformazioni](../../../../docs/standard/data/xml/xpathnavigator-in-transformations.md)
- [XPathNodeIterator nelle trasformazioni](../../../../docs/standard/data/xml/xpathnodeiterator-in-transformations.md)
- [Input di XPathDocument in XslTransform](../../../../docs/standard/data/xml/xpathdocument-input-to-xsltransform.md)
- [Input di XmlDataDocument in XslTransform](../../../../docs/standard/data/xml/xmldatadocument-input-to-xsltransform.md)
- [Input di XmlDocument in XslTransform](../../../../docs/standard/data/xml/xmldocument-input-to-xsltransform.md)
