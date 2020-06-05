---
title: Struttura del programma e convenzioni di scrittura del codice
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
ms.openlocfilehash: c8d851afc33e7e898ab16abc941d8680f74145e3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84398305"
---
# <a name="program-structure-and-code-conventions-visual-basic"></a><span data-ttu-id="e1ae1-102">Struttura del programma e convenzioni di scrittura del codice (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e1ae1-102">Program Structure and Code Conventions (Visual Basic)</span></span>
<span data-ttu-id="e1ae1-103">In questa sezione viene presentata la tipica struttura del programma Visual Basic, viene fornito un semplice programma di Visual Basic, "Hello, World" e vengono illustrate le convenzioni del codice Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="e1ae1-103">This section introduces the typical Visual Basic program structure, provides a simple Visual Basic program, "Hello, World", and discusses Visual Basic code conventions.</span></span> <span data-ttu-id="e1ae1-104">Le convenzioni del codice sono suggerimenti che non si concentrano sulla logica di un programma, ma sulla struttura fisica e sull'aspetto.</span><span class="sxs-lookup"><span data-stu-id="e1ae1-104">Code conventions are suggestions that focus not on a program's logic but on its physical structure and appearance.</span></span> <span data-ttu-id="e1ae1-105">Il codice che segue semplifica la lettura, la comprensione e la gestione del codice.</span><span class="sxs-lookup"><span data-stu-id="e1ae1-105">Following them makes your code easier to read, understand, and maintain.</span></span> <span data-ttu-id="e1ae1-106">Le convenzioni del codice possono includere, tra le altre:</span><span class="sxs-lookup"><span data-stu-id="e1ae1-106">Code conventions can include, among others:</span></span>  
  
- <span data-ttu-id="e1ae1-107">Formati standardizzati per l'assegnazione di etichette e l'inserimento di commenti nel codice.</span><span class="sxs-lookup"><span data-stu-id="e1ae1-107">Standardized formats for labeling and commenting code.</span></span>  
  
- <span data-ttu-id="e1ae1-108">Linee guida per la spaziatura, la formattazione e il rientro del codice.</span><span class="sxs-lookup"><span data-stu-id="e1ae1-108">Guidelines for spacing, formatting, and indenting code.</span></span>  
  
