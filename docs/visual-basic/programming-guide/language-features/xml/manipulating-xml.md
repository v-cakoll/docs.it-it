---
title: Modifica di XML in Visual Basic
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- LINQ to XML [Visual Basic], manipulating XML
- Visual Basic code, XML
- XML [Visual Basic], manipulating
ms.assetid: da32cffb-198d-41b1-9af3-260fe32e3b7d
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 061617524659ac2f8793e2030f26a2d6b2724a64
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="manipulating-xml-in-visual-basic"></a><span data-ttu-id="c8d13-102">Modifica di XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c8d13-102">Manipulating XML in Visual Basic</span></span>
<span data-ttu-id="c8d13-103">È possibile utilizzare *valori letterali XML* caricare XML da un'origine esterna, ad esempio una stringa, un file o un flusso.</span><span class="sxs-lookup"><span data-stu-id="c8d13-103">You can use *XML literals* to load XML from an external source such as a string, file, or stream.</span></span> <span data-ttu-id="c8d13-104">È quindi possibile utilizzare [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] per modificare il codice XML e utilizzare [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] per eseguire query in XML.</span><span class="sxs-lookup"><span data-stu-id="c8d13-104">You can then use [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] to manipulate the XML and use [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] to query the XML.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c8d13-105">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="c8d13-105">In This Section</span></span>  
 [<span data-ttu-id="c8d13-106">Procedura: Caricare XML da un file, da una stringa o da un flusso</span><span class="sxs-lookup"><span data-stu-id="c8d13-106">How to: Load XML from a File, String, or Stream</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md)  
 <span data-ttu-id="c8d13-107">Di seguito viene illustrato come caricare XML in un <xref:System.Xml.Linq.XDocument> o <xref:System.Xml.Linq.XElement> oggetto da un file di testo, una stringa o un flusso.</span><span class="sxs-lookup"><span data-stu-id="c8d13-107">Demonstrates how to load XML into an <xref:System.Xml.Linq.XDocument> or <xref:System.Xml.Linq.XElement> object from a text file, string, or stream.</span></span>  
  
 [<span data-ttu-id="c8d13-108">Procedura: Trasformare XML usando LINQ</span><span class="sxs-lookup"><span data-stu-id="c8d13-108">How to: Transform XML by Using LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-transform-xml-by-using-linq.md)  
 <span data-ttu-id="c8d13-109">Di seguito viene illustrato come trasformare il contenuto di un <xref:System.Xml.Linq.XDocument> oggetto in un nuovo documento XML.</span><span class="sxs-lookup"><span data-stu-id="c8d13-109">Demonstrates how to transform the contents of an <xref:System.Xml.Linq.XDocument> object into a new XML document.</span></span>  
  
 [<span data-ttu-id="c8d13-110">Procedura: Modificare valori letterali XML</span><span class="sxs-lookup"><span data-stu-id="c8d13-110">How to: Modify XML Literals</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-modify-xml-literals.md)  
 <span data-ttu-id="c8d13-111">Viene illustrato come modificare gli elementi, attributi e valori in un valore letterale XML.</span><span class="sxs-lookup"><span data-stu-id="c8d13-111">Demonstrates how to modify the elements, attributes, and values in an XML literal.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="c8d13-112">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="c8d13-112">Related Sections</span></span>  
 [<span data-ttu-id="c8d13-113">Proprietà Axis XML</span><span class="sxs-lookup"><span data-stu-id="c8d13-113">XML Axis Properties</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)  
 <span data-ttu-id="c8d13-114">Vengono forniti collegamenti alle sezioni che descrivono le varie proprietà di accesso XML.</span><span class="sxs-lookup"><span data-stu-id="c8d13-114">Provides links to sections that describe the various XML access properties.</span></span>  
  
 [<span data-ttu-id="c8d13-115">Cenni preliminari su LINQ to XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c8d13-115">Overview of LINQ to XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/overview-of-linq-to-xml.md)  
 <span data-ttu-id="c8d13-116">Fornisce un'introduzione all'uso [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="c8d13-116">Provides an introduction to using [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] in Visual Basic.</span></span>  
  
 [<span data-ttu-id="c8d13-117">Creazione di XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c8d13-117">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 <span data-ttu-id="c8d13-118">Fornisce un'introduzione all'utilizzo di valori letterali XML in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="c8d13-118">Provides an introduction to using XML literals in Visual Basic.</span></span>  
  
 [<span data-ttu-id="c8d13-119">Accesso a XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c8d13-119">Accessing XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)  
 <span data-ttu-id="c8d13-120">Viene illustrato come accedere a parti di un elemento o documento XML in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="c8d13-120">Demonstrates how to access parts of an XML element or document in Visual Basic.</span></span>  
  
 [<span data-ttu-id="c8d13-121">XML</span><span class="sxs-lookup"><span data-stu-id="c8d13-121">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)  
 <span data-ttu-id="c8d13-122">Vengono forniti collegamenti a sezioni in cui viene illustrato come utilizzare [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="c8d13-122">Provides links to sections that describe how to use [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] in Visual Basic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8d13-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c8d13-123">See Also</span></span>  
 [<span data-ttu-id="c8d13-124">XML</span><span class="sxs-lookup"><span data-stu-id="c8d13-124">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)  
 [<span data-ttu-id="c8d13-125">LINQ</span><span class="sxs-lookup"><span data-stu-id="c8d13-125">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [<span data-ttu-id="c8d13-126">Introduzione a LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c8d13-126">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
