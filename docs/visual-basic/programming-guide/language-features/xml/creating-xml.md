---
title: Creazione di XML in Visual Basic
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- XML [Visual Basic], creating
- LINQ to XML [Visual Basic], creating XML
- XML literals [Visual Basic], creating
ms.assetid: 8ae29ec5-e5fb-4137-9df5-60a288df7045
caps.latest.revision: 24
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 029ff0a2120809fd4637de5910adaffa60e3b8a7
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="creating-xml-in-visual-basic"></a><span data-ttu-id="c8142-102">Creazione di XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c8142-102">Creating XML in Visual Basic</span></span>
<span data-ttu-id="c8142-103">Visual Basic consente di utilizzare *valori letterali XML* direttamente nel codice.</span><span class="sxs-lookup"><span data-stu-id="c8142-103">Visual Basic enables you to use *XML literals* directly in your code.</span></span> <span data-ttu-id="c8142-104">Sintassi del valore letterale XML rappresenta [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] oggetti ed è simile alla sintassi XML 1.0.</span><span class="sxs-lookup"><span data-stu-id="c8142-104">The XML literal syntax represents [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objects, and it is similar to the XML 1.0 syntax.</span></span> <span data-ttu-id="c8142-105">Questo rende più semplice creare elementi, documenti e frammenti XML a livello di programmazione perché il codice ha la stessa struttura del XML finale.</span><span class="sxs-lookup"><span data-stu-id="c8142-105">This makes it easier to create XML elements, documents, and fragments programmatically because your code has the same structure as the final XML.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c8142-106">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="c8142-106">In This Section</span></span>  
  
|<span data-ttu-id="c8142-107">Termine</span><span class="sxs-lookup"><span data-stu-id="c8142-107">Term</span></span>|<span data-ttu-id="c8142-108">Definizione</span><span class="sxs-lookup"><span data-stu-id="c8142-108">Definition</span></span>|  
|---|---|  
|[<span data-ttu-id="c8142-109">Cenni preliminari sui valori letterali XML</span><span class="sxs-lookup"><span data-stu-id="c8142-109">XML Literals Overview</span></span>](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-overview.md)|<span data-ttu-id="c8142-110">Introduzione ai valori letterali XML e come interagiscono [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c8142-110">Introduction to XML literals and how they relate to [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span></span>|  
|[<span data-ttu-id="c8142-111">Espressioni incorporate in XML</span><span class="sxs-lookup"><span data-stu-id="c8142-111">Embedded Expressions in XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)|<span data-ttu-id="c8142-112">Viene descritto come utilizzare le espressioni incorporate nei valori letterali XML.</span><span class="sxs-lookup"><span data-stu-id="c8142-112">Describes how to use embedded expressions in XML literals.</span></span>|  
|[<span data-ttu-id="c8142-113">Procedura: Creare valori letterali XML</span><span class="sxs-lookup"><span data-stu-id="c8142-113">How to: Create XML Literals</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-create-xml-literals.md)|<span data-ttu-id="c8142-114">Viene descritto come creare un elemento XML nel codice utilizzando un valore letterale XML.</span><span class="sxs-lookup"><span data-stu-id="c8142-114">Describes how to create an XML element in code by using an XML literal.</span></span>|  
|[<span data-ttu-id="c8142-115">Spazi vuoti nei valori letterali XML</span><span class="sxs-lookup"><span data-stu-id="c8142-115">White Space in XML Literals</span></span>](../../../../visual-basic/programming-guide/language-features/xml/white-space-in-xml-literals.md)|<span data-ttu-id="c8142-116">Viene descritto come Visual Basic considera gli spazi vuoti nei valori letterali XML.</span><span class="sxs-lookup"><span data-stu-id="c8142-116">Describes how Visual Basic treats white space in XML literals.</span></span>|  
|[<span data-ttu-id="c8142-117">Valori letterali XML e specifica XML 1.0</span><span class="sxs-lookup"><span data-stu-id="c8142-117">XML Literals and the XML 1.0 Specification</span></span>](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md)|<span data-ttu-id="c8142-118">Viene descritta la sintassi del valore letterale XML in Visual Basic relazione alla specifica XML 1.0.</span><span class="sxs-lookup"><span data-stu-id="c8142-118">Describes how the XML literal syntax in Visual Basic relates to the XML 1.0 specification.</span></span>|  
|[<span data-ttu-id="c8142-119">Procedura: Incorporare espressioni nei valori letterali XML</span><span class="sxs-lookup"><span data-stu-id="c8142-119">How to: Embed Expressions in XML Literals</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-embed-expressions-in-xml-literals.md)|<span data-ttu-id="c8142-120">Viene descritto come utilizzare le espressioni incorporate nei valori letterali XML per creare il contenuto in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="c8142-120">Describes how to use embedded expressions in XML literals to create content at run time.</span></span>|  
|[<span data-ttu-id="c8142-121">Nomi di elementi e attributi XML dichiarati</span><span class="sxs-lookup"><span data-stu-id="c8142-121">Names of Declared XML Elements and Attributes</span></span>](../../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)|<span data-ttu-id="c8142-122">Vengono fornite istruzioni per la denominazione di elementi e attributi XML.</span><span class="sxs-lookup"><span data-stu-id="c8142-122">Describes guidelines for naming XML elements and attributes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c8142-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c8142-123">See Also</span></span>  
 [<span data-ttu-id="c8142-124">XML</span><span class="sxs-lookup"><span data-stu-id="c8142-124">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
