---
title: Struttura del programma e convenzioni del codice (Visual Basic) | Documenti di Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- coding conventions
- Visual Basic code, coding conventions
- coding conventions, Visual Basic
- programs, structure
- program structure
- naming conventions, Visual Basic
- best practices, coding conventions
- conventions, Visual Basic coding
- Visual Basic code
- programming, Visual Basic coding conventions
ms.assetid: dd9be76f-6944-4e78-ad72-0b6084a3fc13
caps.latest.revision: 21
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: c3a091d64b3c55ad3f1291a635fd499da2dacdc8
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="program-structure-and-code-conventions-visual-basic"></a><span data-ttu-id="c449f-102">Struttura del programma e convenzioni di scrittura del codice (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c449f-102">Program Structure and Code Conventions (Visual Basic)</span></span>
<span data-ttu-id="c449f-103">Questa sezione viene presentata la tipica [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] struttura del programma, fornisce una semplice [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] programma "Hello, World" e vengono illustrati [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] convenzioni del codice.</span><span class="sxs-lookup"><span data-stu-id="c449f-103">This section introduces the typical [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] program structure, provides a simple [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] program, "Hello, World", and discusses [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] code conventions.</span></span> <span data-ttu-id="c449f-104">Convenzioni nel codice vengono forniti suggerimenti che lo stato attivo non logica del programma ma la struttura fisica e l'aspetto.</span><span class="sxs-lookup"><span data-stu-id="c449f-104">Code conventions are suggestions that focus not on a program's logic but on its physical structure and appearance.</span></span> <span data-ttu-id="c449f-105">Seguendo le rende più semplice da leggere, comprendere e gestire il codice.</span><span class="sxs-lookup"><span data-stu-id="c449f-105">Following them makes your code easier to read, understand, and maintain.</span></span> <span data-ttu-id="c449f-106">Convenzioni nel codice possono includere, tra gli altri:</span><span class="sxs-lookup"><span data-stu-id="c449f-106">Code conventions can include, among others:</span></span>  
  
-   <span data-ttu-id="c449f-107">Formati standardizzati per l'assegnazione di etichette e commenti nel codice.</span><span class="sxs-lookup"><span data-stu-id="c449f-107">Standardized formats for labeling and commenting code.</span></span>  
  
-   <span data-ttu-id="c449f-108">Linee guida per la spaziatura, la formattazione e rientri di codice.</span><span class="sxs-lookup"><span data-stu-id="c449f-108">Guidelines for spacing, formatting, and indenting code.</span></span>  
  
-   <span data-ttu-id="c449f-109">Convenzioni di denominazione per gli oggetti, variabili e procedure.</span><span class="sxs-lookup"><span data-stu-id="c449f-109">Naming conventions for objects, variables, and procedures.</span></span>  
  
 <span data-ttu-id="c449f-110">Gli argomenti seguenti presentano una serie di linee guida per la programmazione [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] i programmi, insieme a esempi di corretto utilizzo.</span><span class="sxs-lookup"><span data-stu-id="c449f-110">The following topics present a set of programming guidelines for [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] programs, along with examples of good usage.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c449f-111">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="c449f-111">In This Section</span></span>  
 [<span data-ttu-id="c449f-112">Struttura di un programma Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c449f-112">Structure of a Visual Basic Program</span></span>](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)  
 <span data-ttu-id="c449f-113">Viene fornita una panoramica degli elementi che costituiscono un [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] programma.</span><span class="sxs-lookup"><span data-stu-id="c449f-113">Provides an overview of the elements that make up a [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] program.</span></span>  
  
 [<span data-ttu-id="c449f-114">Routine Main in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c449f-114">Main Procedure in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/main-procedure.md)  
 <span data-ttu-id="c449f-115">Descrive la procedura che viene utilizzato come l'avvio di punto e controllo generale per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c449f-115">Discusses the procedure that serves as the starting point and overall control for your application.</span></span>  
  
 [<span data-ttu-id="c449f-116">Riferimenti e istruzione Imports</span><span class="sxs-lookup"><span data-stu-id="c449f-116">References and the Imports Statement</span></span>](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)  
 <span data-ttu-id="c449f-117">Viene illustrato come fare riferimento agli oggetti in altri assembly.</span><span class="sxs-lookup"><span data-stu-id="c449f-117">Discusses how to reference objects in other assemblies.</span></span>  
  
 [<span data-ttu-id="c449f-118">Spazi dei nomi in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c449f-118">Namespaces in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/namespaces.md)  
 <span data-ttu-id="c449f-119">Viene descritto come gli spazi dei nomi organizzare gli oggetti all'interno di assembly.</span><span class="sxs-lookup"><span data-stu-id="c449f-119">Describes how namespaces organize objects within assemblies.</span></span>  
  
 [<span data-ttu-id="c449f-120">Convenzioni di denominazione di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c449f-120">Visual Basic Naming Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)  
 <span data-ttu-id="c449f-121">Include linee guida generali per la denominazione delle procedure, costanti, variabili, argomenti e gli oggetti.</span><span class="sxs-lookup"><span data-stu-id="c449f-121">Includes general guidelines for naming procedures, constants, variables, arguments, and objects.</span></span>  
  
 [<span data-ttu-id="c449f-122">Convenzioni di codifica di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c449f-122">Visual Basic Coding Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/coding-conventions.md)  
 <span data-ttu-id="c449f-123">Esamina le linee guida utilizzate nello sviluppo di esempi in questa documentazione.</span><span class="sxs-lookup"><span data-stu-id="c449f-123">Reviews the guidelines used in developing the samples in this documentation.</span></span>  
  
 [<span data-ttu-id="c449f-124">Compilazione condizionale</span><span class="sxs-lookup"><span data-stu-id="c449f-124">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)  
 <span data-ttu-id="c449f-125">Viene descritto come compilare determinati blocchi di codice in modo selettivo e impostare il compilatore di ignorare gli altri.</span><span class="sxs-lookup"><span data-stu-id="c449f-125">Describes how to compile particular blocks of code selectively while directing the compiler to ignore others.</span></span>  
  
 [<span data-ttu-id="c449f-126">Procedura: Interrompere e combinare istruzioni nel codice</span><span class="sxs-lookup"><span data-stu-id="c449f-126">How to: Break and Combine Statements in Code</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)  
 <span data-ttu-id="c449f-127">Viene illustrato come suddividere lunghe istruzioni in più righe e combinare istruzioni brevi su una riga.</span><span class="sxs-lookup"><span data-stu-id="c449f-127">Shows how to divide long statements into multiple lines and combine short statements on one line.</span></span>  
  
 [<span data-ttu-id="c449f-128">Procedura: Comprimere e nascondere sezioni di codice</span><span class="sxs-lookup"><span data-stu-id="c449f-128">How to: Collapse and Hide Sections of Code</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-collapse-and-hide-sections-of-code.md)  
 <span data-ttu-id="c449f-129">Viene illustrato come comprimere e nascondere sezioni di codice il [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] editor di codice.</span><span class="sxs-lookup"><span data-stu-id="c449f-129">Shows how to collapse and hide sections of code in the [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] code editor.</span></span>  
  
 [<span data-ttu-id="c449f-130">Procedura: Etichettare le istruzioni</span><span class="sxs-lookup"><span data-stu-id="c449f-130">How to: Label Statements</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md)  
 <span data-ttu-id="c449f-131">Viene illustrato come contrassegnare una riga di codice per identificarla per l'utilizzo con le istruzioni, ad esempio `On Error Goto`.</span><span class="sxs-lookup"><span data-stu-id="c449f-131">Shows how to mark a line of code to identify it for use with statements such as `On Error Goto`.</span></span>  
  
 [<span data-ttu-id="c449f-132">Caratteri speciali nel codice</span><span class="sxs-lookup"><span data-stu-id="c449f-132">Special Characters in Code</span></span>](../../../visual-basic/programming-guide/program-structure/special-characters-in-code.md)  
 <span data-ttu-id="c449f-133">Viene illustrato come e dove utilizzare caratteri non alfabetici e non numerici.</span><span class="sxs-lookup"><span data-stu-id="c449f-133">Shows how and where to use non-numeric and non-alphabetic characters.</span></span>  
  
 [<span data-ttu-id="c449f-134">Commenti nel codice</span><span class="sxs-lookup"><span data-stu-id="c449f-134">Comments in Code</span></span>](../../../visual-basic/programming-guide/program-structure/comments-in-code.md)  
 <span data-ttu-id="c449f-135">Viene descritto come aggiungere commenti descrittivi al codice.</span><span class="sxs-lookup"><span data-stu-id="c449f-135">Discusses how to add descriptive comments to your code.</span></span>  
  
 [<span data-ttu-id="c449f-136">Parole chiave come nomi di elementi nel codice</span><span class="sxs-lookup"><span data-stu-id="c449f-136">Keywords as Element Names in Code</span></span>](../../../visual-basic/programming-guide/program-structure/keywords-as-element-names-in-code.md)  
 <span data-ttu-id="c449f-137">Viene descritto come utilizzare le parentesi quadre (`[]`) per delimitare i nomi delle variabili che sono anche [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] parole chiave.</span><span class="sxs-lookup"><span data-stu-id="c449f-137">Describes how to use brackets (`[]`) to delimit variable names that are also [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] keywords.</span></span>  
  
 [<span data-ttu-id="c449f-138">Me, My, MyBase e MyClass</span><span class="sxs-lookup"><span data-stu-id="c449f-138">Me, My, MyBase, and MyClass</span></span>](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)  
 <span data-ttu-id="c449f-139">Descrive diversi modi per fare riferimento agli elementi di un [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] programma.</span><span class="sxs-lookup"><span data-stu-id="c449f-139">Describes various ways to refer to elements of a [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] program.</span></span>  
  
 [<span data-ttu-id="c449f-140">Limitazioni di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c449f-140">Visual Basic Limitations</span></span>](../../../visual-basic/programming-guide/program-structure/limitations.md)  
 <span data-ttu-id="c449f-141">Viene illustrata la rimozione dei limiti di codifica noti in [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span><span class="sxs-lookup"><span data-stu-id="c449f-141">Discusses the removal of known coding limits within [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="c449f-142">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="c449f-142">Related Sections</span></span>  
 [<span data-ttu-id="c449f-143">Convenzioni tipografiche e di scrittura del codice</span><span class="sxs-lookup"><span data-stu-id="c449f-143">Typographic and Code Conventions</span></span>](../../../visual-basic/language-reference/typographic-and-code-conventions.md)  
 <span data-ttu-id="c449f-144">Vengono illustrate le convenzioni standard per [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span><span class="sxs-lookup"><span data-stu-id="c449f-144">Provides standard coding conventions for [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span>  
  
 <span data-ttu-id="c449f-145">[Writing Code](https://docs.microsoft.com/visualstudio/ide/writing-code-in-the-code-and-text-editor) (Scrittura di codice)</span><span class="sxs-lookup"><span data-stu-id="c449f-145">[Writing Code](https://docs.microsoft.com/visualstudio/ide/writing-code-in-the-code-and-text-editor)</span></span>  
 <span data-ttu-id="c449f-146">Vengono descritte le funzionalità che rendono più semplice per scrivere e gestire il codice.</span><span class="sxs-lookup"><span data-stu-id="c449f-146">Describes features that make it easier for you to write and manage your code.</span></span>
