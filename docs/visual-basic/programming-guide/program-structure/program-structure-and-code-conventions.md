---
title: Struttura del programma e convenzioni di scrittura del codice (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- coding conventions
- Visual Basic code, coding conventions
- coding conventions [Visual Basic], Visual Basic
- programs [Visual Basic], structure
- program structure [Visual Basic]
- naming conventions [Visual Basic], Visual Basic
- best practices [Visual Basic], coding conventions
- conventions [Visual Basic], Visual Basic coding
- Visual Basic code
- programming [Visual Basic], Visual Basic coding conventions
ms.assetid: dd9be76f-6944-4e78-ad72-0b6084a3fc13
ms.openlocfilehash: b79e339ebe81a7228a02837e5c0c23c80a8132e9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61916942"
---
# <a name="program-structure-and-code-conventions-visual-basic"></a><span data-ttu-id="708a1-102">Struttura del programma e convenzioni di scrittura del codice (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="708a1-102">Program Structure and Code Conventions (Visual Basic)</span></span>
<span data-ttu-id="708a1-103">In questa sezione presenta la struttura del programma Visual Basic tipica, offre un semplice programma Visual Basic, "Hello, World" e vengono illustrate le convenzioni di codice Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="708a1-103">This section introduces the typical Visual Basic program structure, provides a simple Visual Basic program, "Hello, World", and discusses Visual Basic code conventions.</span></span> <span data-ttu-id="708a1-104">Convenzioni di codice sono suggerimenti dello stato attivo non sulla logica del programma ma sulla sua struttura fisica e aspetto.</span><span class="sxs-lookup"><span data-stu-id="708a1-104">Code conventions are suggestions that focus not on a program's logic but on its physical structure and appearance.</span></span> <span data-ttu-id="708a1-105">Seguendo queste istruzioni, il codice più facile da leggere, comprendere e gestire.</span><span class="sxs-lookup"><span data-stu-id="708a1-105">Following them makes your code easier to read, understand, and maintain.</span></span> <span data-ttu-id="708a1-106">Convenzioni del codice possono includere, tra gli altri:</span><span class="sxs-lookup"><span data-stu-id="708a1-106">Code conventions can include, among others:</span></span>  
  
- <span data-ttu-id="708a1-107">Formati standardizzati per l'assegnazione di etichette e commenti nel codice.</span><span class="sxs-lookup"><span data-stu-id="708a1-107">Standardized formats for labeling and commenting code.</span></span>  
  
- <span data-ttu-id="708a1-108">Linee guida per la spaziatura, la formattazione e il rientro di codice.</span><span class="sxs-lookup"><span data-stu-id="708a1-108">Guidelines for spacing, formatting, and indenting code.</span></span>  
  
- <span data-ttu-id="708a1-109">Convenzioni di denominazione per oggetti, variabili e le procedure.</span><span class="sxs-lookup"><span data-stu-id="708a1-109">Naming conventions for objects, variables, and procedures.</span></span>  
  
 <span data-ttu-id="708a1-110">Gli argomenti seguenti presentano una serie di linee guida di programmazione per applicazioni Visual Basic, insieme a esempi di corretto utilizzo.</span><span class="sxs-lookup"><span data-stu-id="708a1-110">The following topics present a set of programming guidelines for Visual Basic programs, along with examples of good usage.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="708a1-111">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="708a1-111">In This Section</span></span>  
 [<span data-ttu-id="708a1-112">Struttura di un programma Visual Basic</span><span class="sxs-lookup"><span data-stu-id="708a1-112">Structure of a Visual Basic Program</span></span>](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)  
 <span data-ttu-id="708a1-113">Viene fornita una panoramica degli elementi che costituiscono un programma Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="708a1-113">Provides an overview of the elements that make up a Visual Basic program.</span></span>  
  
 [<span data-ttu-id="708a1-114">Routine Main in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="708a1-114">Main Procedure in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/main-procedure.md)  
 <span data-ttu-id="708a1-115">Viene descritta la routine che viene utilizzato come l'avvio di un punto e controllo generale per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="708a1-115">Discusses the procedure that serves as the starting point and overall control for your application.</span></span>  
  
 [<span data-ttu-id="708a1-116">Riferimenti e istruzione Imports</span><span class="sxs-lookup"><span data-stu-id="708a1-116">References and the Imports Statement</span></span>](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)  
 <span data-ttu-id="708a1-117">Viene illustrato come fare riferimento agli oggetti in altri assembly.</span><span class="sxs-lookup"><span data-stu-id="708a1-117">Discusses how to reference objects in other assemblies.</span></span>  
  
 [<span data-ttu-id="708a1-118">Spazi dei nomi in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="708a1-118">Namespaces in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/namespaces.md)  
 <span data-ttu-id="708a1-119">Descrive come gli spazi dei nomi organizzare gli oggetti all'interno degli assembly.</span><span class="sxs-lookup"><span data-stu-id="708a1-119">Describes how namespaces organize objects within assemblies.</span></span>  
  
 [<span data-ttu-id="708a1-120">Convenzioni di denominazione di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="708a1-120">Visual Basic Naming Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)  
 <span data-ttu-id="708a1-121">Vengono fornite indicazioni generali per la denominazione di routine, costanti, variabili, argomenti e gli oggetti.</span><span class="sxs-lookup"><span data-stu-id="708a1-121">Includes general guidelines for naming procedures, constants, variables, arguments, and objects.</span></span>  
  
 [<span data-ttu-id="708a1-122">Convenzioni di scrittura codice di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="708a1-122">Visual Basic Coding Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/coding-conventions.md)  
 <span data-ttu-id="708a1-123">Esamina le linee guida utilizzate per sviluppare gli esempi in questa documentazione.</span><span class="sxs-lookup"><span data-stu-id="708a1-123">Reviews the guidelines used in developing the samples in this documentation.</span></span>  
  
 [<span data-ttu-id="708a1-124">Compilazione condizionale</span><span class="sxs-lookup"><span data-stu-id="708a1-124">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)  
 <span data-ttu-id="708a1-125">Viene descritto come compilare determinati blocchi di codice in modo selettivo e impostare il compilatore da ignorarne altri.</span><span class="sxs-lookup"><span data-stu-id="708a1-125">Describes how to compile particular blocks of code selectively while directing the compiler to ignore others.</span></span>  
  
 [<span data-ttu-id="708a1-126">Procedura: Interrompere e combinare istruzioni nel codice</span><span class="sxs-lookup"><span data-stu-id="708a1-126">How to: Break and Combine Statements in Code</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)  
 <span data-ttu-id="708a1-127">Viene illustrato come suddividere lunghe istruzioni in più righe e combinare istruzioni brevi su un'unica riga.</span><span class="sxs-lookup"><span data-stu-id="708a1-127">Shows how to divide long statements into multiple lines and combine short statements on one line.</span></span>  
  
 [<span data-ttu-id="708a1-128">Procedura: Comprimere e nascondere sezioni di codice</span><span class="sxs-lookup"><span data-stu-id="708a1-128">How to: Collapse and Hide Sections of Code</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-collapse-and-hide-sections-of-code.md)  
 <span data-ttu-id="708a1-129">Illustra come comprimere e nascondere sezioni di codice in Visual Basic editor di codice.</span><span class="sxs-lookup"><span data-stu-id="708a1-129">Shows how to collapse and hide sections of code in the Visual Basic code editor.</span></span>  
  
 [<span data-ttu-id="708a1-130">Procedura: etichettare le istruzioni</span><span class="sxs-lookup"><span data-stu-id="708a1-130">How to: Label Statements</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md)  
 <span data-ttu-id="708a1-131">Viene illustrato come contrassegnare una riga di codice per facilitarne l'identificazione per l'uso con le istruzioni, ad esempio `On Error Goto`.</span><span class="sxs-lookup"><span data-stu-id="708a1-131">Shows how to mark a line of code to identify it for use with statements such as `On Error Goto`.</span></span>  
  
 [<span data-ttu-id="708a1-132">Caratteri speciali nel codice</span><span class="sxs-lookup"><span data-stu-id="708a1-132">Special Characters in Code</span></span>](../../../visual-basic/programming-guide/program-structure/special-characters-in-code.md)  
 <span data-ttu-id="708a1-133">Viene illustrato come e dove usare caratteri non numerici e non alfabetici.</span><span class="sxs-lookup"><span data-stu-id="708a1-133">Shows how and where to use non-numeric and non-alphabetic characters.</span></span>  
  
 [<span data-ttu-id="708a1-134">Commenti nel codice</span><span class="sxs-lookup"><span data-stu-id="708a1-134">Comments in Code</span></span>](../../../visual-basic/programming-guide/program-structure/comments-in-code.md)  
 <span data-ttu-id="708a1-135">Viene descritto come aggiungere commenti descrittivi al codice.</span><span class="sxs-lookup"><span data-stu-id="708a1-135">Discusses how to add descriptive comments to your code.</span></span>  
  
 [<span data-ttu-id="708a1-136">Parole chiave come nomi di elementi nel codice</span><span class="sxs-lookup"><span data-stu-id="708a1-136">Keywords as Element Names in Code</span></span>](../../../visual-basic/programming-guide/program-structure/keywords-as-element-names-in-code.md)  
 <span data-ttu-id="708a1-137">Viene descritto come utilizzare le parentesi (`[]`) per delimitare i nomi delle variabili che sono anche parole chiave Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="708a1-137">Describes how to use brackets (`[]`) to delimit variable names that are also Visual Basic keywords.</span></span>  
  
 [<span data-ttu-id="708a1-138">Me, My, MyBase e MyClass</span><span class="sxs-lookup"><span data-stu-id="708a1-138">Me, My, MyBase, and MyClass</span></span>](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)  
 <span data-ttu-id="708a1-139">Descrive vari modi per fare riferimento agli elementi di un programma Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="708a1-139">Describes various ways to refer to elements of a Visual Basic program.</span></span>  
  
 [<span data-ttu-id="708a1-140">Limitazioni di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="708a1-140">Visual Basic Limitations</span></span>](../../../visual-basic/programming-guide/program-structure/limitations.md)  
 <span data-ttu-id="708a1-141">Viene illustrata la rimozione dei limiti di codifica noti all'interno di Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="708a1-141">Discusses the removal of known coding limits within Visual Basic.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="708a1-142">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="708a1-142">Related Sections</span></span>  
 [<span data-ttu-id="708a1-143">Convenzioni tipografiche e di scrittura del codice</span><span class="sxs-lookup"><span data-stu-id="708a1-143">Typographic and Code Conventions</span></span>](../../../visual-basic/language-reference/typographic-and-code-conventions.md)  
 <span data-ttu-id="708a1-144">Vengono illustrate le convenzioni standard per Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="708a1-144">Provides standard coding conventions for Visual Basic.</span></span>  
  
 <span data-ttu-id="708a1-145">[Writing Code](/visualstudio/ide/writing-code-in-the-code-and-text-editor) (Scrittura di codice)</span><span class="sxs-lookup"><span data-stu-id="708a1-145">[Writing Code](/visualstudio/ide/writing-code-in-the-code-and-text-editor)</span></span>  
 <span data-ttu-id="708a1-146">Vengono descritte le funzionalità che rendono più semplice per scrivere e gestire il codice.</span><span class="sxs-lookup"><span data-stu-id="708a1-146">Describes features that make it easier for you to write and manage your code.</span></span>