- <span data-ttu-id="e1ae1-109">Convenzioni di denominazione per oggetti, variabili e procedure.</span><span class="sxs-lookup"><span data-stu-id="e1ae1-109">Naming conventions for objects, variables, and procedures.</span></span>  
  
 <span data-ttu-id="e1ae1-110">Negli argomenti seguenti viene presentata una serie di linee guida di programmazione per Visual Basic programmi, oltre ad esempi di utilizzo corretto.</span><span class="sxs-lookup"><span data-stu-id="e1ae1-110">The following topics present a set of programming guidelines for Visual Basic programs, along with examples of good usage.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e1ae1-111">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="e1ae1-111">In This Section</span></span>  
 [<span data-ttu-id="e1ae1-112">Struttura di un programma Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e1ae1-112">Structure of a Visual Basic Program</span></span>](structure-of-a-visual-basic-program.md)  
 <span data-ttu-id="e1ae1-113">Viene fornita una panoramica degli elementi che costituiscono un programma Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="e1ae1-113">Provides an overview of the elements that make up a Visual Basic program.</span></span>  
  
 [<span data-ttu-id="e1ae1-114">Routine Main in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e1ae1-114">Main Procedure in Visual Basic</span></span>](main-procedure.md)  
 <span data-ttu-id="e1ae1-115">Viene descritta la procedura che funge da punto di partenza e controllo generale per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e1ae1-115">Discusses the procedure that serves as the starting point and overall control for your application.</span></span>  
  
 [<span data-ttu-id="e1ae1-116">Riferimenti e istruzione Imports</span><span class="sxs-lookup"><span data-stu-id="e1ae1-116">References and the Imports Statement</span></span>](references-and-the-imports-statement.md)  
 <span data-ttu-id="e1ae1-117">Viene illustrato come fare riferimento a oggetti in altri assembly.</span><span class="sxs-lookup"><span data-stu-id="e1ae1-117">Discusses how to reference objects in other assemblies.</span></span>  
  
 [<span data-ttu-id="e1ae1-118">Spazi dei nomi in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e1ae1-118">Namespaces in Visual Basic</span></span>](namespaces.md)  
 <span data-ttu-id="e1ae1-119">Viene descritto come gli spazi dei nomi organizzano gli oggetti all'interno degli assembly.</span><span class="sxs-lookup"><span data-stu-id="e1ae1-119">Describes how namespaces organize objects within assemblies.</span></span>  
  
 [<span data-ttu-id="e1ae1-120">Convenzioni di denominazione di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e1ae1-120">Visual Basic Naming Conventions</span></span>](naming-conventions.md)  
 <span data-ttu-id="e1ae1-121">Include linee guida generali per la denominazione di procedure, costanti, variabili, argomenti e oggetti.</span><span class="sxs-lookup"><span data-stu-id="e1ae1-121">Includes general guidelines for naming procedures, constants, variables, arguments, and objects.</span></span>  
  
 [<span data-ttu-id="e1ae1-122">Convenzioni di codifica di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e1ae1-122">Visual Basic Coding Conventions</span></span>](coding-conventions.md)  
 <span data-ttu-id="e1ae1-123">Esamina le linee guida utilizzate per lo sviluppo degli esempi in questa documentazione.</span><span class="sxs-lookup"><span data-stu-id="e1ae1-123">Reviews the guidelines used in developing the samples in this documentation.</span></span>  
  
 [<span data-ttu-id="e1ae1-124">Compilazione condizionale</span><span class="sxs-lookup"><span data-stu-id="e1ae1-124">Conditional Compilation</span></span>](conditional-compilation.md)  
 <span data-ttu-id="e1ae1-125">Viene descritto come compilare in modo selettivo blocchi specifici di codice, indirizzando il compilatore per ignorarne altri.</span><span class="sxs-lookup"><span data-stu-id="e1ae1-125">Describes how to compile particular blocks of code selectively while directing the compiler to ignore others.</span></span>  
  
 [<span data-ttu-id="e1ae1-126">Procedura: Interrompere e combinare istruzioni nel codice</span><span class="sxs-lookup"><span data-stu-id="e1ae1-126">How to: Break and Combine Statements in Code</span></span>](how-to-break-and-combine-statements-in-code.md)  
 <span data-ttu-id="e1ae1-127">Viene illustrato come dividere istruzioni lunghe in più righe e combinare brevi istruzioni in una sola riga.</span><span class="sxs-lookup"><span data-stu-id="e1ae1-127">Shows how to divide long statements into multiple lines and combine short statements on one line.</span></span>  
  
 [<span data-ttu-id="e1ae1-128">Procedura: Comprimere e nascondere sezioni di codice</span><span class="sxs-lookup"><span data-stu-id="e1ae1-128">How to: Collapse and Hide Sections of Code</span></span>](how-to-collapse-and-hide-sections-of-code.md)  
 <span data-ttu-id="e1ae1-129">Viene illustrato come comprimere e nascondere sezioni di codice nell'editor di codice Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="e1ae1-129">Shows how to collapse and hide sections of code in the Visual Basic code editor.</span></span>  
  
 [<span data-ttu-id="e1ae1-130">Procedura: Etichettare le istruzioni</span><span class="sxs-lookup"><span data-stu-id="e1ae1-130">How to: Label Statements</span></span>](how-to-label-statements.md)  
 <span data-ttu-id="e1ae1-131">Viene illustrato come contrassegnare una riga di codice per identificarla per l'utilizzo con istruzioni quali `On Error Goto` .</span><span class="sxs-lookup"><span data-stu-id="e1ae1-131">Shows how to mark a line of code to identify it for use with statements such as `On Error Goto`.</span></span>  
  
 [<span data-ttu-id="e1ae1-132">Caratteri speciali nel codice</span><span class="sxs-lookup"><span data-stu-id="e1ae1-132">Special Characters in Code</span></span>](special-characters-in-code.md)  
 <span data-ttu-id="e1ae1-133">Mostra come e dove usare caratteri non numerici e non alfabetici.</span><span class="sxs-lookup"><span data-stu-id="e1ae1-133">Shows how and where to use non-numeric and non-alphabetic characters.</span></span>  
  
 [<span data-ttu-id="e1ae1-134">Commenti nel codice</span><span class="sxs-lookup"><span data-stu-id="e1ae1-134">Comments in Code</span></span>](comments-in-code.md)  
 <span data-ttu-id="e1ae1-135">Viene illustrato come aggiungere commenti descrittivi al codice.</span><span class="sxs-lookup"><span data-stu-id="e1ae1-135">Discusses how to add descriptive comments to your code.</span></span>  
  
 [<span data-ttu-id="e1ae1-136">Parole chiave come nomi di elementi nel codice</span><span class="sxs-lookup"><span data-stu-id="e1ae1-136">Keywords as Element Names in Code</span></span>](keywords-as-element-names-in-code.md)  
 <span data-ttu-id="e1ae1-137">Viene descritto come utilizzare le parentesi quadre ( `[]` ) per delimitare i nomi delle variabili che sono anche Visual Basic parole chiave.</span><span class="sxs-lookup"><span data-stu-id="e1ae1-137">Describes how to use brackets (`[]`) to delimit variable names that are also Visual Basic keywords.</span></span>  
  
 [<span data-ttu-id="e1ae1-138">Me, My, MyBase e MyClass</span><span class="sxs-lookup"><span data-stu-id="e1ae1-138">Me, My, MyBase, and MyClass</span></span>](me-my-mybase-and-myclass.md)  
 <span data-ttu-id="e1ae1-139">Vengono descritti i vari modi per fare riferimento agli elementi di un programma Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="e1ae1-139">Describes various ways to refer to elements of a Visual Basic program.</span></span>  
  
 [<span data-ttu-id="e1ae1-140">Limitazioni di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e1ae1-140">Visual Basic Limitations</span></span>](limitations.md)  
 <span data-ttu-id="e1ae1-141">Viene illustrata la rimozione dei limiti di codifica noti all'interno Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="e1ae1-141">Discusses the removal of known coding limits within Visual Basic.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="e1ae1-142">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="e1ae1-142">Related Sections</span></span>  
 [<span data-ttu-id="e1ae1-143">Convenzioni tipografiche e di scrittura del codice</span><span class="sxs-lookup"><span data-stu-id="e1ae1-143">Typographic and Code Conventions</span></span>](../../language-reference/typographic-and-code-conventions.md)  
 <span data-ttu-id="e1ae1-144">Fornisce le convenzioni di codifica standard per Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="e1ae1-144">Provides standard coding conventions for Visual Basic.</span></span>  
  
 [<span data-ttu-id="e1ae1-145">Scrittura di codice</span><span class="sxs-lookup"><span data-stu-id="e1ae1-145">Writing Code</span></span>](/visualstudio/ide/writing-code-in-the-code-and-text-editor)  
 <span data-ttu-id="e1ae1-146">Descrive le funzionalità che semplificano la scrittura e la gestione del codice.</span><span class="sxs-lookup"><span data-stu-id="e1ae1-146">Describes features that make it easier for you to write and manage your code.</span></span>
