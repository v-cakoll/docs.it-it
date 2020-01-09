---
title: Documenti e dati XML
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: e695047f-3c0f-4045-8708-5baea91cc380
ms.openlocfilehash: e0c3f3e99b06b65caf79d87a7831369f6fb33b08
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710791"
---
# <a name="xml-documents-and-data"></a>Documenti e dati XML

.NET Framework fornisce un set completo e integrato di classi tramite cui è possibile compilare facilmente applicazioni che supportano XML. Le classi negli spazi dei nomi seguenti supportano l'analisi e la scrittura del codice XML, la modifica dei dati XML in memoria, la convalida dei dati e la trasformazione XSLT.

- <xref:System.Xml>

- <xref:System.Xml.XPath>

- <xref:System.Xml.Xsl>

- <xref:System.Xml.Schema>

- <xref:System.Xml.Linq>

Per un elenco completo, cercare "System.Xml" nel [browser API .NET](https://docs.microsoft.com/dotnet/api/?term=system.xml).

Le classi in questi spazi dei nomi supportano le raccomandazioni W3C (World Wide Web Consortium). Ad esempio:

- La classe <xref:System.Xml.XmlDocument?displayProperty=nameWithType> implementa le raccomandazioni [W3C Document Object Model (DOM) Level 1 Core](https://www.w3.org/TR/REC-DOM-Level-1/) e [DOM Level 2 Core](https://www.w3.org/TR/DOM-Level-2-Core/).

- Le classi <xref:System.Xml.XmlReader?displayProperty=nameWithType> e <xref:System.Xml.XmlWriter?displayProperty=nameWithType> supportano le raccomandazioni [W3C XML 1.0](https://www.w3.org/TR/2006/REC-xml-20060816/) e [Namespaces in XML](https://www.w3.org/TR/REC-xml-names/).

- Gli schemi nella classe <xref:System.Xml.Schema.XmlSchemaSet?displayProperty=nameWithType> supportano le raccomandazioni [W3C XML Schema Part 1: Structures](https://www.w3.org/TR/xmlschema-1/) e [XML Schema Part 2: Datatypes](https://www.w3.org/TR/xmlschema-2/).

- Le classi nello spazio dei nomi <xref:System.Xml.Xsl?displayProperty=nameWithType> supportano le trasformazioni XSLT conformi alla raccomandazione [W3C XSLT 1.0](https://www.w3.org/TR/xslt).

Le classi XML in .NET Framework offrono i vantaggi seguenti:

- **Produttività.** Grazie a [LINQ to XML (C#)](../../../csharp/programming-guide/concepts/linq/linq-to-xml-overview.md) e [LINQ to XML (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md) è più semplice programmare con XML. Inoltre, viene garantita un'esperienza per le query simile a SQL.

- **Estendibilità.** Le classi XML di .NET Framework sono estendibili mediante l'uso di classi di base astratte e metodi virtuali. Ad esempio, è possibile creare una classe derivata della classe <xref:System.Xml.XmlUrlResolver> tramite cui viene archiviato il flusso della cache nel disco locale.

- **Architettura modulare.** .NET Framework offre un'architettura in cui è possibile un utilizzo interscambiabile dei componenti e i dati possono essere trasmessi tra i componenti. Ad esempio, un archivio dati quale un oggetto <xref:System.Xml.XPath.XPathDocument> o <xref:System.Xml.XmlDocument> può essere trasformato con la classe <xref:System.Xml.Xsl.XslCompiledTransform> e l'output potrà quindi essere inserito in un flusso di un altro archivio o restituito come flusso da un servizio Web.

- **Prestazioni.** Per prestazioni ottimali dell'applicazione, alcune delle classi XML di .NET Framework supportano un modello basato sul flusso con le caratteristiche seguenti:

  - Minimo utilizzo della memorizzazione nella cache per l'analisi di tipo forward-only, modello pull (<xref:System.Xml.XmlReader>).

  - Convalida di tipo forward-only (<xref:System.Xml.XmlReader>).

  - Tipo di navigazione tramite cursore grazie al quale la creazione di nodi è ridotta a un singolo nodo virtuale, fornendo nel contempo l'accesso casuale al documento (<xref:System.Xml.XPath.XPathNavigator>).

  Per ottimizzare le prestazioni ogni volta che è necessaria l'elaborazione XSLT, è possibile usare la classe <xref:System.Xml.XPath.XPathDocument>, vale a dire un archivio ottimizzato di sola lettura per query XPath progettate per interagire in modo efficiente con la classe <xref:System.Xml.Xsl.XslCompiledTransform>.

- **Integrazione con ADO.NET.** Le classi XML e [ADO.NET](../../../../docs/framework/data/adonet/index.md) sono strettamente integrati per riunire dati relazionali e XML. La classe <xref:System.Data.DataSet> è una cache in memoria dei dati recuperati da un database. Con la classe <xref:System.Data.DataSet> è possibile leggere e scrivere il codice XML usando le classi <xref:System.Xml.XmlReader> e <xref:System.Xml.XmlWriter>, mantenere la struttura interna degli schemi relazionali come XML Schema (XSD) e dedurre la struttura dello schema di un documento XML.

## <a name="in-this-section"></a>In questa sezione

[Opzioni di elaborazione XML](../../../../docs/standard/data/xml/xml-processing-options.md) illustra le opzioni per l'elaborazione di dati XML.

[Elaborazione di dati XML in memoria](../../../../docs/standard/data/xml/processing-xml-data-in-memory.md) Vengono illustrati i tre modelli per l'elaborazione dei dati XML in memoria: [LINQ to XMLC#()](../../../csharp/programming-guide/concepts/linq/linq-to-xml-overview.md) e [LINQ to XML (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md), la classe <xref:System.Xml.XmlDocument> (basata sulla Document Object Model W3C) e la classe <xref:System.Xml.XPath.XPathDocument> (basata sul modello di dati XPath).

[Trasformazioni XSLT](../../../../docs/standard/data/xml/xslt-transformations.md)\
Viene descritto come usare il processore XSLT.

[Modello a oggetti dello schema XML](../../../../docs/standard/data/xml/xml-schema-object-model-som.md)\
Vengono descritte le classi usate per la compilazione e la modifica di XML Schema (XSD) fornendo una classe <xref:System.Xml.Schema.XmlSchema> per il caricamento e la modifica di uno schema.

[Integrazione di XML con dati relazionali e ADO.NET](../../../../docs/standard/data/xml/xml-integration-with-relational-data-and-adonet.md)\
Viene descritto come .NET Framework consente l'accesso in tempo reale e in modalità sincrona alle rappresentazioni sia relazionali sia gerarchiche di dati tramite gli oggetti <xref:System.Data.DataSet> e <xref:System.Xml.XmlDataDocument>.

[Gestione di spazi dei nomi in un documento XML](../../../../docs/standard/data/xml/managing-namespaces-in-an-xml-document.md)\
Viene descritto come viene usata la classe <xref:System.Xml.XmlNamespaceManager> per archiviare e gestire le informazioni sugli spazi dei nomi.

[Supporto di tipi di dati nelle classi System.Xml](../../../../docs/standard/data/xml/type-support-in-the-system-xml-classes.md)\
Vengono descritti il mapping dei tipi di dati XML ai tipi CLR, la conversione di tipi di dati XML e altre funzionalità di supporto dei tipi nelle classi <xref:System.Xml>.

## <a name="related-sections"></a>Sezioni correlate

[ADO.NET](../../../../docs/framework/data/adonet/index.md)\
Vengono fornite informazioni sulle modalità di accesso ai dati usando ADO.NET.

[Sicurezza](../../../../docs/standard/security/index.md)\
Viene fornita una panoramica sul sistema di sicurezza di .NET Framework.
