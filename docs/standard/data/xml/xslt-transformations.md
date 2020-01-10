---
title: Trasformazioni XSLT
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 202f8820-224c-494f-b61e-cd127eac6e03
ms.openlocfilehash: 4bbecfbf1b163a9d7bfe6957806095b5b17fbab7
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709634"
---
# <a name="xslt-transformations"></a><span data-ttu-id="562af-102">Trasformazioni XSLT</span><span class="sxs-lookup"><span data-stu-id="562af-102">XSLT Transformations</span></span>
<span data-ttu-id="562af-103">L'Extensible Stylesheet Language Transformation (XSLT) consente di trasformare il contenuto di un documento XML di origine in un altro documento di formato o struttura diversi,</span><span class="sxs-lookup"><span data-stu-id="562af-103">The Extensible Stylesheet Language Transformation (XSLT) lets you transform the content of a source XML document into another document that is different in format or structure.</span></span> <span data-ttu-id="562af-104">ad esempio per trasformare l'XML in HTML per l'uso su un sito Web o per trasformarlo in un documento che contenga solo i campi richiesti da un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="562af-104">For example, you can use XSLT to transform XML into HTML for use on a Web site or to transform it into a document that contains only the fields required by an application.</span></span> <span data-ttu-id="562af-105">Questo processo di trasformazione è specificato dalla raccomandazione [W3C XSL Transformations (XSLT) Version 1.0 recommendation](https://www.w3.org/TR/xslt-10/).</span><span class="sxs-lookup"><span data-stu-id="562af-105">This transformation process is specified by the [W3C XSL Transformations (XSLT) Version 1.0 recommendation](https://www.w3.org/TR/xslt-10/).</span></span>  
  
 <span data-ttu-id="562af-106">La classe <xref:System.Xml.Xsl.XslCompiledTransform> è il processore XSLT in .NET.</span><span class="sxs-lookup"><span data-stu-id="562af-106">The <xref:System.Xml.Xsl.XslCompiledTransform> class is the XSLT processor in .NET.</span></span> <span data-ttu-id="562af-107">La classe <xref:System.Xml.Xsl.XslCompiledTransform> supporta la [raccomandazione W3C XSLT 1.0](https://www.w3.org/TR/xslt-10/).</span><span class="sxs-lookup"><span data-stu-id="562af-107">The <xref:System.Xml.Xsl.XslCompiledTransform> class supports the [W3C XSLT 1.0 recommendation](https://www.w3.org/TR/xslt-10/).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="562af-108">La classe <xref:System.Xml.Xsl.XslTransform> è obsoleta in .NET Framework versione 2.0.</span><span class="sxs-lookup"><span data-stu-id="562af-108">The <xref:System.Xml.Xsl.XslTransform> class is obsolete in .NET Framework version 2.0.</span></span> <span data-ttu-id="562af-109">La classe <xref:System.Xml.Xsl.XslCompiledTransform> è una nuova implementazione del motore XSLT,</span><span class="sxs-lookup"><span data-stu-id="562af-109">The <xref:System.Xml.Xsl.XslCompiledTransform> class is a new implementation of the XSLT engine.</span></span> <span data-ttu-id="562af-110">che include prestazioni migliori e nuove funzionalità di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="562af-110">It includes performance improvements and new security features.</span></span> <span data-ttu-id="562af-111">Si consiglia di creare le applicazioni XSLT usando la classe <xref:System.Xml.Xsl.XslCompiledTransform>.</span><span class="sxs-lookup"><span data-stu-id="562af-111">The recommended practice is to create XSLT applications using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="562af-112">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="562af-112">In This Section</span></span>  
 [<span data-ttu-id="562af-113">Uso della classe XslCompiledTransform</span><span class="sxs-lookup"><span data-stu-id="562af-113">Using the XslCompiledTransform Class</span></span>](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md)  
 <span data-ttu-id="562af-114">Vengono fornite informazioni sull'utilizzo della classe <xref:System.Xml.Xsl.XslCompiledTransform>.</span><span class="sxs-lookup"><span data-stu-id="562af-114">Provides information on using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span>  
  
 [<span data-ttu-id="562af-115">Migrazione dalla classe XslTransform</span><span class="sxs-lookup"><span data-stu-id="562af-115">Migrating From the XslTransform Class</span></span>](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md)  
 <span data-ttu-id="562af-116">Viene descritto come migrare il codice dalla classe <xref:System.Xml.Xsl.XslTransform>.</span><span class="sxs-lookup"><span data-stu-id="562af-116">Discusses how to migrate code from the <xref:System.Xml.Xsl.XslTransform> class.</span></span>  
  
 [<span data-ttu-id="562af-117">Compilatore XSLT (xsltc.exe)</span><span class="sxs-lookup"><span data-stu-id="562af-117">XSLT Compiler (xsltc.exe)</span></span>](../../../../docs/standard/data/xml/xslt-compiler-xsltc-exe.md)  
 <span data-ttu-id="562af-118">Vengono fornite informazioni sull'utilizzo del compilatore XSLT.</span><span class="sxs-lookup"><span data-stu-id="562af-118">Provides information on using the XSLT compiler.</span></span>  
  
 [<span data-ttu-id="562af-119">Trasformazioni XSLT con la classe XslTransform</span><span class="sxs-lookup"><span data-stu-id="562af-119">XSLT Transformations with the XslTransform Class</span></span>](../../../../docs/standard/data/xml/xslt-transformations-with-the-xsltransform-class.md)  
 <span data-ttu-id="562af-120">Vengono fornite informazioni sull'utilizzo della classe <xref:System.Xml.Xsl.XslTransform>.</span><span class="sxs-lookup"><span data-stu-id="562af-120">Provides information on using the <xref:System.Xml.Xsl.XslTransform> class.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="562af-121">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="562af-121">Reference</span></span>  
 <xref:System.Xml.Xsl.XslCompiledTransform>  
 <xref:System.Xml.Xsl.XsltArgumentList>  
 <xref:System.Xml.Xsl.XsltSettings>  
  
## <a name="related-sections"></a><span data-ttu-id="562af-122">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="562af-122">Related Sections</span></span>  
 [<span data-ttu-id="562af-123">Documenti e dati XML</span><span class="sxs-lookup"><span data-stu-id="562af-123">XML Documents and Data</span></span>](../../../../docs/standard/data/xml/index.md)
