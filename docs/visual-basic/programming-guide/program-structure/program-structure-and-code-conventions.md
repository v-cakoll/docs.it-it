---
title: Struttura del programma e convenzioni di scrittura del codice (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
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
caps.latest.revision: 21
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9980a815d83b21214f1be441d641c3da38c1b541
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="program-structure-and-code-conventions-visual-basic"></a><span data-ttu-id="f20a7-102">Struttura del programma e convenzioni di scrittura del codice (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f20a7-102">Program Structure and Code Conventions (Visual Basic)</span></span>
<span data-ttu-id="f20a7-103">In questa sezione presenta la struttura del programma Visual Basic tipico, fornisce un semplice programma Visual Basic, "Hello, World" e vengono illustrate le convenzioni di codice Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="f20a7-103">This section introduces the typical Visual Basic program structure, provides a simple Visual Basic program, "Hello, World", and discusses Visual Basic code conventions.</span></span> <span data-ttu-id="f20a7-104">Convenzioni nel codice vengono forniti suggerimenti che lo stato attivo non logica del programma ma la struttura fisica e l'aspetto.</span><span class="sxs-lookup"><span data-stu-id="f20a7-104">Code conventions are suggestions that focus not on a program's logic but on its physical structure and appearance.</span></span> <span data-ttu-id="f20a7-105">Seguito li rende più facile da leggere, comprendere e gestire il codice.</span><span class="sxs-lookup"><span data-stu-id="f20a7-105">Following them makes your code easier to read, understand, and maintain.</span></span> <span data-ttu-id="f20a7-106">Convenzioni nel codice possono includere, tra gli altri:</span><span class="sxs-lookup"><span data-stu-id="f20a7-106">Code conventions can include, among others:</span></span>  
  
-   <span data-ttu-id="f20a7-107">Formati standard per l'assegnazione di etichette e commenti nel codice.</span><span class="sxs-lookup"><span data-stu-id="f20a7-107">Standardized formats for labeling and commenting code.</span></span>  
  
-   <span data-ttu-id="f20a7-108">Linee guida per la spaziatura, la formattazione e il rientro di codice.</span><span class="sxs-lookup"><span data-stu-id="f20a7-108">Guidelines for spacing, formatting, and indenting code.</span></span>  
  
-   <span data-ttu-id="f20a7-109">Convenzioni di denominazione per oggetti, variabili e procedure.</span><span class="sxs-lookup"><span data-stu-id="f20a7-109">Naming conventions for objects, variables, and procedures.</span></span>  
  
 <span data-ttu-id="f20a7-110">Gli argomenti seguenti presentano una serie di linee guida di programmazione per programmi Visual Basic, insieme a esempi di utilizzo ottima.</span><span class="sxs-lookup"><span data-stu-id="f20a7-110">The following topics present a set of programming guidelines for Visual Basic programs, along with examples of good usage.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f20a7-111">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="f20a7-111">In This Section</span></span>  
 [<span data-ttu-id="f20a7-112">Struttura di un programma Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f20a7-112">Structure of a Visual Basic Program</span></span>](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)  
 <span data-ttu-id="f20a7-113">Viene fornita una panoramica degli elementi che costituiscono un programma Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="f20a7-113">Provides an overview of the elements that make up a Visual Basic program.</span></span>  
  
 [<span data-ttu-id="f20a7-114">Routine Main in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f20a7-114">Main Procedure in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/main-procedure.md)  
 <span data-ttu-id="f20a7-115">Descrive la procedura che serve come l'avvio di un punto e controllano generale per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f20a7-115">Discusses the procedure that serves as the starting point and overall control for your application.</span></span>  
  
 [<span data-ttu-id="f20a7-116">Riferimenti e istruzione Imports</span><span class="sxs-lookup"><span data-stu-id="f20a7-116">References and the Imports Statement</span></span>](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)  
 <span data-ttu-id="f20a7-117">Viene illustrato come fare riferimento a oggetti in altri assembly.</span><span class="sxs-lookup"><span data-stu-id="f20a7-117">Discusses how to reference objects in other assemblies.</span></span>  
  
 [<span data-ttu-id="f20a7-118">Spazi dei nomi in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f20a7-118">Namespaces in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/namespaces.md)  
 <span data-ttu-id="f20a7-119">Viene descritto come gli spazi dei nomi organizzare gli oggetti all'interno di assembly.</span><span class="sxs-lookup"><span data-stu-id="f20a7-119">Describes how namespaces organize objects within assemblies.</span></span>  
  
 [<span data-ttu-id="f20a7-120">Convenzioni di denominazione di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f20a7-120">Visual Basic Naming Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)  
 <span data-ttu-id="f20a7-121">Include linee guida generali per la denominazione delle procedure, costanti, variabili, argomenti e gli oggetti.</span><span class="sxs-lookup"><span data-stu-id="f20a7-121">Includes general guidelines for naming procedures, constants, variables, arguments, and objects.</span></span>  
  
 [<span data-ttu-id="f20a7-122">Convenzioni di scrittura codice di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f20a7-122">Visual Basic Coding Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/coding-conventions.md)  
 <span data-ttu-id="f20a7-123">Esamina le linee guida utilizzate nello sviluppo di campioni in questa documentazione.</span><span class="sxs-lookup"><span data-stu-id="f20a7-123">Reviews the guidelines used in developing the samples in this documentation.</span></span>  
  
 [<span data-ttu-id="f20a7-124">Compilazione condizionale</span><span class="sxs-lookup"><span data-stu-id="f20a7-124">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)  
 <span data-ttu-id="f20a7-125">Viene descritto come compilare determinati blocchi di codice in modo selettivo e indirizza al compilatore di ignorare gli altri.</span><span class="sxs-lookup"><span data-stu-id="f20a7-125">Describes how to compile particular blocks of code selectively while directing the compiler to ignore others.</span></span>  
  
 [<span data-ttu-id="f20a7-126">Procedura: Interrompere e combinare istruzioni nel codice</span><span class="sxs-lookup"><span data-stu-id="f20a7-126">How to: Break and Combine Statements in Code</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)  
 <span data-ttu-id="f20a7-127">Viene illustrato come suddividere lunghe istruzioni in più righe e combinare istruzioni brevi su una riga.</span><span class="sxs-lookup"><span data-stu-id="f20a7-127">Shows how to divide long statements into multiple lines and combine short statements on one line.</span></span>  
  
 [<span data-ttu-id="f20a7-128">Procedura: Comprimere e nascondere sezioni di codice</span><span class="sxs-lookup"><span data-stu-id="f20a7-128">How to: Collapse and Hide Sections of Code</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-collapse-and-hide-sections-of-code.md)  
 <span data-ttu-id="f20a7-129">Viene illustrato come comprimere e nascondere sezioni di codice in Visual Basic editor di codice.</span><span class="sxs-lookup"><span data-stu-id="f20a7-129">Shows how to collapse and hide sections of code in the Visual Basic code editor.</span></span>  
  
 [<span data-ttu-id="f20a7-130">Procedura: Etichettare le istruzioni</span><span class="sxs-lookup"><span data-stu-id="f20a7-130">How to: Label Statements</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md)  
 <span data-ttu-id="f20a7-131">Viene illustrato come contrassegnare una riga di codice per facilitarne l'identificazione per l'utilizzo con le istruzioni, ad esempio `On Error Goto`.</span><span class="sxs-lookup"><span data-stu-id="f20a7-131">Shows how to mark a line of code to identify it for use with statements such as `On Error Goto`.</span></span>  
  
 [<span data-ttu-id="f20a7-132">Caratteri speciali nel codice</span><span class="sxs-lookup"><span data-stu-id="f20a7-132">Special Characters in Code</span></span>](../../../visual-basic/programming-guide/program-structure/special-characters-in-code.md)  
 <span data-ttu-id="f20a7-133">Viene illustrato come e dove per utilizzare caratteri non alfabetici non numerico.</span><span class="sxs-lookup"><span data-stu-id="f20a7-133">Shows how and where to use non-numeric and non-alphabetic characters.</span></span>  
  
 [<span data-ttu-id="f20a7-134">Commenti nel codice</span><span class="sxs-lookup"><span data-stu-id="f20a7-134">Comments in Code</span></span>](../../../visual-basic/programming-guide/program-structure/comments-in-code.md)  
 <span data-ttu-id="f20a7-135">Viene descritto come aggiungere commenti descrittivi al codice.</span><span class="sxs-lookup"><span data-stu-id="f20a7-135">Discusses how to add descriptive comments to your code.</span></span>  
  
 [<span data-ttu-id="f20a7-136">Parole chiave come nomi di elementi nel codice</span><span class="sxs-lookup"><span data-stu-id="f20a7-136">Keywords as Element Names in Code</span></span>](../../../visual-basic/programming-guide/program-structure/keywords-as-element-names-in-code.md)  
 <span data-ttu-id="f20a7-137">Viene descritto come utilizzare le parentesi quadre (`[]`) per delimitare i nomi delle variabili che sono anche parole chiave di Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="f20a7-137">Describes how to use brackets (`[]`) to delimit variable names that are also Visual Basic keywords.</span></span>  
  
 [<span data-ttu-id="f20a7-138">Me, My, MyBase e MyClass</span><span class="sxs-lookup"><span data-stu-id="f20a7-138">Me, My, MyBase, and MyClass</span></span>](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)  
 <span data-ttu-id="f20a7-139">Descrive diversi modi per fare riferimento agli elementi di un programma Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="f20a7-139">Describes various ways to refer to elements of a Visual Basic program.</span></span>  
  
 [<span data-ttu-id="f20a7-140">Limitazioni di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f20a7-140">Visual Basic Limitations</span></span>](../../../visual-basic/programming-guide/program-structure/limitations.md)  
 <span data-ttu-id="f20a7-141">Viene illustrata la rimozione dei limiti di codifica noti in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="f20a7-141">Discusses the removal of known coding limits within Visual Basic.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="f20a7-142">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="f20a7-142">Related Sections</span></span>  
 [<span data-ttu-id="f20a7-143">Convenzioni tipografiche e di scrittura del codice</span><span class="sxs-lookup"><span data-stu-id="f20a7-143">Typographic and Code Conventions</span></span>](../../../visual-basic/language-reference/typographic-and-code-conventions.md)  
 <span data-ttu-id="f20a7-144">Vengono illustrate le convenzioni standard per Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="f20a7-144">Provides standard coding conventions for Visual Basic.</span></span>  
  
 <span data-ttu-id="f20a7-145">[Writing Code](/visualstudio/ide/writing-code-in-the-code-and-text-editor) (Scrittura di codice)</span><span class="sxs-lookup"><span data-stu-id="f20a7-145">[Writing Code](/visualstudio/ide/writing-code-in-the-code-and-text-editor)</span></span>  
 <span data-ttu-id="f20a7-146">Descrive le funzionalità che rendono più semplice per scrivere e gestire il codice.</span><span class="sxs-lookup"><span data-stu-id="f20a7-146">Describes features that make it easier for you to write and manage your code.</span></span>
