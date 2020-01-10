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
# <a name="xsltransform-class-implements-the-xslt-processor"></a><span data-ttu-id="60276-102">Implementazione del processore XSLT da parte della classe XslTransform</span><span class="sxs-lookup"><span data-stu-id="60276-102">XslTransform Class Implements the XSLT Processor</span></span>

> [!NOTE]
> <span data-ttu-id="60276-103">La classe <xref:System.Xml.Xsl.XslTransform> è obsoleta in .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="60276-103">The <xref:System.Xml.Xsl.XslTransform> class is obsolete in the .NET Framework 2.0.</span></span> <span data-ttu-id="60276-104">È possibile eseguire le trasformazioni XSLT (Extensible Stylesheet Language for Transformations) usando la classe <xref:System.Xml.Xsl.XslCompiledTransform>.</span><span class="sxs-lookup"><span data-stu-id="60276-104">You can perform Extensible Stylesheet Language for Transformations (XSLT) transformations using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span> <span data-ttu-id="60276-105">Per altre informazioni, vedere [Utilizzo della classe XslCompiledTransform](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) e [Migrazione dalla classe XslTransform](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md).</span><span class="sxs-lookup"><span data-stu-id="60276-105">See [Using the XslCompiledTransform Class](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) and [Migrating From the XslTransform Class](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md) for more information.</span></span>

<span data-ttu-id="60276-106">La classe <xref:System.Xml.Xsl.XslTransform> è un processore XSLT che implementa la raccomandazione XSL Transformations (XSLT) Version 1.0.</span><span class="sxs-lookup"><span data-stu-id="60276-106">The <xref:System.Xml.Xsl.XslTransform> class is an XSLT processor implementing the XSL Transformations (XSLT) Version 1.0 recommendation.</span></span> <span data-ttu-id="60276-107">Il metodo <xref:System.Xml.Xsl.XslTransform.Load%2A> individua e legge i fogli di stile, mentre il metodo <xref:System.Xml.Xsl.XslTransform.Transform%2A> trasforma il documento di origine.</span><span class="sxs-lookup"><span data-stu-id="60276-107">The <xref:System.Xml.Xsl.XslTransform.Load%2A> method locates and reads style sheets, and the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method transforms the given source document.</span></span> <span data-ttu-id="60276-108">Come documento di origine per <xref:System.Xml.XPath.IXPathNavigable> può essere usato qualsiasi archivio che implementi l'interfaccia <xref:System.Xml.Xsl.XslTransform>.</span><span class="sxs-lookup"><span data-stu-id="60276-108">Any store that implements the <xref:System.Xml.XPath.IXPathNavigable> interface can be used as the source document for the <xref:System.Xml.Xsl.XslTransform>.</span></span> <span data-ttu-id="60276-109">Poiché .NET Framework attualmente implementa l'interfaccia <xref:System.Xml.XPath.IXPathNavigable> nelle classi <xref:System.Xml.XmlDocument>, <xref:System.Xml.XmlDataDocument> e <xref:System.Xml.XPath.XPathDocument>, è possibile usare uno qualsiasi di questi elementi come documento di origine di input per una trasformazione.</span><span class="sxs-lookup"><span data-stu-id="60276-109">The .NET Framework currently implements the <xref:System.Xml.XPath.IXPathNavigable> interface on the <xref:System.Xml.XmlDocument>, the <xref:System.Xml.XmlDataDocument>, and the <xref:System.Xml.XPath.XPathDocument>, so all of these can be used as the input source document to a transformation.</span></span>

<span data-ttu-id="60276-110">L'oggetto <xref:System.Xml.Xsl.XslTransform> in .NET Framework supporta solo la specifica XSLT 1.0, definita con lo spazio dei nomi seguente:</span><span class="sxs-lookup"><span data-stu-id="60276-110">The <xref:System.Xml.Xsl.XslTransform> object in the .NET Framework only supports the XSLT 1.0 specification, defined with the following namespace:</span></span>

```xml
<xsl:stylesheet xmlns:xsl="http://www.w3.org/1999/XSL/Transform" version="1.0">
```

<span data-ttu-id="60276-111">Usando il metodo <xref:System.Xml.Xsl.XslTransform.Load%2A>, è possibile caricare il foglio di stile da una delle seguenti classi:</span><span class="sxs-lookup"><span data-stu-id="60276-111">The style sheet can be loaded, using the <xref:System.Xml.Xsl.XslTransform.Load%2A> method, from one of the following classes:</span></span>

- <span data-ttu-id="60276-112">XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="60276-112">XPathNavigator</span></span>

- <span data-ttu-id="60276-113">XmlReader</span><span class="sxs-lookup"><span data-stu-id="60276-113">XmlReader</span></span>

