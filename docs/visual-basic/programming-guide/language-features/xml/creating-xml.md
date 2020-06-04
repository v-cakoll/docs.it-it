---
title: Creazione di XML
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], creating
- LINQ to XML [Visual Basic], creating XML
- XML literals [Visual Basic], creating
ms.assetid: 8ae29ec5-e5fb-4137-9df5-60a288df7045
ms.openlocfilehash: 0777b428d651c09d4bfb9789ab7b2ac8e74cc32e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410283"
---
# <a name="creating-xml-in-visual-basic"></a><span data-ttu-id="68929-102">Creazione di XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="68929-102">Creating XML in Visual Basic</span></span>
<span data-ttu-id="68929-103">Visual Basic consente di usare i *valori letterali XML* direttamente nel codice.</span><span class="sxs-lookup"><span data-stu-id="68929-103">Visual Basic enables you to use *XML literals* directly in your code.</span></span> <span data-ttu-id="68929-104">La sintassi dei valori letterali XML rappresenta [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] oggetti ed è simile alla sintassi xml 1,0.</span><span class="sxs-lookup"><span data-stu-id="68929-104">The XML literal syntax represents [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objects, and it is similar to the XML 1.0 syntax.</span></span> <span data-ttu-id="68929-105">In questo modo è più semplice creare elementi, documenti e frammenti XML a livello di codice, perché il codice ha la stessa struttura del codice XML finale.</span><span class="sxs-lookup"><span data-stu-id="68929-105">This makes it easier to create XML elements, documents, and fragments programmatically because your code has the same structure as the final XML.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="68929-106">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="68929-106">In This Section</span></span>  
  
|<span data-ttu-id="68929-107">Termine</span><span class="sxs-lookup"><span data-stu-id="68929-107">Term</span></span>|<span data-ttu-id="68929-108">Definizione</span><span class="sxs-lookup"><span data-stu-id="68929-108">Definition</span></span>|  
|---|---|  
|[<span data-ttu-id="68929-109">Cenni preliminari sui valori letterali XML</span><span class="sxs-lookup"><span data-stu-id="68929-109">XML Literals Overview</span></span>](xml-literals-overview.md)|<span data-ttu-id="68929-110">Introduzione ai valori letterali XML e al modo in cui sono correlati [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="68929-110">Introduction to XML literals and how they relate to [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span></span>|  
|[<span data-ttu-id="68929-111">Espressioni incorporate in XML</span><span class="sxs-lookup"><span data-stu-id="68929-111">Embedded Expressions in XML</span></span>](embedded-expressions-in-xml.md)|<span data-ttu-id="68929-112">Viene descritto come utilizzare le espressioni incorporate nei valori letterali XML.</span><span class="sxs-lookup"><span data-stu-id="68929-112">Describes how to use embedded expressions in XML literals.</span></span>|  
|[<span data-ttu-id="68929-113">Procedura: Creare valori letterali XML</span><span class="sxs-lookup"><span data-stu-id="68929-113">How to: Create XML Literals</span></span>](how-to-create-xml-literals.md)|<span data-ttu-id="68929-114">Viene descritto come creare un elemento XML nel codice usando un valore letterale XML.</span><span class="sxs-lookup"><span data-stu-id="68929-114">Describes how to create an XML element in code by using an XML literal.</span></span>|  
|[<span data-ttu-id="68929-115">Spazi vuoti nei valori letterali XML</span><span class="sxs-lookup"><span data-stu-id="68929-115">White Space in XML Literals</span></span>](white-space-in-xml-literals.md)|<span data-ttu-id="68929-116">Viene descritto il modo in cui Visual Basic considera gli spazi vuoti nei valori letterali XML.</span><span class="sxs-lookup"><span data-stu-id="68929-116">Describes how Visual Basic treats white space in XML literals.</span></span>|  
|[<span data-ttu-id="68929-117">Valori letterali XML e specifica XML 1.0</span><span class="sxs-lookup"><span data-stu-id="68929-117">XML Literals and the XML 1.0 Specification</span></span>](xml-literals-and-the-xml-1-0-specification.md)|<span data-ttu-id="68929-118">Viene descritto il modo in cui la sintassi dei valori letterali XML in Visual Basic è correlata alla specifica XML 1,0.</span><span class="sxs-lookup"><span data-stu-id="68929-118">Describes how the XML literal syntax in Visual Basic relates to the XML 1.0 specification.</span></span>|  
|[<span data-ttu-id="68929-119">Procedura: incorporare espressioni nei valori letterali XML</span><span class="sxs-lookup"><span data-stu-id="68929-119">How to: Embed Expressions in XML Literals</span></span>](how-to-embed-expressions-in-xml-literals.md)|<span data-ttu-id="68929-120">Viene descritto come utilizzare le espressioni incorporate nei valori letterali XML per creare contenuto in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="68929-120">Describes how to use embedded expressions in XML literals to create content at run time.</span></span>|  
|[<span data-ttu-id="68929-121">Nomi di elementi e attributi XML dichiarati</span><span class="sxs-lookup"><span data-stu-id="68929-121">Names of Declared XML Elements and Attributes</span></span>](names-of-declared-xml-elements-and-attributes.md)|<span data-ttu-id="68929-122">Vengono descritte le linee guida per la denominazione di elementi e attributi XML.</span><span class="sxs-lookup"><span data-stu-id="68929-122">Describes guidelines for naming XML elements and attributes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="68929-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="68929-123">See also</span></span>

- [<span data-ttu-id="68929-124">XML</span><span class="sxs-lookup"><span data-stu-id="68929-124">XML</span></span>](index.md)
