---
title: Trasformazioni XSLT con la classe XslTransform
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 500335af-f9b5-413b-968a-e6d9a824478c
ms.openlocfilehash: 5f670fa5e83d1802496c0cc6972a7e3af7cae374
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709647"
---
# <a name="xslt-transformations-with-the-xsltransform-class"></a><span data-ttu-id="6c344-102">Trasformazioni XSLT con la classe XslTransform</span><span class="sxs-lookup"><span data-stu-id="6c344-102">XSLT Transformations with the XslTransform Class</span></span>

> [!NOTE]
> <span data-ttu-id="6c344-103">La classe <xref:System.Xml.Xsl.XslTransform> è obsoleta in .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="6c344-103">The <xref:System.Xml.Xsl.XslTransform> class is obsolete in the .NET Framework 2.0.</span></span> <span data-ttu-id="6c344-104">È possibile eseguire le trasformazioni XSLT (Extensible Stylesheet Language for Transformations) usando la classe <xref:System.Xml.Xsl.XslCompiledTransform>.</span><span class="sxs-lookup"><span data-stu-id="6c344-104">You can perform Extensible Stylesheet Language for Transformations (XSLT) transformations using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span> <span data-ttu-id="6c344-105">Per altre informazioni, vedere [Utilizzo della classe XslCompiledTransform](using-the-xslcompiledtransform-class.md) e [Migrazione dalla classe XslTransform](migrating-from-the-xsltransform-class.md).</span><span class="sxs-lookup"><span data-stu-id="6c344-105">See [Using the XslCompiledTransform Class](using-the-xslcompiledtransform-class.md) and [Migrating From the XslTransform Class](migrating-from-the-xsltransform-class.md) for more information.</span></span>

