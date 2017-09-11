---
title: Creazione di XML in Visual Basic | Documenti di Microsoft
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
- XML [Visual Basic], creating
- LINQ to XML [Visual Basic], creating XML
- XML literals [Visual Basic], creating
ms.assetid: 8ae29ec5-e5fb-4137-9df5-60a288df7045
caps.latest.revision: 24
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
ms.openlocfilehash: ec45ab4dc7d4c9282d444c00b0b262b3d8dd4da1
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="creating-xml-in-visual-basic"></a><span data-ttu-id="6624a-102">Creazione di XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6624a-102">Creating XML in Visual Basic</span></span>
[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="6624a-103">Consente di utilizzare *valori letterali XML* direttamente nel codice.</span><span class="sxs-lookup"><span data-stu-id="6624a-103"> enables you to use *XML literals* directly in your code.</span></span> <span data-ttu-id="6624a-104">Sintassi del valore letterale XML rappresenta [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] oggetti ed è simile alla sintassi XML 1.0.</span><span class="sxs-lookup"><span data-stu-id="6624a-104">The XML literal syntax represents [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] objects, and it is similar to the XML 1.0 syntax.</span></span> <span data-ttu-id="6624a-105">Questo rende più facile creare elementi, documenti e frammenti XML a livello di programmazione perché il codice ha la stessa struttura del XML finale.</span><span class="sxs-lookup"><span data-stu-id="6624a-105">This makes it easier to create XML elements, documents, and fragments programmatically because your code has the same structure as the final XML.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6624a-106">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="6624a-106">In This Section</span></span>  
  
|<span data-ttu-id="6624a-107">Termine</span><span class="sxs-lookup"><span data-stu-id="6624a-107">Term</span></span>|<span data-ttu-id="6624a-108">Definizione</span><span class="sxs-lookup"><span data-stu-id="6624a-108">Definition</span></span>|  
|---|---|  
|[<span data-ttu-id="6624a-109">Cenni preliminari sui valori letterali XML</span><span class="sxs-lookup"><span data-stu-id="6624a-109">XML Literals Overview</span></span>](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-overview.md)|<span data-ttu-id="6624a-110">Introduzione ai valori letterali XML e le relazioni [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].</span><span class="sxs-lookup"><span data-stu-id="6624a-110">Introduction to XML literals and how they relate to [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].</span></span>|  
|[<span data-ttu-id="6624a-111">Espressioni incorporate in XML</span><span class="sxs-lookup"><span data-stu-id="6624a-111">Embedded Expressions in XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)|<span data-ttu-id="6624a-112">Viene descritto come utilizzare le espressioni incorporate nei valori letterali XML.</span><span class="sxs-lookup"><span data-stu-id="6624a-112">Describes how to use embedded expressions in XML literals.</span></span>|  
|[<span data-ttu-id="6624a-113">Procedura: Creare valori letterali XML</span><span class="sxs-lookup"><span data-stu-id="6624a-113">How to: Create XML Literals</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-create-xml-literals.md)|<span data-ttu-id="6624a-114">Viene descritto come creare un elemento XML nel codice utilizzando un valore letterale XML.</span><span class="sxs-lookup"><span data-stu-id="6624a-114">Describes how to create an XML element in code by using an XML literal.</span></span>|  
|[<span data-ttu-id="6624a-115">Spazi vuoti nei valori letterali XML</span><span class="sxs-lookup"><span data-stu-id="6624a-115">White Space in XML Literals</span></span>](../../../../visual-basic/programming-guide/language-features/xml/white-space-in-xml-literals.md)|<span data-ttu-id="6624a-116">Viene descritto come [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] considera gli spazi vuoti nei valori letterali XML.</span><span class="sxs-lookup"><span data-stu-id="6624a-116">Describes how [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] treats white space in XML literals.</span></span>|  
|[<span data-ttu-id="6624a-117">Valori letterali XML e specifica XML 1.0</span><span class="sxs-lookup"><span data-stu-id="6624a-117">XML Literals and the XML 1.0 Specification</span></span>](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md)|<span data-ttu-id="6624a-118">Viene descritto come la sintassi di valore letterale XML in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] si riferisce alla specifica XML 1.0.</span><span class="sxs-lookup"><span data-stu-id="6624a-118">Describes how the XML literal syntax in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] relates to the XML 1.0 specification.</span></span>|  
|[<span data-ttu-id="6624a-119">Procedura: Incorporare espressioni nei valori letterali XML</span><span class="sxs-lookup"><span data-stu-id="6624a-119">How to: Embed Expressions in XML Literals</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-embed-expressions-in-xml-literals.md)|<span data-ttu-id="6624a-120">Viene descritto come utilizzare le espressioni incorporate nei valori letterali XML per creare contenuto in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="6624a-120">Describes how to use embedded expressions in XML literals to create content at run time.</span></span>|  
|[<span data-ttu-id="6624a-121">Nomi di elementi e attributi XML dichiarati</span><span class="sxs-lookup"><span data-stu-id="6624a-121">Names of Declared XML Elements and Attributes</span></span>](../../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)|<span data-ttu-id="6624a-122">Vengono fornite istruzioni per la denominazione di elementi e attributi XML.</span><span class="sxs-lookup"><span data-stu-id="6624a-122">Describes guidelines for naming XML elements and attributes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6624a-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6624a-123">See Also</span></span>  
 [<span data-ttu-id="6624a-124">XML</span><span class="sxs-lookup"><span data-stu-id="6624a-124">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