- <span data-ttu-id="60276-114">Una stringa che rappresenta un URL</span><span class="sxs-lookup"><span data-stu-id="60276-114">A string representing a URL</span></span>

<span data-ttu-id="60276-115">Per ognuna delle classi di input sopra riportate, esiste un diverso metodo <xref:System.Xml.Xsl.XslTransform.Load%2A>.</span><span class="sxs-lookup"><span data-stu-id="60276-115">There is a different <xref:System.Xml.Xsl.XslTransform.Load%2A> method for each of the above input classes.</span></span> <span data-ttu-id="60276-116">Alcuni metodi richiedono come argomento una combinazione di una di queste classi con la classe <xref:System.Xml.XmlResolver>.</span><span class="sxs-lookup"><span data-stu-id="60276-116">Some methods take in a combination of one of these classes and the <xref:System.Xml.XmlResolver> class as arguments.</span></span> <span data-ttu-id="60276-117">L'oggetto <xref:System.Xml.XmlResolver> consente di individuare le risorse a cui `<xsl:import>` o `<xsl:include>` fa riferimento nel foglio di stile.</span><span class="sxs-lookup"><span data-stu-id="60276-117">The <xref:System.Xml.XmlResolver> locates resources referenced by `<xsl:import>` or `<xsl:include>` found in the style sheet.</span></span> <span data-ttu-id="60276-118">Per i metodi seguenti, viene usata come input una stringa <xref:System.Xml.XmlReader> o <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="60276-118">The following methods take a string, <xref:System.Xml.XmlReader>, or <xref:System.Xml.XPath.XPathNavigator> as input.</span></span>

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

<span data-ttu-id="60276-119">Molti dei metodi <xref:System.Xml.Xsl.XslTransform.Load%2A> sopra descritti accettano come parametro <xref:System.Xml.XmlResolver>.</span><span class="sxs-lookup"><span data-stu-id="60276-119">Most of the <xref:System.Xml.Xsl.XslTransform.Load%2A> methods shown above take an <xref:System.Xml.XmlResolver> as a parameter.</span></span> <span data-ttu-id="60276-120">L'oggetto <xref:System.Xml.XmlResolver> consente di caricare il foglio di stile e qualsiasi altro eventuale foglio di stile a cui viene fatto riferimento negli elementi xsl:import e xsl:include.</span><span class="sxs-lookup"><span data-stu-id="60276-120">The <xref:System.Xml.XmlResolver> is used to load the style sheet and any style sheet(s) referenced in xsl:import and xsl:include elements.</span></span>

<span data-ttu-id="60276-121">Molti dei metodi <xref:System.Xml.Xsl.XslTransform.Load%2A> accettano come parametro anche Evidence,</span><span class="sxs-lookup"><span data-stu-id="60276-121">Most of the <xref:System.Xml.Xsl.XslTransform.Load%2A> methods also take evidence as a parameter.</span></span> <span data-ttu-id="60276-122">Evidence è il parametro <xref:System.Security.Policy.Evidence> associato al foglio di stile.</span><span class="sxs-lookup"><span data-stu-id="60276-122">The evidence parameter is the <xref:System.Security.Policy.Evidence> that is associated with the style sheet.</span></span> <span data-ttu-id="60276-123">Il livello di sicurezza del foglio di stile influenza il livello di sicurezza delle eventuali risorse a cui esso fa riferimento successivamente, quali lo script contenuto, le funzioni `document()` usate e gli oggetti di estensione usati da <xref:System.Xml.Xsl.XsltArgumentList>.</span><span class="sxs-lookup"><span data-stu-id="60276-123">The security level of the style sheet affects the security level of any subsequent resources it references, such as the script it contains, any `document()` functions it uses, and any extension objects used by the <xref:System.Xml.Xsl.XsltArgumentList>.</span></span>

<span data-ttu-id="60276-124">Se il foglio di stile viene caricato usando il metodo <xref:System.Xml.Xsl.XslTransform.Load%2A> contenente un parametro URL e nessun parametro evidence, l'evidenza del foglio di stile viene calcolata combinando l'URL con il sito e la zona relativi.</span><span class="sxs-lookup"><span data-stu-id="60276-124">If the style sheet is loaded using a <xref:System.Xml.Xsl.XslTransform.Load%2A> method that contains a URL parameter and no evidence is provided, the evidence of the style sheet is calculated by combining the given URL with its site and zone.</span></span>

