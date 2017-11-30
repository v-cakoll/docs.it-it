---
title: Trasformazioni XSLT
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 202f8820-224c-494f-b61e-cd127eac6e03
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 0d7fa8492487daff68fd8ebaf4159dd537d13e51
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="xslt-transformations"></a><span data-ttu-id="95272-102">Trasformazioni XSLT</span><span class="sxs-lookup"><span data-stu-id="95272-102">XSLT Transformations</span></span>
<span data-ttu-id="95272-103">L'Extensible Stylesheet Language Transformation (XSLT) consente di trasformare il contenuto di un documento XML di origine in un altro documento di formato o struttura diversi,</span><span class="sxs-lookup"><span data-stu-id="95272-103">The Extensible Stylesheet Language Transformation (XSLT) lets you transform the content of a source XML document into another document that is different in format or structure.</span></span> <span data-ttu-id="95272-104">ad esempio per trasformare l'XML in HTML per l'uso su un sito Web o per trasformarlo in un documento che contenga solo i campi richiesti da un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="95272-104">For example, you can use XSLT to transform XML into HTML for use on a Web site or to transform it into a document that contains only the fields required by an application.</span></span> <span data-ttu-id="95272-105">Questo processo di trasformazione è specificato per il [raccomandazione W3C XSL Transformations (XSLT) Version 1.0](http://go.microsoft.com/fwlink/?LinkID=49919).</span><span class="sxs-lookup"><span data-stu-id="95272-105">This transformation process is specified by the [W3C XSL Transformations (XSLT) Version 1.0 recommendation](http://go.microsoft.com/fwlink/?LinkID=49919).</span></span>  
  
 <span data-ttu-id="95272-106">La classe <xref:System.Xml.Xsl.XslCompiledTransform> è il processore XSLT in .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="95272-106">The <xref:System.Xml.Xsl.XslCompiledTransform> class is the XSLT processor in the .NET Framework.</span></span> <span data-ttu-id="95272-107">La classe <xref:System.Xml.Xsl.XslCompiledTransform> supporta la raccomandazione W3C XSLT 1.0.</span><span class="sxs-lookup"><span data-stu-id="95272-107">The <xref:System.Xml.Xsl.XslCompiledTransform> class supports the W3C XSLT 1.0 recommendation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="95272-108">La classe <xref:System.Xml.Xsl.XslTransform> è obsoleta in .NET Framework versione 2.0.</span><span class="sxs-lookup"><span data-stu-id="95272-108">The <xref:System.Xml.Xsl.XslTransform> class is obsolete in .NET Framework version 2.0.</span></span> <span data-ttu-id="95272-109">La classe <xref:System.Xml.Xsl.XslCompiledTransform> è una nuova implementazione del motore XSLT,</span><span class="sxs-lookup"><span data-stu-id="95272-109">The <xref:System.Xml.Xsl.XslCompiledTransform> class is a new implementation of the XSLT engine.</span></span> <span data-ttu-id="95272-110">che include prestazioni migliori e nuove funzionalità di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="95272-110">It includes performance improvements and new security features.</span></span> <span data-ttu-id="95272-111">Si consiglia di creare le applicazioni XSLT usando la classe <xref:System.Xml.Xsl.XslCompiledTransform>.</span><span class="sxs-lookup"><span data-stu-id="95272-111">The recommended practice is to create XSLT applications using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="95272-112">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="95272-112">In This Section</span></span>  
 [<span data-ttu-id="95272-113">Utilizzo della classe XslCompiledTransform</span><span class="sxs-lookup"><span data-stu-id="95272-113">Using the XslCompiledTransform Class</span></span>](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md)  
 <span data-ttu-id="95272-114">Vengono fornite informazioni sull'utilizzo della classe <xref:System.Xml.Xsl.XslCompiledTransform>.</span><span class="sxs-lookup"><span data-stu-id="95272-114">Provides information on using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span>  
  
 [<span data-ttu-id="95272-115">La migrazione dalla classe XslTransform</span><span class="sxs-lookup"><span data-stu-id="95272-115">Migrating From the XslTransform Class</span></span>](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md)  
 <span data-ttu-id="95272-116">Viene descritto come migrare il codice dalla classe <xref:System.Xml.Xsl.XslTransform>.</span><span class="sxs-lookup"><span data-stu-id="95272-116">Discusses how to migrate code from the <xref:System.Xml.Xsl.XslTransform> class.</span></span>  
  
 [<span data-ttu-id="95272-117">Compilatore XSLT (xsltc.exe)</span><span class="sxs-lookup"><span data-stu-id="95272-117">XSLT Compiler (xsltc.exe)</span></span>](../../../../docs/standard/data/xml/xslt-compiler-xsltc-exe.md)  
 <span data-ttu-id="95272-118">Vengono fornite informazioni sull'utilizzo del compilatore XSLT.</span><span class="sxs-lookup"><span data-stu-id="95272-118">Provides information on using the XSLT compiler.</span></span>  
  
 [<span data-ttu-id="95272-119">Trasformazioni XSLT con la classe XslTransform</span><span class="sxs-lookup"><span data-stu-id="95272-119">XSLT Transformations with the XslTransform Class</span></span>](../../../../docs/standard/data/xml/xslt-transformations-with-the-xsltransform-class.md)  
 <span data-ttu-id="95272-120">Vengono fornite informazioni sull'utilizzo della classe <xref:System.Xml.Xsl.XslTransform>.</span><span class="sxs-lookup"><span data-stu-id="95272-120">Provides information on using the <xref:System.Xml.Xsl.XslTransform> class.</span></span>  
  
 <span data-ttu-id="95272-121">**Nota** la <xref:System.Xml.Xsl.XslTransform> classe è obsoleta in .NET Framework versione 2.0.</span><span class="sxs-lookup"><span data-stu-id="95272-121">**Note** The <xref:System.Xml.Xsl.XslTransform> class is obsolete in the .NET Framework 2.0 release.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="95272-122">Riferimento</span><span class="sxs-lookup"><span data-stu-id="95272-122">Reference</span></span>  
 <xref:System.Xml.Xsl.XslCompiledTransform>  
  
 <xref:System.Xml.Xsl.XsltArgumentList>  
  
 <xref:System.Xml.Xsl.XsltSettings>  
  
## <a name="related-sections"></a><span data-ttu-id="95272-123">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="95272-123">Related Sections</span></span>  
 [<span data-ttu-id="95272-124">Documenti e dati XML</span><span class="sxs-lookup"><span data-stu-id="95272-124">XML Documents and Data</span></span>](../../../../docs/standard/data/xml/index.md)
