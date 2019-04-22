---
title: Creazione di XML in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], creating
- LINQ to XML [Visual Basic], creating XML
- XML literals [Visual Basic], creating
ms.assetid: 8ae29ec5-e5fb-4137-9df5-60a288df7045
ms.openlocfilehash: d847f589bc47f8ab3d6691666bbd879e795db0c6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58813041"
---
# <a name="creating-xml-in-visual-basic"></a><span data-ttu-id="65ada-102">Creazione di XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="65ada-102">Creating XML in Visual Basic</span></span>
<span data-ttu-id="65ada-103">Visual Basic consente di usare *valori letterali XML* direttamente nel codice.</span><span class="sxs-lookup"><span data-stu-id="65ada-103">Visual Basic enables you to use *XML literals* directly in your code.</span></span> <span data-ttu-id="65ada-104">La sintassi dei valori letterali XML rappresenta [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] oggetti ed è simile alla sintassi XML 1.0.</span><span class="sxs-lookup"><span data-stu-id="65ada-104">The XML literal syntax represents [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objects, and it is similar to the XML 1.0 syntax.</span></span> <span data-ttu-id="65ada-105">Questo rende più semplice creare gli elementi, documenti e frammenti XML a livello di codice perché il codice ha la stessa struttura il codice XML finale.</span><span class="sxs-lookup"><span data-stu-id="65ada-105">This makes it easier to create XML elements, documents, and fragments programmatically because your code has the same structure as the final XML.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="65ada-106">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="65ada-106">In This Section</span></span>  
  
|<span data-ttu-id="65ada-107">Termine</span><span class="sxs-lookup"><span data-stu-id="65ada-107">Term</span></span>|<span data-ttu-id="65ada-108">Definizione</span><span class="sxs-lookup"><span data-stu-id="65ada-108">Definition</span></span>|  
|---|---|  
|[<span data-ttu-id="65ada-109">Cenni preliminari sui valori letterali XML</span><span class="sxs-lookup"><span data-stu-id="65ada-109">XML Literals Overview</span></span>](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-overview.md)|<span data-ttu-id="65ada-110">Introduzione ai valori letterali XML e come interagiscono [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="65ada-110">Introduction to XML literals and how they relate to [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span></span>|  
|[<span data-ttu-id="65ada-111">Espressioni incorporate in XML</span><span class="sxs-lookup"><span data-stu-id="65ada-111">Embedded Expressions in XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)|<span data-ttu-id="65ada-112">Viene descritto come utilizzare le espressioni incorporate nei valori letterali XML.</span><span class="sxs-lookup"><span data-stu-id="65ada-112">Describes how to use embedded expressions in XML literals.</span></span>|  
|[<span data-ttu-id="65ada-113">Procedura: Creare valori letterali XML</span><span class="sxs-lookup"><span data-stu-id="65ada-113">How to: Create XML Literals</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-create-xml-literals.md)|<span data-ttu-id="65ada-114">Viene descritto come creare un elemento XML nel codice con un valore letterale XML.</span><span class="sxs-lookup"><span data-stu-id="65ada-114">Describes how to create an XML element in code by using an XML literal.</span></span>|  
|[<span data-ttu-id="65ada-115">Spazi vuoti nei valori letterali XML</span><span class="sxs-lookup"><span data-stu-id="65ada-115">White Space in XML Literals</span></span>](../../../../visual-basic/programming-guide/language-features/xml/white-space-in-xml-literals.md)|<span data-ttu-id="65ada-116">Viene descritto come Visual Basic considera gli spazi vuoti nei valori letterali XML.</span><span class="sxs-lookup"><span data-stu-id="65ada-116">Describes how Visual Basic treats white space in XML literals.</span></span>|  
|[<span data-ttu-id="65ada-117">Valori letterali XML e specifica XML 1.0</span><span class="sxs-lookup"><span data-stu-id="65ada-117">XML Literals and the XML 1.0 Specification</span></span>](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md)|<span data-ttu-id="65ada-118">Viene descritta la sintassi dei valori letterali XML in Visual Basic relazione alla specifica XML 1.0.</span><span class="sxs-lookup"><span data-stu-id="65ada-118">Describes how the XML literal syntax in Visual Basic relates to the XML 1.0 specification.</span></span>|  
|[<span data-ttu-id="65ada-119">Procedura: Incorporare espressioni nei valori letterali XML</span><span class="sxs-lookup"><span data-stu-id="65ada-119">How to: Embed Expressions in XML Literals</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-embed-expressions-in-xml-literals.md)|<span data-ttu-id="65ada-120">Viene descritto come utilizzare le espressioni incorporate nei valori letterali XML per creare contenuto in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="65ada-120">Describes how to use embedded expressions in XML literals to create content at run time.</span></span>|  
|[<span data-ttu-id="65ada-121">Nomi di elementi e attributi XML dichiarati</span><span class="sxs-lookup"><span data-stu-id="65ada-121">Names of Declared XML Elements and Attributes</span></span>](../../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)|<span data-ttu-id="65ada-122">Descrive linee guida per la denominazione di elementi e attributi XML.</span><span class="sxs-lookup"><span data-stu-id="65ada-122">Describes guidelines for naming XML elements and attributes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="65ada-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="65ada-123">See also</span></span>

- [<span data-ttu-id="65ada-124">XML</span><span class="sxs-lookup"><span data-stu-id="65ada-124">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