<span data-ttu-id="60276-125">Se i parametri URI ed Evidence non vengono forniti, il parametro Evidence impostato per il foglio di stile è completamente attendibile.</span><span class="sxs-lookup"><span data-stu-id="60276-125">If no URI or evidence is provided, then the evidence set for the style sheet is fully trusted.</span></span> <span data-ttu-id="60276-126">Non caricare fogli di stile da origini non attendibili né aggiungere a <xref:System.Xml.Xsl.XsltArgumentList> oggetti di estensione non attendibili.</span><span class="sxs-lookup"><span data-stu-id="60276-126">Do not load style sheets from untrusted sources, or add untrusted extension objects into the <xref:System.Xml.Xsl.XsltArgumentList>.</span></span>

<span data-ttu-id="60276-127">Per altre informazioni sui livelli di sicurezza, sul parametro Evidence e su come questi influiscono sugli script, vedere [Scripting dei fogli di stile XSLT con \<msxsl:script>](../../../../docs/standard/data/xml/xslt-stylesheet-scripting-using-msxsl-script.md).</span><span class="sxs-lookup"><span data-stu-id="60276-127">For more information about security levels and evidence and how it affects scripting, see [XSLT Stylesheet Scripting Using \<msxsl:script>](../../../../docs/standard/data/xml/xslt-stylesheet-scripting-using-msxsl-script.md).</span></span> <span data-ttu-id="60276-128">Per altre informazioni sui livelli di sicurezza, sul parametro Evidence e su come questi influiscono sugli oggetti di estensione, vedere [XsltArgumentList per i parametri dei fogli di stile e gli oggetti di estensione](../../../../docs/standard/data/xml/xsltargumentlist-for-style-sheet-parameters-and-extension-objects.md).</span><span class="sxs-lookup"><span data-stu-id="60276-128">For information about security levels and evidence and how it affects extension objects, see [XsltArgumentList for Style Sheet Parameters and Extension Objects](../../../../docs/standard/data/xml/xsltargumentlist-for-style-sheet-parameters-and-extension-objects.md).</span></span>

<span data-ttu-id="60276-129">Per altre informazioni sui livelli di sicurezza, sul parametro Evidence e su come questi influiscono sulla funzione `document()`, vedere [Risoluzione di fogli di stile e documenti XSLT esterni](../../../../docs/standard/data/xml/resolving-external-xslt-style-sheets-and-documents.md).</span><span class="sxs-lookup"><span data-stu-id="60276-129">For information about security levels and evidence and how it affects the `document()` function, see [Resolving External XSLT Style Sheets and Documents](../../../../docs/standard/data/xml/resolving-external-xslt-style-sheets-and-documents.md).</span></span>

<span data-ttu-id="60276-130">Insieme al foglio di stile è possibile fornire vari parametri di input.</span><span class="sxs-lookup"><span data-stu-id="60276-130">A style sheet can be supplied with a number of input parameters.</span></span> <span data-ttu-id="60276-131">È inoltre possibile usare il foglio di stile per chiamare le funzioni sugli oggetti di estensione.</span><span class="sxs-lookup"><span data-stu-id="60276-131">The style sheet can also call functions on extension objects.</span></span> <span data-ttu-id="60276-132">Sia i parametri che gli oggetti di estensione vengono forniti al foglio di stile mediante la classe <xref:System.Xml.Xsl.XsltArgumentList>.</span><span class="sxs-lookup"><span data-stu-id="60276-132">Both parameters and extension objects are supplied to the style sheet using the <xref:System.Xml.Xsl.XsltArgumentList> class.</span></span> <span data-ttu-id="60276-133">Per altre informazioni sul <xref:System.Xml.Xsl.XsltArgumentList>, vedere <xref:System.Xml.Xsl.XsltArgumentList>.</span><span class="sxs-lookup"><span data-stu-id="60276-133">For more information about the <xref:System.Xml.Xsl.XsltArgumentList>, see <xref:System.Xml.Xsl.XsltArgumentList>.</span></span>

## <a name="recommended-secure-use-of-xsltransform-class"></a><span data-ttu-id="60276-134">Uso protetto consigliato per la classe XslTransform</span><span class="sxs-lookup"><span data-stu-id="60276-134">Recommended Secure Use of XslTransform Class</span></span>

<span data-ttu-id="60276-135">I privilegi di sicurezza del foglio di stile dipendono dal parametro Evidence fornito.</span><span class="sxs-lookup"><span data-stu-id="60276-135">The security privileges of the style sheet depend on the evidence provided.</span></span> <span data-ttu-id="60276-136">Nella tabella seguente vengono riportate la provenienza del foglio di stile e una spiegazione relativa al tipo di evidenza da fornire.</span><span class="sxs-lookup"><span data-stu-id="60276-136">The following table summarizes the location of the style sheet and gives an explanation of what type of evidence to give.</span></span>

