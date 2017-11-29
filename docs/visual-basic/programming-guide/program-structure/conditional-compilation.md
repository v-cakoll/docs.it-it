---
title: Compilazione condizionale in Visual Basic
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- conditional compilation [Visual Basic], about conditional compilation
- compilation [Visual Basic], conditional
ms.assetid: 9c35e55e-7eee-44fb-a586-dad1f1884848
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 559380dc9baceb2fba4dca782e83f335f1bcd92d
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="conditional-compilation-in-visual-basic"></a><span data-ttu-id="93ea5-102">Compilazione condizionale in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="93ea5-102">Conditional Compilation in Visual Basic</span></span>
<span data-ttu-id="93ea5-103">In *compilazione condizionale*, determinati blocchi di codice in un programma vengono compilati in modo selettivo, mentre gli altri vengono ignorati.</span><span class="sxs-lookup"><span data-stu-id="93ea5-103">In *conditional compilation*, particular blocks of code in a program are compiled selectively while others are ignored.</span></span>  
  
 <span data-ttu-id="93ea5-104">Ad esempio, è possibile scrivere il debug di istruzioni che confrontano la velocità di diversi approcci per la stessa attività di programmazione o si desidera localizzare un'applicazione in più lingue.</span><span class="sxs-lookup"><span data-stu-id="93ea5-104">For example, you may want to write debugging statements that compare the speed of different approaches to the same programming task, or you may want to localize an application for multiple languages.</span></span> <span data-ttu-id="93ea5-105">Le istruzioni di compilazione condizionale sono progettate per l'esecuzione durante la fase di compilazione, non in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="93ea5-105">Conditional compilation statements are designed to run during compile time, not at run time.</span></span>  
  
 <span data-ttu-id="93ea5-106">Per indicare i blocchi di codice da compilare in modo condizionale con il `#If...Then...#Else` direttiva.</span><span class="sxs-lookup"><span data-stu-id="93ea5-106">You denote blocks of code to be conditionally compiled with the `#If...Then...#Else` directive.</span></span> <span data-ttu-id="93ea5-107">Ad esempio, francese e tedesco creare versioni della stessa applicazione dallo stesso codice sorgente, incorporare per segmenti di codice specifico della piattaforma in `#If...Then` istruzioni che utilizzano costanti predefinite `FrenchVersion` e `GermanVersion`.</span><span class="sxs-lookup"><span data-stu-id="93ea5-107">For example, to create French- and German-language versions of the same application from the same source code, you embed platform-specific code segments in `#If...Then` statements using the predefined constants `FrenchVersion` and `GermanVersion`.</span></span> <span data-ttu-id="93ea5-108">Nell'esempio seguente viene illustrato come:</span><span class="sxs-lookup"><span data-stu-id="93ea5-108">The following example demonstrates how:</span></span>  
  
 [!code-vb[VbVbalrConditionalComp#5](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/conditional-compilation_1.vb)]  
  
 <span data-ttu-id="93ea5-109">Se si imposta il valore di `FrenchVersion` costante di compilazione condizionale a `True` in fase di compilazione, viene compilato il codice condizionale per la versione francese.</span><span class="sxs-lookup"><span data-stu-id="93ea5-109">If you set the value of the `FrenchVersion` conditional compilation constant to `True` at compile time, the conditional code for the French version is compiled.</span></span> <span data-ttu-id="93ea5-110">Se si imposta il valore di `GermanVersion` costante da `True`, il compilatore utilizza la versione tedesca.</span><span class="sxs-lookup"><span data-stu-id="93ea5-110">If you set the value of the `GermanVersion` constant to `True`, the compiler uses the German version.</span></span> <span data-ttu-id="93ea5-111">Se non è impostata su `True`, il codice negli ultimi `Else` blocco viene eseguito.</span><span class="sxs-lookup"><span data-stu-id="93ea5-111">If neither is set to `True`, the code in the last `Else` block runs.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="93ea5-112">Completamento automatico verrà non funziona quando la modifica del codice e l'utilizzo di direttive di compilazione condizionale se il codice non fa parte del ramo corrente.</span><span class="sxs-lookup"><span data-stu-id="93ea5-112">Autocompletion will not function when editing code and using conditional compilation directives if the code is not part of the current branch.</span></span>  
  
## <a name="declaring-conditional-compilation-constants"></a><span data-ttu-id="93ea5-113">Dichiarazione di costanti di compilazione condizionale</span><span class="sxs-lookup"><span data-stu-id="93ea5-113">Declaring Conditional Compilation Constants</span></span>  
 <span data-ttu-id="93ea5-114">È possibile impostare le costanti di compilazione condizionale in uno dei tre modi:</span><span class="sxs-lookup"><span data-stu-id="93ea5-114">You can set conditional compilation constants in one of three ways:</span></span>  
  
-   <span data-ttu-id="93ea5-115">Nel **Progettazione progetti**</span><span class="sxs-lookup"><span data-stu-id="93ea5-115">In the **Project Designer**</span></span>  
  
-   <span data-ttu-id="93ea5-116">Nella riga di comando quando si utilizza il compilatore della riga di comando</span><span class="sxs-lookup"><span data-stu-id="93ea5-116">At the command line when using the command-line compiler</span></span>  
  
-   <span data-ttu-id="93ea5-117">Nel codice</span><span class="sxs-lookup"><span data-stu-id="93ea5-117">In your code</span></span>  
  
 <span data-ttu-id="93ea5-118">Costanti di compilazione condizionale hanno un ambito speciale e non sono accessibili dal codice standard.</span><span class="sxs-lookup"><span data-stu-id="93ea5-118">Conditional compilation constants have a special scope and cannot be accessed from standard code.</span></span> <span data-ttu-id="93ea5-119">L'ambito di una costante di compilazione condizionale dipende dal modo in cui è impostata.</span><span class="sxs-lookup"><span data-stu-id="93ea5-119">The scope of a conditional compilation constant is dependent on the way it is set.</span></span> <span data-ttu-id="93ea5-120">La tabella seguente elenca l'ambito delle costanti dichiarate utilizzando ciascuna delle tre modalità menzionate sopra.</span><span class="sxs-lookup"><span data-stu-id="93ea5-120">The following table lists the scope of constants declared using each of the three ways mentioned above.</span></span>  
  
|<span data-ttu-id="93ea5-121">Configurazione (costante)</span><span class="sxs-lookup"><span data-stu-id="93ea5-121">How constant is set</span></span>|<span data-ttu-id="93ea5-122">Ambito di costante</span><span class="sxs-lookup"><span data-stu-id="93ea5-122">Scope of constant</span></span>|  
|---|---|  
|<span data-ttu-id="93ea5-123">**Progettazione progetti**</span><span class="sxs-lookup"><span data-stu-id="93ea5-123">**Project Designer**</span></span>|<span data-ttu-id="93ea5-124">Pubblica a tutti i file nel progetto</span><span class="sxs-lookup"><span data-stu-id="93ea5-124">Public to all files in the project</span></span>|  
|<span data-ttu-id="93ea5-125">Riga di comando</span><span class="sxs-lookup"><span data-stu-id="93ea5-125">Command line</span></span>|<span data-ttu-id="93ea5-126">Pubblica a tutti i file passati al compilatore da riga di comando</span><span class="sxs-lookup"><span data-stu-id="93ea5-126">Public to all files passed to the command-line compiler</span></span>|  
|<span data-ttu-id="93ea5-127">`#Const`istruzione nel codice</span><span class="sxs-lookup"><span data-stu-id="93ea5-127">`#Const` statement in code</span></span>|<span data-ttu-id="93ea5-128">Private per il file in cui è dichiarato</span><span class="sxs-lookup"><span data-stu-id="93ea5-128">Private to the file in which it is declared</span></span>|  
  
|<span data-ttu-id="93ea5-129">Per impostare le costanti in Progettazione progetti</span><span class="sxs-lookup"><span data-stu-id="93ea5-129">To set constants in the Project Designer</span></span>|  
|---|  
|<span data-ttu-id="93ea5-130">-Prima di creare il file eseguibile, impostare le costanti **progettazione** seguendo i passaggi forniti nella [gestione dei progetti e le proprietà di soluzione](/visualstudio/ide/managing-project-and-solution-properties).</span><span class="sxs-lookup"><span data-stu-id="93ea5-130">-   Before creating your executable file, set constants in the **Project Designer** by following the steps provided in [Managing Project and Solution Properties](/visualstudio/ide/managing-project-and-solution-properties).</span></span>|  
  
|<span data-ttu-id="93ea5-131">Per impostare le costanti nella riga di comando</span><span class="sxs-lookup"><span data-stu-id="93ea5-131">To set constants at the command line</span></span>|  
|---|  
|<span data-ttu-id="93ea5-132">-Utilizzare il **/d** commutatore per inserire le costanti di compilazione condizionale, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="93ea5-132">-   Use the **/d** switch to enter conditional compilation constants, as in the following example:</span></span><br />     `vbc MyProj.vb /d:conFrenchVersion=–1:conANSI=0`<br />     <span data-ttu-id="93ea5-133">Non è necessario tra spazio il **/d** commutatore e la prima costante.</span><span class="sxs-lookup"><span data-stu-id="93ea5-133">No space is required between the **/d** switch and the first constant.</span></span> <span data-ttu-id="93ea5-134">Per ulteriori informazioni, vedere [/define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md).</span><span class="sxs-lookup"><span data-stu-id="93ea5-134">For more information, see [/define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md).</span></span><br />     <span data-ttu-id="93ea5-135">Le dichiarazioni della riga di comando eseguire l'override delle dichiarazioni inserite nella **progettazione**, ma non le cancellano.</span><span class="sxs-lookup"><span data-stu-id="93ea5-135">Command-line declarations override declarations entered in the **Project Designer**, but do not erase them.</span></span> <span data-ttu-id="93ea5-136">Impostare gli argomenti **progettazione** rimangono valide per le compilazioni successive.</span><span class="sxs-lookup"><span data-stu-id="93ea5-136">Arguments set in **Project Designer** remain in effect for subsequent compilations.</span></span><br />     <span data-ttu-id="93ea5-137">Quando si scrivono costanti nel codice stesso, non esistono strict regole per il posizionamento, poiché l'ambito è l'intero modulo in cui sono dichiarati.</span><span class="sxs-lookup"><span data-stu-id="93ea5-137">When writing constants in the code itself, there are no strict rules as to their placement, since their scope is the entire module in which they are declared.</span></span>|  
  
|<span data-ttu-id="93ea5-138">Per impostare le costanti nel codice</span><span class="sxs-lookup"><span data-stu-id="93ea5-138">To set constants in your code</span></span>|  
|---|  
|<span data-ttu-id="93ea5-139">-Inserire le costanti nel blocco di dichiarazione del modulo in cui vengono utilizzati.</span><span class="sxs-lookup"><span data-stu-id="93ea5-139">-   Place the constants in the declaration block of the module in which they are used.</span></span> <span data-ttu-id="93ea5-140">Consente di mantenere il codice organizzati e facili da leggere.</span><span class="sxs-lookup"><span data-stu-id="93ea5-140">This helps keep your code organized and easier to read.</span></span>|  
  
## <a name="related-topics"></a><span data-ttu-id="93ea5-141">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="93ea5-141">Related Topics</span></span>  
  
|<span data-ttu-id="93ea5-142">Titolo</span><span class="sxs-lookup"><span data-stu-id="93ea5-142">Title</span></span>|<span data-ttu-id="93ea5-143">Descrizione</span><span class="sxs-lookup"><span data-stu-id="93ea5-143">Description</span></span>|  
|---|---|  
|[<span data-ttu-id="93ea5-144">Struttura del programma e convenzioni di scrittura del codice</span><span class="sxs-lookup"><span data-stu-id="93ea5-144">Program Structure and Code Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)|<span data-ttu-id="93ea5-145">Vengono forniti suggerimenti per rendere il codice facili da leggere e gestire.</span><span class="sxs-lookup"><span data-stu-id="93ea5-145">Provides suggestions for making your code easy to read and maintain.</span></span>|  
  
## <a name="reference"></a><span data-ttu-id="93ea5-146">Riferimento</span><span class="sxs-lookup"><span data-stu-id="93ea5-146">Reference</span></span>  
 [<span data-ttu-id="93ea5-147">Direttiva #Const</span><span class="sxs-lookup"><span data-stu-id="93ea5-147">#Const Directive</span></span>](../../../visual-basic/language-reference/directives/const-directive.md)  
  
 [<span data-ttu-id="93ea5-148">Direttive #If...Then...#Else</span><span class="sxs-lookup"><span data-stu-id="93ea5-148">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)  
  
 [<span data-ttu-id="93ea5-149">/define (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="93ea5-149">/define (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/define.md)
