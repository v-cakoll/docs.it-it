---
title: Modifica di XML in Visual Basic | Documenti di Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- LINQ to XML [Visual Basic], manipulating XML
- Visual Basic code, XML
- XML [Visual Basic], manipulating
ms.assetid: da32cffb-198d-41b1-9af3-260fe32e3b7d
caps.latest.revision: 5
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 62b955d78eb507aab4c786e84f3044ba54a38ebc
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="manipulating-xml-in-visual-basic"></a><span data-ttu-id="365e4-102">Modifica di XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="365e4-102">Manipulating XML in Visual Basic</span></span>
<span data-ttu-id="365e4-103">È possibile utilizzare *valori letterali XML* caricare XML da un'origine esterna, ad esempio una stringa, un file o un flusso.</span><span class="sxs-lookup"><span data-stu-id="365e4-103">You can use *XML literals* to load XML from an external source such as a string, file, or stream.</span></span> <span data-ttu-id="365e4-104">È quindi possibile utilizzare [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] per modificare il codice XML e utilizzare [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)] per eseguire query in XML.</span><span class="sxs-lookup"><span data-stu-id="365e4-104">You can then use [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] to manipulate the XML and use [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)] to query the XML.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="365e4-105">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="365e4-105">In This Section</span></span>  
 [<span data-ttu-id="365e4-106">Procedura: Caricare XML da un file, da una stringa o da un flusso</span><span class="sxs-lookup"><span data-stu-id="365e4-106">How to: Load XML from a File, String, or Stream</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md)  
 <span data-ttu-id="365e4-107">Di seguito viene illustrato come caricare XML in un <xref:System.Xml.Linq.XDocument>o <xref:System.Xml.Linq.XElement>oggetto da un file di testo, stringa o flusso.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="365e4-107">Demonstrates how to load XML into an <xref:System.Xml.Linq.XDocument> or <xref:System.Xml.Linq.XElement> object from a text file, string, or stream.</span></span>  
  
 [<span data-ttu-id="365e4-108">Procedura: Trasformare XML usando LINQ</span><span class="sxs-lookup"><span data-stu-id="365e4-108">How to: Transform XML by Using LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-transform-xml-by-using-linq.md)  
 <span data-ttu-id="365e4-109">Di seguito viene illustrato come trasformare il contenuto di un <xref:System.Xml.Linq.XDocument>oggetto in un nuovo documento XML.</xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="365e4-109">Demonstrates how to transform the contents of an <xref:System.Xml.Linq.XDocument> object into a new XML document.</span></span>  
  
 [<span data-ttu-id="365e4-110">Procedura: Modificare valori letterali XML</span><span class="sxs-lookup"><span data-stu-id="365e4-110">How to: Modify XML Literals</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-modify-xml-literals.md)  
 <span data-ttu-id="365e4-111">Viene illustrato come modificare gli elementi, attributi e valori in un valore letterale XML.</span><span class="sxs-lookup"><span data-stu-id="365e4-111">Demonstrates how to modify the elements, attributes, and values in an XML literal.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="365e4-112">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="365e4-112">Related Sections</span></span>  
 [<span data-ttu-id="365e4-113">Proprietà Axis XML</span><span class="sxs-lookup"><span data-stu-id="365e4-113">XML Axis Properties</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)  
 <span data-ttu-id="365e4-114">Vengono forniti collegamenti alle sezioni che descrivono le varie proprietà di accesso XML.</span><span class="sxs-lookup"><span data-stu-id="365e4-114">Provides links to sections that describe the various XML access properties.</span></span>  
  
 [<span data-ttu-id="365e4-115">Panoramica di LINQ to XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="365e4-115">Overview of LINQ to XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/overview-of-linq-to-xml.md)  
 <span data-ttu-id="365e4-116">Viene fornita un'introduzione all'utilizzo di [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="365e4-116">Provides an introduction to using [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] in Visual Basic.</span></span>  
  
 [<span data-ttu-id="365e4-117">Creazione di XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="365e4-117">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 <span data-ttu-id="365e4-118">Viene fornita un'introduzione all'utilizzo di valori letterali XML in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="365e4-118">Provides an introduction to using XML literals in Visual Basic.</span></span>  
  
 [<span data-ttu-id="365e4-119">Accesso a XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="365e4-119">Accessing XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)  
 <span data-ttu-id="365e4-120">Viene illustrato come accedere a parti di un elemento o documento XML in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="365e4-120">Demonstrates how to access parts of an XML element or document in Visual Basic.</span></span>  
  
 [<span data-ttu-id="365e4-121">XML</span><span class="sxs-lookup"><span data-stu-id="365e4-121">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)  
 <span data-ttu-id="365e4-122">Vengono forniti collegamenti ad argomenti in cui viene descritto come utilizzare [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="365e4-122">Provides links to sections that describe how to use [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] in Visual Basic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="365e4-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="365e4-123">See Also</span></span>  
 <span data-ttu-id="365e4-124">[XML](../../../../visual-basic/programming-guide/language-features/xml/index.md) </span><span class="sxs-lookup"><span data-stu-id="365e4-124">[XML](../../../../visual-basic/programming-guide/language-features/xml/index.md) </span></span>  
<span data-ttu-id="365e4-125"> [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md) </span><span class="sxs-lookup"><span data-stu-id="365e4-125"> [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md) </span></span>  
<span data-ttu-id="365e4-126"> [Introduzione a LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span><span class="sxs-lookup"><span data-stu-id="365e4-126"> [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span></span>