- <span data-ttu-id="60276-137">Il foglio di stile XSLT non ha riferimenti esterni oppure proviene da un codebase attendibile.</span><span class="sxs-lookup"><span data-stu-id="60276-137">The XSLT style sheet has no external references, or the style sheet comes from a code base that you trust.</span></span>

  - <span data-ttu-id="60276-138">Fornire l'evidenza dall'assembly:</span><span class="sxs-lookup"><span data-stu-id="60276-138">Provide the evidence from your assembly:</span></span>

    ```vb
    Dim xslt = New XslTransform() xslt.Load(stylesheet, resolver, Me.GetType().Assembly.Evidence)

    XsltTransform xslt = new XslTransform();  xslt.Load(stylesheet, resolver, this.GetType().Assembly.Evidence);
    ```

- <span data-ttu-id="60276-139">Il foglio di stile XSLT proviene da un'origine esterna.</span><span class="sxs-lookup"><span data-stu-id="60276-139">The XSLT style sheet comes from an outside source.</span></span> <span data-ttu-id="60276-140">conosciuta e con un URI verificabile.</span><span class="sxs-lookup"><span data-stu-id="60276-140">The origin of the source is known and there is a verifiable URI.</span></span>

  - <span data-ttu-id="60276-141">Fornire l'evidenza usando l'URI.</span><span class="sxs-lookup"><span data-stu-id="60276-141">Create evidence using the URI.</span></span>

    ```vb
    Dim xslt As New XslTransform() Dim ev As Evidence = XmlSecureResolver.CreateEvidenceForUrl(stylesheetUri) xslt.Load(stylesheet, resolver, evidence)

    XslTransform xslt = new XslTransform(); Evidence ev = XmlSecureResolver.CreateEvidenceForUrl(stylesheetUri); xslt.Load(stylesheet, resolver, evidence);
    ```

- <span data-ttu-id="60276-142">Il foglio di stile XSLT proviene da un'origine esterna.</span><span class="sxs-lookup"><span data-stu-id="60276-142">The XSLT style sheet comes from an outside source.</span></span> <span data-ttu-id="60276-143">Tale origine non è nota.</span><span class="sxs-lookup"><span data-stu-id="60276-143">The origin of the source is not known.</span></span>

  - <span data-ttu-id="60276-144">Impostare evidence su `null`.</span><span class="sxs-lookup"><span data-stu-id="60276-144">Set evidence to `null`.</span></span> <span data-ttu-id="60276-145">I blocchi di script non verranno elaborati, la funzione XSLT `document()` non è supportata e gli oggetti estensioni privilegiati verranno disattivati.</span><span class="sxs-lookup"><span data-stu-id="60276-145">Script blocks are not processed, the XSLT `document()` function is not supported, and privileged extension objects are disallowed.</span></span>

    <span data-ttu-id="60276-146">Inoltre, è possibile impostare anche il parametro `resolver` su `null`, in modo tale che gli elementi `xsl:import` e `xsl:include` non vengano elaborati.</span><span class="sxs-lookup"><span data-stu-id="60276-146">Additionally, you can also set the `resolver` parameter to `null` This ensures that `xsl:import` and `xsl:include` elements are not processed.</span></span>

- <span data-ttu-id="60276-147">Il foglio di stile XSLT proviene da un'origine esterna.</span><span class="sxs-lookup"><span data-stu-id="60276-147">The XSLT style sheet comes from an outside source.</span></span> <span data-ttu-id="60276-148">Tale origine non è nota, ma è necessario il supporto degli script.</span><span class="sxs-lookup"><span data-stu-id="60276-148">The origin of the source is not known, but you require script support.</span></span>

  - <span data-ttu-id="60276-149">Richiedere l'evidenza dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="60276-149">Request evidence from the caller.</span></span>

## <a name="transformation-of-xml-data"></a><span data-ttu-id="60276-150">Trasformazione dei dati XML</span><span class="sxs-lookup"><span data-stu-id="60276-150">Transformation of XML Data</span></span>

<span data-ttu-id="60276-151">Una volta caricato il foglio di stile, la trasformazione viene avviata chiamando uno dei metodi <xref:System.Xml.Xsl.XslTransform.Transform%2A> e fornendo un documento di origine di input.</span><span class="sxs-lookup"><span data-stu-id="60276-151">Once a style sheet is loaded, the transformation starts by calling one of the <xref:System.Xml.Xsl.XslTransform.Transform%2A> methods and supplying an input source document.</span></span> <span data-ttu-id="60276-152">Viene eseguito l'overload del metodo <xref:System.Xml.Xsl.XslTransform.Transform%2A> per fornire output di trasformazione diversi.</span><span class="sxs-lookup"><span data-stu-id="60276-152">The <xref:System.Xml.Xsl.XslTransform.Transform%2A> method is overloaded to provide different transformation outputs.</span></span> <span data-ttu-id="60276-153">La trasformazione può dare luogo ai seguenti formati di output:</span><span class="sxs-lookup"><span data-stu-id="60276-153">The transformation can result in the following output formats:</span></span>

