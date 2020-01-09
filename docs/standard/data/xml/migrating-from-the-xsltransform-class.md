---
title: Migrazione dalla classe XslTransform
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 9404d758-679f-4ffb-995d-3d07d817659e
ms.openlocfilehash: 95e71e1fdd0ded145025316a5d6597b27a6cc970
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710648"
---
# <a name="migrating-from-the-xsltransform-class"></a>Migrazione dalla classe XslTransform

L'architettura XSLT è stata riprogettata in Visual Studio 2005. La classe <xref:System.Xml.Xsl.XslTransform> è stata sostituita dalla classe <xref:System.Xml.Xsl.XslCompiledTransform>.

Nelle sezioni seguenti vengono descritte alcune delle principali differenze tra <xref:System.Xml.Xsl.XslCompiledTransform> e le classi di <xref:System.Xml.Xsl.XslTransform>.

## <a name="performance"></a>Prestazioni

La classe <xref:System.Xml.Xsl.XslCompiledTransform> presenta numerosi miglioramenti a livello di prestazioni. Il nuovo processore XSLT consente di compilare il foglio di stile XSLT in un formato comune intermedio analogamente a ciò che esegue CLR (Common Language Runtime) per altri linguaggi di programmazione. Una volta compilato, il foglio di stile può essere memorizzato nella cache e usato nuovamente.

Inoltre, la classe <xref:System.Xml.Xsl.XslCompiledTransform> include altre ottimizzazioni che rendono molto più veloce la classe <xref:System.Xml.Xsl.XslTransform>.

> [!NOTE]
> Sebbene le prestazioni complessive della classe <xref:System.Xml.Xsl.XslCompiledTransform> siano migliori rispetto alla classe <xref:System.Xml.Xsl.XslTransform>, l'esecuzione del metodo <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A> della classe <xref:System.Xml.Xsl.XslCompiledTransform> potrebbe risultare più lenta di quella del metodo <xref:System.Xml.Xsl.XslTransform.Load%2A> della classe <xref:System.Xml.Xsl.XslTransform> la prima volta che tale metodo viene chiamato su una trasformazione. Questa situazione si verifica perché il file XSLT deve essere compilato prima del caricamento. Per altre informazioni, vedere il post di blog seguente: [XslCompiledTransform Slower than XslTransform?](https://blogs.msdn.microsoft.com/antosha/2006/07/16/xslcompiledtransform-slower-than-xsltransform/) (XslCompiledTransform è più lento di XslTransform?)

## <a name="security"></a>Sicurezza -

Per impostazione predefinita, la classe <xref:System.Xml.Xsl.XslCompiledTransform> disabilita il supporto per la funzione `document()` di XSLT e per lo script incorporato. Queste funzionalità possono essere abilitate creando un oggetto <xref:System.Xml.Xsl.XsltSettings> in cui le funzionalità sono abilitate e passandolo al metodo <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A>. Nell'esempio seguente viene illustrato come abilitare lo scripting ed eseguire una trasformazione XSLT.