<span data-ttu-id="6c344-106">Lo scopo dell'XSLT (Extensible Stylesheet Language Transformation) è quello di trasformare il contenuto di un documento XML di origine in un altro documento di formato o struttura diversa, ad esempio, per trasformare il codice XML in HTML per l'uso su un sito Web o per trasformarlo in un documento che contenga solo i campi richiesti da un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="6c344-106">The goal of the XSLT is to transform the content of a source XML document into another document that is different in format or structure (for example, to transform XML into HTML for use on a Web site or to transform it into a document that contains only the fields required by an application).</span></span> <span data-ttu-id="6c344-107">Questo processo di trasformazione è specificato dalla raccomandazione [XSLT versione 1.0](https://www.w3.org/TR/1999/REC-xslt-19991116) di World Wide Web Consortium (W3C).</span><span class="sxs-lookup"><span data-stu-id="6c344-107">This transformation process is specified by the World Wide Web Consortium (W3C)[XSLT version 1.0 recommendation](https://www.w3.org/TR/1999/REC-xslt-19991116).</span></span> <span data-ttu-id="6c344-108">In .NET Framework la classe <xref:System.Xml.Xsl.XslTransform>, disponibile nello spazio dei nomi <xref:System.Xml.Xsl>, è il processore XSLT che implementa la funzionalità di questa specifica.</span><span class="sxs-lookup"><span data-stu-id="6c344-108">In the .NET Framework, the <xref:System.Xml.Xsl.XslTransform> class, found in the <xref:System.Xml.Xsl> namespace, is the XSLT processor that implements the functionality of this specification.</span></span> <span data-ttu-id="6c344-109">Alcune funzionalità non sono state implementate dalla raccomandazione W3C XSL Transformations (XSLT) versione 1.0 e sono elencate in [Output da un XslTransform](outputs-from-an-xsltransform.md).</span><span class="sxs-lookup"><span data-stu-id="6c344-109">There are a small number of features that have not been implemented from the W3C XSLT 1.0 recommendation, listed in [Outputs from an XslTransform](outputs-from-an-xsltransform.md).</span></span> <span data-ttu-id="6c344-110">La figura seguente illustra l'architettura di trasformazione di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6c344-110">The following figure shows the transformation architecture of the .NET Framework.</span></span>

## <a name="overview"></a><span data-ttu-id="6c344-111">Panoramica di</span><span class="sxs-lookup"><span data-stu-id="6c344-111">Overview</span></span>

![Diagramma che illustra l'architettura di trasformazione XSLT.](./media/xslt-transformations-with-the-xsltransform-class/xslt-transformation-architecture.gif) 

<span data-ttu-id="6c344-113">Per la selezione di parti di un documento XML, nella raccomandazione XSLT viene usato XPath (XML Path Language), ovvero un linguaggio di query usato per navigare nei nodi dell'albero di un documento.</span><span class="sxs-lookup"><span data-stu-id="6c344-113">The XSLT recommendation uses XML Path Language (XPath) to select parts of an XML document, where XPath is a query language used to navigate nodes of a document tree.</span></span> <span data-ttu-id="6c344-114">Come illustrato nel diagramma, l'implementazione di XPath in .NET Framework viene usata per la selezione di parti di XML archiviate in diverse classi, ad esempio una classe <xref:System.Xml.XmlDocument>, una classe <xref:System.Xml.XmlDataDocument> e una classe <xref:System.Xml.XPath.XPathDocument>.</span><span class="sxs-lookup"><span data-stu-id="6c344-114">As shown in the diagram, the .NET Framework implementation of XPath is used to select parts of XML stored in several classes, such as an <xref:System.Xml.XmlDocument>, an <xref:System.Xml.XmlDataDocument>, and an <xref:System.Xml.XPath.XPathDocument>.</span></span> <span data-ttu-id="6c344-115"><xref:System.Xml.XPath.XPathDocument> è un archivio dati XSLT ottimizzato che, se usato con <xref:System.Xml.Xsl.XslTransform>, fornisce trasformazioni XSLT con elevate prestazioni.</span><span class="sxs-lookup"><span data-stu-id="6c344-115">An <xref:System.Xml.XPath.XPathDocument> is an optimized XSLT data store, and when used with <xref:System.Xml.Xsl.XslTransform>, it provides XSLT transformations with good performance.</span></span>

<span data-ttu-id="6c344-116">Nella tabella seguente sono elencate le classi più usate con <xref:System.Xml.Xsl.XslTransform>, XPath e le relative funzioni.</span><span class="sxs-lookup"><span data-stu-id="6c344-116">The following table list commonly uses classes when working with <xref:System.Xml.Xsl.XslTransform> and XPath and their function.</span></span>

|<span data-ttu-id="6c344-117">Classe o interfaccia</span><span class="sxs-lookup"><span data-stu-id="6c344-117">Class or Interface</span></span>|<span data-ttu-id="6c344-118">Funzione</span><span class="sxs-lookup"><span data-stu-id="6c344-118">Function</span></span>|
|------------------------|--------------|
|<xref:System.Xml.XPath.XPathNavigator>|<span data-ttu-id="6c344-119">Si tratta di un'API che fornisce un modello di tipo cursore per la navigazione in un archivio nonché il supporto delle query XPath.</span><span class="sxs-lookup"><span data-stu-id="6c344-119">It is an API that provides a cursor style model for navigating over a store, along with XPath query support.</span></span> <span data-ttu-id="6c344-120">Non viene fornita la funzionalità di modifica dell'archivio sottostante.</span><span class="sxs-lookup"><span data-stu-id="6c344-120">It does not provide editing of the underlying store.</span></span> <span data-ttu-id="6c344-121">Per la modifica, usare la classe <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="6c344-121">For editing, use the <xref:System.Xml.XmlDocument> class.</span></span>|
|<xref:System.Xml.XPath.IXPathNavigable>|<span data-ttu-id="6c344-122">Si tratta di un'interfaccia che fornisce un metodo `CreateNavigator` a un <xref:System.Xml.XPath.XPathNavigator> per l'archivio.</span><span class="sxs-lookup"><span data-stu-id="6c344-122">It is an interface that provides a `CreateNavigator` method to an <xref:System.Xml.XPath.XPathNavigator> for the store.</span></span>|
|<xref:System.Xml.XmlDocument>|<span data-ttu-id="6c344-123">Consente la modifica di questo documento.</span><span class="sxs-lookup"><span data-stu-id="6c344-123">It enables editing of this document.</span></span> <span data-ttu-id="6c344-124">Implementa <xref:System.Xml.XPath.IXPathNavigable>, consentendo scenari per la modifica di documenti in cui vengono successivamente richieste trasformazioni XSLT.</span><span class="sxs-lookup"><span data-stu-id="6c344-124">It implements <xref:System.Xml.XPath.IXPathNavigable>, allowing document-editing scenarios where XSLT transformations are subsequently required.</span></span> <span data-ttu-id="6c344-125">Per altre informazioni, vedere [Input di XmlDocument in XslTransform](xmldocument-input-to-xsltransform.md).</span><span class="sxs-lookup"><span data-stu-id="6c344-125">For more information, see [XmlDocument Input to XslTransform](xmldocument-input-to-xsltransform.md).</span></span>|
|<xref:System.Xml.XmlDataDocument>|<span data-ttu-id="6c344-126">Derivato da <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="6c344-126">It is derived from the <xref:System.Xml.XmlDocument>.</span></span> <span data-ttu-id="6c344-127">Supera i limiti dei modelli basati sui dati XML e relazionali usando un <xref:System.Data.DataSet> per ottimizzare l'archiviazione dei dati strutturati all'interno del documento XML, in base ai mapping specificati nel <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="6c344-127">It bridges the relational and XML worlds by using a <xref:System.Data.DataSet> to optimize storage of structured data within the XML document according to specified mappings on the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="6c344-128">Implementa <xref:System.Xml.XPath.IXPathNavigable>, consentendo scenari in cui è possibile eseguire trasformazioni XSLT sui dati relazionali recuperati da un database.</span><span class="sxs-lookup"><span data-stu-id="6c344-128">It implements <xref:System.Xml.XPath.IXPathNavigable>, allowing scenarios where XSLT transformations can be performed over relational data retrieved from a database.</span></span> <span data-ttu-id="6c344-129">Per altre informazioni, vedere [Integrazione di XML con dati relazionali e ADO.NET](xml-integration-with-relational-data-and-adonet.md).</span><span class="sxs-lookup"><span data-stu-id="6c344-129">For more information, see [XML Integration with Relational Data and ADO.NET](xml-integration-with-relational-data-and-adonet.md).</span></span>|
|<xref:System.Xml.XPath.XPathDocument>|<span data-ttu-id="6c344-130">Questa classe è ottimizzata per l'elaborazione con <xref:System.Xml.Xsl.XslTransform> e per le query XPath. Fornisce una cache di sola lettura a elevate prestazioni.</span><span class="sxs-lookup"><span data-stu-id="6c344-130">This class is optimized for <xref:System.Xml.Xsl.XslTransform> processing and XPath queries, and it provides a read-only high performance cache.</span></span> <span data-ttu-id="6c344-131">Implementa <xref:System.Xml.XPath.IXPathNavigable> ed è l'archivio migliore da usare per le trasformazioni XSLT.</span><span class="sxs-lookup"><span data-stu-id="6c344-131">It implements <xref:System.Xml.XPath.IXPathNavigable> and is the preferred store to use for XSLT transformations.</span></span>|
|<xref:System.Xml.XPath.XPathNodeIterator>|<span data-ttu-id="6c344-132">Consente di navigare nei set di nodi XPath.</span><span class="sxs-lookup"><span data-stu-id="6c344-132">It provides navigation over XPath node sets.</span></span> <span data-ttu-id="6c344-133">Tutti i metodi di selezione XPath di <xref:System.Xml.XPath.XPathNavigator> restituiscono un <xref:System.Xml.XPath.XPathNodeIterator>.</span><span class="sxs-lookup"><span data-stu-id="6c344-133">All XPath selection methods on the <xref:System.Xml.XPath.XPathNavigator> return an <xref:System.Xml.XPath.XPathNodeIterator>.</span></span> <span data-ttu-id="6c344-134">È possibile creare più oggetti <xref:System.Xml.XPath.XPathNodeIterator> nello stesso archivio, ognuno dei quali rappresenta un set di nodi selezionato.</span><span class="sxs-lookup"><span data-stu-id="6c344-134">Multiple <xref:System.Xml.XPath.XPathNodeIterator> objects can be created over the same store, each representing a selected set of nodes.</span></span>|

## <a name="msxml-xslt-extensions"></a><span data-ttu-id="6c344-135">Estensioni XSLT di MSXML</span><span class="sxs-lookup"><span data-stu-id="6c344-135">MSXML XSLT Extensions</span></span>

<span data-ttu-id="6c344-136">Le funzioni `msxsl:script` e `msxsl:node-set` sono le uniche estensioni XSLT di MSXML (Microsoft XML Core Services) supportate dalla classe <xref:System.Xml.Xsl.XslTransform>.</span><span class="sxs-lookup"><span data-stu-id="6c344-136">The `msxsl:script` and `msxsl:node-set` functions are the only Microsoft XML Core Services (MSXML) XSLT extensions supported by the <xref:System.Xml.Xsl.XslTransform> class.</span></span>

## <a name="example"></a><span data-ttu-id="6c344-137">Esempio</span><span class="sxs-lookup"><span data-stu-id="6c344-137">Example</span></span>

<span data-ttu-id="6c344-138">Nell'esempio di codice seguente viene caricato un foglio di stile XSLT, il file mydata.xml viene letto in un <xref:System.Xml.XPath.XPathDocument> e viene eseguita una trasformazione sui dati basata sul file fittizio myStyleSheet.xsl. L'output formattato viene quindi inviato alla console.</span><span class="sxs-lookup"><span data-stu-id="6c344-138">The following code example loads an XSLT style sheet, reads a file called mydata.xml into an <xref:System.Xml.XPath.XPathDocument>, and performs a transformation on the data on a fictitious file called myStyleSheet.xsl, sending the formatted output to the console.</span></span>

```vb
Imports System.IO
Imports System.Xml
Imports System.Xml.XPath
Imports System.Xml.Xsl

Public Class Sample
    Private filename As [String] = "mydata.xml"
    Private stylesheet As [String] = "myStyleSheet.xsl"

    Public Shared Sub Main()
        Dim xslt As New XslTransform()
        xslt.Load(stylesheet)
        Dim xpathdocument As New XPathDocument(filename)
        Dim writer As New XmlTextWriter(Console.Out)
        writer.Formatting = Formatting.Indented

        xslt.Transform(xpathdocument, Nothing, writer, Nothing)
    End Sub 'Main
End Class 'Sample
```

```csharp
using System;
using System.IO;
using System.Xml;
using System.Xml.XPath;
using System.Xml.Xsl;

public class Sample 
{
    private const String filename = "mydata.xml";
    private const String stylesheet = "myStyleSheet.xsl";

    public static void Main()
    {
        XslTransform xslt = new XslTransform();
        xslt.Load(stylesheet);
        XPathDocument xpathdocument = new XPathDocument(filename);
        XmlTextWriter writer = new XmlTextWriter(Console.Out);
        writer.Formatting = Formatting.Indented;

        xslt.Transform(xpathdocument, null, writer, null);
    }
}
```

## <a name="see-also"></a><span data-ttu-id="6c344-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6c344-139">See also</span></span>

- <xref:System.Xml.Xsl.XslTransform>
- [<span data-ttu-id="6c344-140">Implementazione del processore XSLT da parte della classe XslTransform</span><span class="sxs-lookup"><span data-stu-id="6c344-140">XslTransform Class Implements the XSLT Processor</span></span>](xsltransform-class-implements-the-xslt-processor.md)
- [<span data-ttu-id="6c344-141">Implementazione di comportamenti discretionary nella classe XslTransform</span><span class="sxs-lookup"><span data-stu-id="6c344-141">Implementation of Discretionary Behaviors in the XslTransform Class</span></span>](implementation-of-discretionary-behaviors-in-the-xsltransform-class.md)
- [<span data-ttu-id="6c344-142">XPathNavigator nelle trasformazioni</span><span class="sxs-lookup"><span data-stu-id="6c344-142">XPathNavigator in Transformations</span></span>](xpathnavigator-in-transformations.md)
- [<span data-ttu-id="6c344-143">XPathNodeIterator nelle trasformazioni</span><span class="sxs-lookup"><span data-stu-id="6c344-143">XPathNodeIterator in Transformations</span></span>](xpathnodeiterator-in-transformations.md)
- [<span data-ttu-id="6c344-144">Input di XPathDocument in XslTransform</span><span class="sxs-lookup"><span data-stu-id="6c344-144">XPathDocument Input to XslTransform</span></span>](xpathdocument-input-to-xsltransform.md)
- [<span data-ttu-id="6c344-145">Input di XmlDataDocument in XslTransform</span><span class="sxs-lookup"><span data-stu-id="6c344-145">XmlDataDocument Input to XslTransform</span></span>](xmldatadocument-input-to-xsltransform.md)
- [<span data-ttu-id="6c344-146">Input di XmlDocument in XslTransform</span><span class="sxs-lookup"><span data-stu-id="6c344-146">XmlDocument Input to XslTransform</span></span>](xmldocument-input-to-xsltransform.md)