- <xref:System.Xml.XmlReader>

- <xref:System.Xml.XmlWriter>

- <xref:System.IO.TextWriter>

- <xref:System.IO.Stream>

- <span data-ttu-id="60276-154">URL di stringa del file</span><span class="sxs-lookup"><span data-stu-id="60276-154">String URL of file</span></span>

<span data-ttu-id="60276-155">Quest'ultimo formato, l'URL di stringa, è utile in uno scenario comunemente usato in cui un documento di input situato in un URL viene trasformato e scritto nell'URL di output.</span><span class="sxs-lookup"><span data-stu-id="60276-155">This last format, the string URL, provides for a commonly used scenario in transforming an input document located in a URL and writing the document to the output URL.</span></span> <span data-ttu-id="60276-156">Questo metodo <xref:System.Xml.Xsl.XslTransform.Transform%2A> è pratico quando si tratta di caricare un documento XML da un file, eseguire la trasformazione XSLT e scrivere l'output in un file.</span><span class="sxs-lookup"><span data-stu-id="60276-156">This <xref:System.Xml.Xsl.XslTransform.Transform%2A> method is a convenience method to load an XML document from a file, perform the XSLT transformation, and write the output to a file.</span></span> <span data-ttu-id="60276-157">Questo evita all'utente di dover creare e caricare il documento di origine di input e quindi scrivere in un flusso di file.</span><span class="sxs-lookup"><span data-stu-id="60276-157">This prevents you from having to create and load the input source document, and then write to a file stream.</span></span> <span data-ttu-id="60276-158">Nell'esempio di codice seguente viene illustrato l'uso del metodo <xref:System.Xml.Xsl.XslTransform.Transform%2A> con l'URL di stringa come input e output:</span><span class="sxs-lookup"><span data-stu-id="60276-158">The following code sample shows this use of the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method using the string URL as input and output:</span></span>

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

## <a name="transforming-a-section-of-an-xml-document"></a><span data-ttu-id="60276-159">Trasformazione di una sezione di un documento XML</span><span class="sxs-lookup"><span data-stu-id="60276-159">Transforming a Section of an XML Document</span></span>

<span data-ttu-id="60276-160">Le trasformazioni si applicano all'intero documento.</span><span class="sxs-lookup"><span data-stu-id="60276-160">Transformations apply to the document as a whole.</span></span> <span data-ttu-id="60276-161">In altre parole, se viene passato un nodo diverso dal nodo radice del documento, il processo di trasformazione accederà comunque a tutti i nodi nel documento caricato.</span><span class="sxs-lookup"><span data-stu-id="60276-161">In other words, if you pass in a node other than the document root node, this does not prevent the transformation process from accessing all nodes in the loaded document.</span></span> <span data-ttu-id="60276-162">Per trasformare un frammento di albero risultato, è necessario creare un <xref:System.Xml.XmlDocument> contenente solo il frammento di nodo e passare tale <xref:System.Xml.XmlDocument> al metodo <xref:System.Xml.Xsl.XslTransform.Transform%2A>.</span><span class="sxs-lookup"><span data-stu-id="60276-162">To transform a result tree fragment, you must create an <xref:System.Xml.XmlDocument> containing just the result tree fragment and pass that <xref:System.Xml.XmlDocument> to the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method.</span></span> <span data-ttu-id="60276-163">Nell'esempio seguente viene eseguita una trasformazione in un frammento di albero risultato.</span><span class="sxs-lookup"><span data-stu-id="60276-163">The following example performs a transformation on a result tree fragment.</span></span>

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

<span data-ttu-id="60276-164">Nell'esempio vengono utilizzati i file Library. XML e print_root. xsl come input e viene restituito quanto segue alla console:</span><span class="sxs-lookup"><span data-stu-id="60276-164">The example uses the library.xml and print_root.xsl files as input and outputs the following to the console:</span></span>

```console
Passing <book genre="novel" ISBN="1-861001-57-5"><title>Pride And Prejudice</title></book> to print_root.xsl
Root node is book.
```

<span data-ttu-id="60276-165">library.xml</span><span class="sxs-lookup"><span data-stu-id="60276-165">library.xml</span></span>

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

<span data-ttu-id="60276-166">print_root.xsl</span><span class="sxs-lookup"><span data-stu-id="60276-166">print_root.xsl</span></span>