[!code-csharp[XML_Migration#16](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#16)]
[!code-vb[XML_Migration#16](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#16)]

Per altre informazioni, vedere [Considerazioni sulla sicurezza XSLT](../../../../docs/standard/data/xml/xslt-security-considerations.md).

## <a name="new-features"></a>Nuove funzioni e caratteristiche

### <a name="temporary-files"></a>File temporanei

I file temporanei vengono talvolta generati durante l'elaborazione XSLT. Se un foglio di stile contiene blocchi di script o se viene compilato con l'impostazione di debug impostata su true, è possibile creare i file temporanei nella cartella %TEMP%. In alcuni casi è possibile che alcuni file temporanei non vengano eliminati a causa di problemi di temporizzazione. Ad esempio, se i file vengono usati nell'AppDomain corrente o dal debugger, il finalizzatore dell'oggetto <xref:System.CodeDom.Compiler.TempFileCollection> non sarà in grado di rimuoverli.

Per assicurarsi che tutti i file temporanei vengano rimossi dal client, è possibile usare la proprietà <xref:System.Xml.Xsl.XslCompiledTransform.TemporaryFiles%2A> per eseguire una pulizia aggiuntiva.

### <a name="support-for-the-xsloutput-element-and-xmlwriter"></a>Supporto per l'elemento xsl:output e XmlWriter

La classe <xref:System.Xml.Xsl.XslTransform> ignora le impostazioni `xsl:output` quando l'output della trasformazione viene inviato a un oggetto <xref:System.Xml.XmlWriter>. Per la classe <xref:System.Xml.Xsl.XslCompiledTransform> è disponibile una proprietà <xref:System.Xml.Xsl.XslCompiledTransform.OutputSettings%2A> che restituisce un oggetto <xref:System.Xml.XmlWriterSettings> contenente le informazioni di output derivate dall'elemento `xsl:output` del foglio di stile. L'oggetto <xref:System.Xml.XmlWriterSettings> viene usato per creare un oggetto <xref:System.Xml.XmlWriter> con le impostazioni corrette che è possibile passare al metodo <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A>. Nel codice C# seguente viene illustrato questo comportamento:

```csharp
// Create the XslTransform object and load the style sheet.
XslCompiledTransform xslt = new XslCompiledTransform();
xslt.Load(stylesheet);

// Load the file to transform.
XPathDocument doc = new XPathDocument(filename);

// Create the writer.
XmlWriter writer = XmlWriter.Create(Console.Out, xslt.OutputSettings);

// Transform the file and send the output to the console.
xslt.Transform(doc, writer);
writer.Close();
```

### <a name="debug-option"></a>Opzione di debug

La classe <xref:System.Xml.Xsl.XslCompiledTransform> è in grado di generare informazioni di debug che consentono di eseguire il debug del foglio di stile con il debugger di Microsoft Visual Studio. Per altre informazioni, vedere <xref:System.Xml.Xsl.XslCompiledTransform.%23ctor%28System.Boolean%29>.

## <a name="behavioral-differences"></a>Differenze di comportamento

### <a name="transforming-to-an-xmlreader"></a>Trasformazione in XmlReader

La classe <xref:System.Xml.Xsl.XslTransform> contiene diversi overload Transform che restituiscono informazioni sulle trasformazioni sotto forma di oggetto <xref:System.Xml.XmlReader>. È possibile usare questi overload per caricare i risultati delle trasformazioni in una rappresentazione in memoria (ad esempio <xref:System.Xml.XmlDocument> o <xref:System.Xml.XPath.XPathDocument>) senza rischiare di sovraccaricare la serializzazione e la deserializzazione dell'albero XML risultante. Nel codice C# seguente viene illustrato come caricare i risultati delle trasformazioni in un oggetto <xref:System.Xml.XmlDocument>.

```csharp
// Load the style sheet
XslTransform xslt = new XslTransform();
xslt.Load("MyStylesheet.xsl");

// Transform input document to XmlDocument for additional processing
XmlDocument doc = new XmlDocument();
doc.Load(xslt.Transform(input, (XsltArgumentList)null));
```

La classe <xref:System.Xml.Xsl.XslCompiledTransform> non supporta la trasformazione in un oggetto <xref:System.Xml.XmlReader>. È tuttavia possibile eseguire la stessa operazione usando il metodo <xref:System.Xml.XPath.XPathNavigator.CreateNavigator%2A> per caricare l'albero XML risultante direttamente da un oggetto <xref:System.Xml.XmlWriter>. Nel codice C# seguente viene illustrato come eseguire la stessa attività usando <xref:System.Xml.Xsl.XslCompiledTransform>.

```csharp
// Transform input document to XmlDocument for additional processing
XmlDocument doc = new XmlDocument();
using (XmlWriter writer = doc.CreateNavigator().AppendChild()) {
    xslt.Transform(input, (XsltArgumentList)null, writer);
}
```

### <a name="discretionary-behavior"></a>Comportamento discretionary

Nella raccomandazione W3C, XSL Transformations (XSLT) Version 1.0, sono incluse aree in cui il provider dell'implementazione può decidere come gestire una determinata situazione. Queste aree si considerano come aree di comportamento discretionary. Sono numerose le aree in cui <xref:System.Xml.Xsl.XslCompiledTransform> si comporta in modo diverso rispetto alla classe <xref:System.Xml.Xsl.XslTransform>. Per altre informazioni, vedere [Errori XSLT risolvibili](../../../../docs/standard/data/xml/recoverable-xslt-errors.md).

### <a name="extension-objects-and-script-functions"></a>Oggetti di estensione e funzioni di script

Con <xref:System.Xml.Xsl.XslCompiledTransform> vengono introdotte due nuove restrizioni relative all'utilizzo di funzioni script:

- Da espressioni XPath è possibile chiamare solo metodi pubblici.

- Gli overload si distinguono tra loro in base al numero di argomenti. Se più di un overload presenta lo stesso numero di argomenti, verrà generata un'eccezione.

In <xref:System.Xml.Xsl.XslCompiledTransform> si verifica un'associazione (ricerca del nome del metodo) alle funzioni di script in fase di compilazione e i fogli di stile usati con XslTransform possono causare un'eccezione quando vengono caricati con <xref:System.Xml.Xsl.XslCompiledTransform>.

Con <xref:System.Xml.Xsl.XslCompiledTransform> sono supportati gli elementi figlio `msxsl:using` e `msxsl:assembly` all'interno dell'elemento `msxsl:script`. Gli elementi `msxsl:using` e `msxsl:assembly` sono usati per dichiarare spazi dei nomi e assembly aggiuntivi da usare nel blocco di script. Per altre informazioni, vedere [Blocchi di script con msxsl:script](../../../../docs/standard/data/xml/script-blocks-using-msxsl-script.md).

In <xref:System.Xml.Xsl.XslCompiledTransform> sono proibiti gli oggetti di estensione che presentano più overload con lo stesso numero di argomenti.

### <a name="msxml-functions"></a>Funzioni MSXML

Alla classe <xref:System.Xml.Xsl.XslCompiledTransform> è stato aggiunto il supporto per altre funzioni MSXML. Nell'elenco seguente vengono descritte le funzionalità nuove o migliorate.

- msxsl:node-set: con <xref:System.Xml.Xsl.XslTransform> è necessario che l'argomento della funzione [node-set Function](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms256197(v=vs.100)) sia un frammento dell'albero dei risultati. Questo requisito non è invece previsto con la classe <xref:System.Xml.Xsl.XslCompiledTransform>.

- msxsl:version: questa funzione è supportata in <xref:System.Xml.Xsl.XslCompiledTransform>.

- Funzioni dell'estensione XPath: le funzioni [ms:string-compare](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms256114(v=vs.100)), [ms:utc](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms256474(v=vs.100)), [ms:namespace-uri](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms256231(v=vs.100)), [ms:local-name](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms256055(v=vs.100)), [ms:number](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms256155(v=vs.100)), [ms:format-date](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms256099(v=vs.100)) e [ms:format-time](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms256467(v=vs.100)) ora sono supportate.

- Funzioni di estensione XPath correlate allo schema: queste funzioni non sono supportate in modalità nativa da <xref:System.Xml.Xsl.XslCompiledTransform>. Tuttavia, possono essere implementate come funzioni di estensione.

## <a name="see-also"></a>Vedere anche

- [Trasformazioni XSLT](../../../../docs/standard/data/xml/xslt-transformations.md)
- [Uso della classe XslCompiledTransform](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md)