```xml
<stylesheet version="1.0" xmlns="http://www.w3.org/1999/XSL/Transform" >
  <output method="text" />
  <template match="/">
     Root node is  <value-of select="local-name(//*[position() = 1])" />
  </template>
</stylesheet>
```

## <a name="migration-of-xslt-from-net-framework-version-10-to-net-framework-version-11"></a><span data-ttu-id="60276-167">Migrazione di XSLT da .NET Framework versione 1.0 a .NET Framework versione 1.1</span><span class="sxs-lookup"><span data-stu-id="60276-167">Migration of XSLT from .NET Framework version 1.0 to .NET Framework version 1.1</span></span>

<span data-ttu-id="60276-168">La tabella seguente illustra i metodi obsoleti di .NET Framework versione 1.0 e quelli nuovi di .NET Framework versione 1.1 per il metodo <xref:System.Xml.Xsl.XslTransform.Load%2A>.</span><span class="sxs-lookup"><span data-stu-id="60276-168">The following table shows the obsolete .NET Framework version 1.0 methods and new .NET Framework version 1.1 methods for the <xref:System.Xml.Xsl.XslTransform.Load%2A> method.</span></span> <span data-ttu-id="60276-169">I nuovi metodi consentono di limitare le autorizzazioni del foglio di stile specificando il parametro Evidence.</span><span class="sxs-lookup"><span data-stu-id="60276-169">The new methods enable you to limit the permissions of the style sheet by specifying evidence.</span></span>

|<span data-ttu-id="60276-170">Metodi Load obsoleti di .NET Framework versione 1.0</span><span class="sxs-lookup"><span data-stu-id="60276-170">Obsolete .NET Framework version 1.0 Load Methods</span></span>|<span data-ttu-id="60276-171">Metodi Load sostitutivi di .NET Framework versione 1.1</span><span class="sxs-lookup"><span data-stu-id="60276-171">Replacement .NET Framework version 1.1 Load Methods</span></span>|
|------------------------------------------------------|---------------------------------------------------------|
|<span data-ttu-id="60276-172">Load(input XPathNavigator);</span><span class="sxs-lookup"><span data-stu-id="60276-172">Load(XPathNavigator input);</span></span><br /><br /> <span data-ttu-id="60276-173">Load(input XPathNavigator, sistema di risoluzione XmlResolver);</span><span class="sxs-lookup"><span data-stu-id="60276-173">Load(XPathNavigator input, XmlResolver resolver);</span></span>|<span data-ttu-id="60276-174">Load(foglio di stile XPathNavigator, sistema di risoluzione XmlResolver, evidenza Evidence);</span><span class="sxs-lookup"><span data-stu-id="60276-174">Load(XPathNavigator stylesheet, XmlResolver resolver, Evidence evidence);</span></span>|
|<span data-ttu-id="60276-175">Load(foglio di stile IXPathNavigable);</span><span class="sxs-lookup"><span data-stu-id="60276-175">Load(IXPathNavigable stylesheet);</span></span><br /><br /> <span data-ttu-id="60276-176">Load(foglio di stile IXPathNavigable, sistema di risoluzione XmlResolver);</span><span class="sxs-lookup"><span data-stu-id="60276-176">Load(IXPathNavigable stylesheet, XmlResolver resolver);</span></span>|<span data-ttu-id="60276-177">Load(foglio di stile IXPathNavigable, sistema di risoluzione XmlResolver, evidenza Evidence);</span><span class="sxs-lookup"><span data-stu-id="60276-177">Load(IXPathNavigable stylesheet, XmlResolver resolver, Evidence evidence);</span></span>|
|<span data-ttu-id="60276-178">Load(foglio di stile XmlReader);</span><span class="sxs-lookup"><span data-stu-id="60276-178">Load(XmlReader stylesheet);</span></span><br /><br /> <span data-ttu-id="60276-179">Load(foglio di stile XmlReader, sistema di risoluzione XmlResolver);</span><span class="sxs-lookup"><span data-stu-id="60276-179">Load(XmlReader stylesheet, XmlResolver resolver);</span></span>|<span data-ttu-id="60276-180">Load(foglio di stile XmlReader, sistema di risoluzione XmlResolver, evidenza Evidence);</span><span class="sxs-lookup"><span data-stu-id="60276-180">Load(XmlReader stylesheet, XmlResolver resolver, Evidence evidence);</span></span>|

<span data-ttu-id="60276-181">Nella tabella seguente vengono illustrati i metodi obsoleti e quelli nuovi per il metodo <xref:System.Xml.Xsl.XslTransform.Transform%2A>.</span><span class="sxs-lookup"><span data-stu-id="60276-181">The following table shows the obsolete and new methods for the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method.</span></span> <span data-ttu-id="60276-182">I nuovi metodi accettano un oggetto <xref:System.Xml.XmlResolver>.</span><span class="sxs-lookup"><span data-stu-id="60276-182">The new methods take an <xref:System.Xml.XmlResolver> object.</span></span>

|<span data-ttu-id="60276-183">Metodi Transform di .NET Framework versione 1.0</span><span class="sxs-lookup"><span data-stu-id="60276-183">Obsolete .NET Framework version 1.0 Transform Methods</span></span>|<span data-ttu-id="60276-184">Metodi Transform sostitutivi di .NET Framework versione 1.1</span><span class="sxs-lookup"><span data-stu-id="60276-184">Replacement .NET Framework version Transform 1.1 Methods</span></span>|
|-----------------------------------------------------------|--------------------------------------------------------------|
|<span data-ttu-id="60276-185">XmlReader Transform(input XPathNavigator, argomenti XsltArgumentList)</span><span class="sxs-lookup"><span data-stu-id="60276-185">XmlReader Transform(XPathNavigator input, XsltArgumentList args)</span></span>|<span data-ttu-id="60276-186">XmlReader Transform(input XPathNavigator, argomenti XsltArgumentList, sistema di risoluzione XmlResolver)</span><span class="sxs-lookup"><span data-stu-id="60276-186">XmlReader Transform(XPathNavigator  input, XsltArgumentList args, XmlResolver resolver)</span></span>|
|<span data-ttu-id="60276-187">XmlReader Transform(input IXPathNavigable, argomenti XsltArgumentList)</span><span class="sxs-lookup"><span data-stu-id="60276-187">XmlReader Transform(IXPathNavigable input, XsltArgumentList args)</span></span>|<span data-ttu-id="60276-188">XmlReader Transform(input IXPathNavigable, arg XsltArgumentList, sistema di risoluzione XmlResolver)</span><span class="sxs-lookup"><span data-stu-id="60276-188">XmlReader Transform(IXPathNavigable input, XsltArgumentList args, XmlResolver resolver)</span></span>|
|<span data-ttu-id="60276-189">Void Transform(input XPathNavigator, argomenti XsltArgumentList, output XmlWriter)</span><span class="sxs-lookup"><span data-stu-id="60276-189">Void Transform(XPathNavigator input, XsltArgumentList args, XmlWriter output)</span></span>|<span data-ttu-id="60276-190">Void Transform(input XPathNavigator, argomenti XsltArgumentList, output XmlWriter, sistema di risoluzione XmlResolver)</span><span class="sxs-lookup"><span data-stu-id="60276-190">Void Transform(XPathNavigator input, XsltArgumentList args, XmlWriter output, XmlResolver resolver)</span></span>|
|<span data-ttu-id="60276-191">Void Transform(input IXPathNavigable, arg XsltArgumentList, output XmlWriter)</span><span class="sxs-lookup"><span data-stu-id="60276-191">Void Transform(IXPathNavigable input, XsltArgumentList args, XmlWriter output)</span></span>|<span data-ttu-id="60276-192">Void Transform(input IXpathNavigable, argomenti XsltArgumentList, output XmlWriter, sistema di risoluzione XmlResolver)</span><span class="sxs-lookup"><span data-stu-id="60276-192">Void Transform(IXpathNavigable input, XsltArgumentList args, XmlWriter output, XmlResolver resolver)</span></span>|
|<span data-ttu-id="60276-193">Void Transform(input XPathNavigator, argomenti XsltArgumentList, output TextWriter)</span><span class="sxs-lookup"><span data-stu-id="60276-193">Void Transform(XPathNavigator input, XsltArgumentList args, TextWriter output)</span></span>|<span data-ttu-id="60276-194">Void Transform(input XPathNavigator, argomenti XsltArgumentList, output TextWriter, sistema di risoluzione XmlResolver)</span><span class="sxs-lookup"><span data-stu-id="60276-194">Void Transform(XPathNavigator input, XsltArgumentList args, TextWriter output, XmlResolver resolver)</span></span>|
|<span data-ttu-id="60276-195">Void Transform(input IXPathNavigable, argomenti XsltArgumentList, output TextWriter)</span><span class="sxs-lookup"><span data-stu-id="60276-195">Void Transform(IXPathNavigable input, XsltArgumentList args, TextWriter output)</span></span>|<span data-ttu-id="60276-196">Void Transform(input IXPathNavigable, argomenti XsltArgumentList, output TextWriter, sistema di risoluzione XmlResolver)</span><span class="sxs-lookup"><span data-stu-id="60276-196">Void Transform(IXPathNavigable input, XsltArgumentList args, TextWriter output, XmlResolver resolver)</span></span>|
|<span data-ttu-id="60276-197">Void Transform(input XPathNavigator, argomenti XsltArgumentList, output Stream)</span><span class="sxs-lookup"><span data-stu-id="60276-197">Void Transform(XPathNavigator input, XsltArgumentList args, Stream output)</span></span>|<span data-ttu-id="60276-198">Void Transform(input XPathNavigator, arg XsltArgumentList, output Stream, sistema di risoluzione XmlResolver)</span><span class="sxs-lookup"><span data-stu-id="60276-198">Void Transform(XPathNavigator input, XsltArgumentList args, Stream output, XmlResolver resolver)</span></span>|
|<span data-ttu-id="60276-199">Void Transform(input IXPathNavigable, arg XsltArgumentList, output Stream)</span><span class="sxs-lookup"><span data-stu-id="60276-199">Void Transform(IXPathNavigable input, XsltArgumentList args, Stream output)</span></span>|<span data-ttu-id="60276-200">Void Transform(input IXPathNavigable, argomenti XsltArgumentList, output Stream, sistema di risoluzione XmlResolver)</span><span class="sxs-lookup"><span data-stu-id="60276-200">Void Transform(IXPathNavigable input, XsltArgumentList args, Stream output, XmlResolver resolver)</span></span>|
|<span data-ttu-id="60276-201">Void Transform(input String, output String)</span><span class="sxs-lookup"><span data-stu-id="60276-201">Void Transform(String input, String output);</span></span>|<span data-ttu-id="60276-202">Void Transform(input String, output String, sistema di risoluzione XmlResolver)</span><span class="sxs-lookup"><span data-stu-id="60276-202">Void Transform(String input, String output, XmlResolver resolver);</span></span>|

<span data-ttu-id="60276-203">La proprietà <xref:System.Xml.Xsl.XslTransform.XmlResolver%2A?displayProperty=nameWithType> è obsoleta in .NET Framework versione 1.1.</span><span class="sxs-lookup"><span data-stu-id="60276-203">The <xref:System.Xml.Xsl.XslTransform.XmlResolver%2A?displayProperty=nameWithType> property is obsolete in .NET Framework version 1.1.</span></span> <span data-ttu-id="60276-204">Al suo posto è possibile usare i nuovi overload <xref:System.Xml.Xsl.XslTransform.Transform%2A> con un oggetto <xref:System.Xml.XmlResolver>.</span><span class="sxs-lookup"><span data-stu-id="60276-204">Instead, use the new <xref:System.Xml.Xsl.XslTransform.Transform%2A> overloads which take an <xref:System.Xml.XmlResolver> object.</span></span>

## <a name="see-also"></a><span data-ttu-id="60276-205">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="60276-205">See also</span></span>

- <xref:System.Xml.Xsl.XslTransform>
- [<span data-ttu-id="60276-206">Trasformazioni XSLT con la classe XslTransform</span><span class="sxs-lookup"><span data-stu-id="60276-206">XSLT Transformations with the XslTransform Class</span></span>](../../../../docs/standard/data/xml/xslt-transformations-with-the-xsltransform-class.md)
- [<span data-ttu-id="60276-207">XPathNavigator nelle trasformazioni</span><span class="sxs-lookup"><span data-stu-id="60276-207">XPathNavigator in Transformations</span></span>](../../../../docs/standard/data/xml/xpathnavigator-in-transformations.md)
- [<span data-ttu-id="60276-208">XPathNodeIterator nelle trasformazioni</span><span class="sxs-lookup"><span data-stu-id="60276-208">XPathNodeIterator in Transformations</span></span>](../../../../docs/standard/data/xml/xpathnodeiterator-in-transformations.md)
- [<span data-ttu-id="60276-209">Input di XPathDocument in XslTransform</span><span class="sxs-lookup"><span data-stu-id="60276-209">XPathDocument Input to XslTransform</span></span>](../../../../docs/standard/data/xml/xpathdocument-input-to-xsltransform.md)
- [<span data-ttu-id="60276-210">Input di XmlDataDocument in XslTransform</span><span class="sxs-lookup"><span data-stu-id="60276-210">XmlDataDocument Input to XslTransform</span></span>](../../../../docs/standard/data/xml/xmldatadocument-input-to-xsltransform.md)
- [<span data-ttu-id="60276-211">Input di XmlDocument in XslTransform</span><span class="sxs-lookup"><span data-stu-id="60276-211">XmlDocument Input to XslTransform</span></span>](../../../../docs/standard/data/xml/xmldocument-input-to-xsltransform.md)
