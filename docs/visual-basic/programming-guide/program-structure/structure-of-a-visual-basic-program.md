---
title: Struttura di un programma Visual Basic | Documenti di Microsoft
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
- conditional compilation, Visual Basic
- program structure, Visual Basic
- procedures, structure
- Visual Basic code, program structure
ms.assetid: ad0c6531-d762-4c77-a700-de16b07b6119
caps.latest.revision: 17
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
ms.openlocfilehash: 3e16ea51d0f766fcb5866cde89e5384a153ac050
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="structure-of-a-visual-basic-program"></a><span data-ttu-id="7b8af-102">Struttura di un programma Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7b8af-102">Structure of a Visual Basic Program</span></span>
<span data-ttu-id="7b8af-103">Oggetto [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] programma è composto da blocchi di compilazione standard.</span><span class="sxs-lookup"><span data-stu-id="7b8af-103">A [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] program is built up from standard building blocks.</span></span> <span data-ttu-id="7b8af-104">Oggetto *soluzione* comprende uno o più progetti.</span><span class="sxs-lookup"><span data-stu-id="7b8af-104">A *solution* comprises one or more projects.</span></span> <span data-ttu-id="7b8af-105">Oggetto *progetto* a sua volta può contenere uno o più assembly.</span><span class="sxs-lookup"><span data-stu-id="7b8af-105">A *project* in turn can contain one or more assemblies.</span></span> <span data-ttu-id="7b8af-106">Ogni *assembly* viene compilato da uno o più file di origine.</span><span class="sxs-lookup"><span data-stu-id="7b8af-106">Each *assembly* is compiled from one or more source files.</span></span> <span data-ttu-id="7b8af-107">Oggetto *file di origine* fornisce la definizione e implementazione di classi, strutture, moduli e interfacce che indirettamente contengono tutto il codice.</span><span class="sxs-lookup"><span data-stu-id="7b8af-107">A *source file* provides the definition and implementation of classes, structures, modules, and interfaces, which ultimately contain all your code.</span></span>  
  
 <span data-ttu-id="7b8af-108">Per ulteriori informazioni su questi blocchi predefiniti di un [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] del programma, vedere [soluzioni e progetti](https://docs.microsoft.com/visualstudio/ide/solutions-and-projects-in-visual-studio) e [assembly e Global Assembly Cache](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md).</span><span class="sxs-lookup"><span data-stu-id="7b8af-108">For more information about these building blocks of a [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] program, see [Solutions and Projects](https://docs.microsoft.com/visualstudio/ide/solutions-and-projects-in-visual-studio) and [Assemblies and the Global Assembly Cache](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md).</span></span>  
  
## <a name="file-level-programming-elements"></a><span data-ttu-id="7b8af-109">Elementi di programmazione a livello di file</span><span class="sxs-lookup"><span data-stu-id="7b8af-109">File-Level Programming Elements</span></span>  
 <span data-ttu-id="7b8af-110">Quando si avvia un progetto o un file e aprire l'editor di codice, viene visualizzato codice già in uso e nell'ordine corretto.</span><span class="sxs-lookup"><span data-stu-id="7b8af-110">When you start a project or file and open the code editor, you see some code already in place and in the correct order.</span></span> <span data-ttu-id="7b8af-111">Qualsiasi codice scritto deve seguire la sequenza seguente:</span><span class="sxs-lookup"><span data-stu-id="7b8af-111">Any code that you write should follow the following sequence:</span></span>  
  
1.  <span data-ttu-id="7b8af-112">`Option`istruzioni</span><span class="sxs-lookup"><span data-stu-id="7b8af-112">`Option` statements</span></span>  
  
2.  <span data-ttu-id="7b8af-113">`Imports`istruzioni</span><span class="sxs-lookup"><span data-stu-id="7b8af-113">`Imports` statements</span></span>  
  
3.  <span data-ttu-id="7b8af-114">`Namespace`istruzioni e gli elementi a livello di spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="7b8af-114">`Namespace` statements and namespace-level elements</span></span>  
  
 <span data-ttu-id="7b8af-115">Se si immette istruzioni in un ordine diverso, possono comportare errori di compilazione.</span><span class="sxs-lookup"><span data-stu-id="7b8af-115">If you enter statements in a different order, compilation errors can result.</span></span>  
  
 <span data-ttu-id="7b8af-116">Un programma può inoltre contenere istruzioni di compilazione condizionale.</span><span class="sxs-lookup"><span data-stu-id="7b8af-116">A program can also contain conditional compilation statements.</span></span> <span data-ttu-id="7b8af-117">È possibile alternare queste nel file di origine tra le istruzioni della sequenza precedente.</span><span class="sxs-lookup"><span data-stu-id="7b8af-117">You can intersperse these in the source file among the statements of the preceding sequence.</span></span>  
  
### <a name="option-statements"></a><span data-ttu-id="7b8af-118">Istruzioni Option</span><span class="sxs-lookup"><span data-stu-id="7b8af-118">Option Statements</span></span>  
 <span data-ttu-id="7b8af-119">`Option`le istruzioni stabiliscono le regole di base per il codice successivo, contribuendo ad evitare errori di sintassi e la logica.</span><span class="sxs-lookup"><span data-stu-id="7b8af-119">`Option` statements establish ground rules for subsequent code, helping prevent syntax and logic errors.</span></span> <span data-ttu-id="7b8af-120">Il [istruzione Option Explicit](../../../visual-basic/language-reference/statements/option-explicit-statement.md) garantisce che tutte le variabili vengono dichiarate e ortografia, riducendo in fase di debug.</span><span class="sxs-lookup"><span data-stu-id="7b8af-120">The [Option Explicit Statement](../../../visual-basic/language-reference/statements/option-explicit-statement.md) ensures that all variables are declared and spelled correctly, which reduces debugging time.</span></span> <span data-ttu-id="7b8af-121">Il [istruzione Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md) consente di ridurre al minimo la logica degli errori e perdita di dati che può verificarsi quando si utilizzano variabili di tipi di dati diversi.</span><span class="sxs-lookup"><span data-stu-id="7b8af-121">The [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md) helps to minimize logic errors and data loss that can occur when you work between variables of different data types.</span></span> <span data-ttu-id="7b8af-122">Il [istruzione Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md) specifica le modalità di stringhe vengono confrontate tra loro, in base a una loro `Binary` o `Text` valori.</span><span class="sxs-lookup"><span data-stu-id="7b8af-122">The [Option Compare Statement](../../../visual-basic/language-reference/statements/option-compare-statement.md) specifies the way strings are compared to each other, based on either their `Binary` or `Text` values.</span></span>  
  
### <a name="imports-statements"></a><span data-ttu-id="7b8af-123">Istruzioni Imports</span><span class="sxs-lookup"><span data-stu-id="7b8af-123">Imports Statements</span></span>  
 <span data-ttu-id="7b8af-124">È possibile includere un [istruzione Imports (tipo e Namespace .NET)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) per importare i nomi definiti all'esterno del progetto.</span><span class="sxs-lookup"><span data-stu-id="7b8af-124">You can include an [Imports Statement (.NET Namespace and Type)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) to import names defined outside your project.</span></span> <span data-ttu-id="7b8af-125">Un `Imports` istruzione consente al codice fare riferimento alle classi e altri tipi definiti nello spazio dei nomi importato, senza la necessità di fornire il nome completo.</span><span class="sxs-lookup"><span data-stu-id="7b8af-125">An `Imports` statement allows your code to refer to classes and other types defined within the imported namespace, without having to qualify them.</span></span> <span data-ttu-id="7b8af-126">È possibile utilizzare il numero `Imports` istruzioni appropriate.</span><span class="sxs-lookup"><span data-stu-id="7b8af-126">You can use as many `Imports` statements as appropriate.</span></span> <span data-ttu-id="7b8af-127">Per ulteriori informazioni, vedere [riferimenti e istruzione Imports](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md).</span><span class="sxs-lookup"><span data-stu-id="7b8af-127">For more information, see [References and the Imports Statement](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md).</span></span>  
  
### <a name="namespace-statements"></a><span data-ttu-id="7b8af-128">Istruzioni Namespace</span><span class="sxs-lookup"><span data-stu-id="7b8af-128">Namespace Statements</span></span>  
 <span data-ttu-id="7b8af-129">Guida di spazi dei nomi organizzare e classificare gli elementi di programmazione per facilitare il raggruppamento e l'accesso.</span><span class="sxs-lookup"><span data-stu-id="7b8af-129">Namespaces help you organize and classify your programming elements for ease of grouping and accessing.</span></span> <span data-ttu-id="7b8af-130">Utilizzare il [istruzione Namespace](../../../visual-basic/language-reference/statements/namespace-statement.md) per classificare le seguenti istruzioni all'interno di un determinato spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="7b8af-130">You use the [Namespace Statement](../../../visual-basic/language-reference/statements/namespace-statement.md) to classify the following statements within a particular namespace.</span></span> <span data-ttu-id="7b8af-131">Per ulteriori informazioni, vedere [spazi dei nomi in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="7b8af-131">For more information, see [Namespaces in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md).</span></span>  
  
### <a name="conditional-compilation-statements"></a><span data-ttu-id="7b8af-132">Istruzioni di compilazione condizionale</span><span class="sxs-lookup"><span data-stu-id="7b8af-132">Conditional Compilation Statements</span></span>  
 <span data-ttu-id="7b8af-133">Istruzioni di compilazione condizionale possono apparire quasi ovunque nel file di origine.</span><span class="sxs-lookup"><span data-stu-id="7b8af-133">Conditional compilation statements can appear almost anywhere in your source file.</span></span> <span data-ttu-id="7b8af-134">Provocano parti del codice per includere o escludere in fase di compilazione in base a determinate condizioni.</span><span class="sxs-lookup"><span data-stu-id="7b8af-134">They cause parts of your code to be included or excluded at compile time depending on certain conditions.</span></span> <span data-ttu-id="7b8af-135">È possibile anche utilizzarli per il debug dell'applicazione, poiché il codice condizionale viene eseguito solo in modalità debug.</span><span class="sxs-lookup"><span data-stu-id="7b8af-135">You can also use them for debugging your application, because conditional code runs in debugging mode only.</span></span> <span data-ttu-id="7b8af-136">Per ulteriori informazioni, vedere [la compilazione condizionale](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md).</span><span class="sxs-lookup"><span data-stu-id="7b8af-136">For more information, see [Conditional Compilation](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md).</span></span>  
  
## <a name="namespace-level-programming-elements"></a><span data-ttu-id="7b8af-137">Elementi di programmazione a livello di Namespace</span><span class="sxs-lookup"><span data-stu-id="7b8af-137">Namespace-Level Programming Elements</span></span>  
 <span data-ttu-id="7b8af-138">Classi, strutture e i moduli contengono tutto il codice nel file di origine.</span><span class="sxs-lookup"><span data-stu-id="7b8af-138">Classes, structures, and modules contain all the code in your source file.</span></span> <span data-ttu-id="7b8af-139">Sono *a livello di spazio dei nomi* elementi che possono essere visualizzate all'interno di uno spazio dei nomi o a livello di file di origine.</span><span class="sxs-lookup"><span data-stu-id="7b8af-139">They are *namespace-level* elements, which can appear within a namespace or at the source file level.</span></span> <span data-ttu-id="7b8af-140">Questi file contengono le dichiarazioni di tutti gli altri elementi di programmazione.</span><span class="sxs-lookup"><span data-stu-id="7b8af-140">They hold the declarations of all other programming elements.</span></span> <span data-ttu-id="7b8af-141">Interfacce che definiscono le firme degli elementi ma non forniscono alcuna implementazione, vengono visualizzati anche a livello di modulo.</span><span class="sxs-lookup"><span data-stu-id="7b8af-141">Interfaces, which define element signatures but provide no implementation, also appear at module level.</span></span> <span data-ttu-id="7b8af-142">Per ulteriori informazioni sugli elementi a livello di modulo, vedere quanto segue:</span><span class="sxs-lookup"><span data-stu-id="7b8af-142">For more information on the module-level elements, see the following:</span></span>  
  
-   [<span data-ttu-id="7b8af-143">Istruzione Class</span><span class="sxs-lookup"><span data-stu-id="7b8af-143">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
-   [<span data-ttu-id="7b8af-144">Istruzione Structure</span><span class="sxs-lookup"><span data-stu-id="7b8af-144">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
-   [<span data-ttu-id="7b8af-145">Istruzione Module</span><span class="sxs-lookup"><span data-stu-id="7b8af-145">Module Statement</span></span>](../../../visual-basic/language-reference/statements/module-statement.md)  
  
-   [<span data-ttu-id="7b8af-146">Istruzione Interface</span><span class="sxs-lookup"><span data-stu-id="7b8af-146">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 <span data-ttu-id="7b8af-147">Gli elementi di dati a livello di spazio dei nomi sono delegati ed enumerazioni.</span><span class="sxs-lookup"><span data-stu-id="7b8af-147">Data elements at namespace level are enumerations and delegates.</span></span>  
  
## <a name="module-level-programming-elements"></a><span data-ttu-id="7b8af-148">Elementi di programmazione a livello di modulo</span><span class="sxs-lookup"><span data-stu-id="7b8af-148">Module-Level Programming Elements</span></span>  
 <span data-ttu-id="7b8af-149">Le procedure, operatori, proprietà ed eventi sono gli unici elementi di programmazione che possono contenere codice eseguibile (istruzioni che eseguono azioni in fase di esecuzione).</span><span class="sxs-lookup"><span data-stu-id="7b8af-149">Procedures, operators, properties, and events are the only programming elements that can hold executable code (statements that perform actions at run time).</span></span> <span data-ttu-id="7b8af-150">Sono il *a livello di modulo* elementi del programma.</span><span class="sxs-lookup"><span data-stu-id="7b8af-150">They are the *module-level* elements of your program.</span></span> <span data-ttu-id="7b8af-151">Per ulteriori informazioni sugli elementi di livello di stored procedure, vedere quanto segue:</span><span class="sxs-lookup"><span data-stu-id="7b8af-151">For more information on the procedure-level elements, see the following:</span></span>  
  
-   [<span data-ttu-id="7b8af-152">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="7b8af-152">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
-   [<span data-ttu-id="7b8af-153">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="7b8af-153">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
-   [<span data-ttu-id="7b8af-154">Istruzione Declare</span><span class="sxs-lookup"><span data-stu-id="7b8af-154">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
-   [<span data-ttu-id="7b8af-155">Istruzione Operator</span><span class="sxs-lookup"><span data-stu-id="7b8af-155">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
-   [<span data-ttu-id="7b8af-156">Istruzione Property</span><span class="sxs-lookup"><span data-stu-id="7b8af-156">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
-   [<span data-ttu-id="7b8af-157">Istruzione Event</span><span class="sxs-lookup"><span data-stu-id="7b8af-157">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 <span data-ttu-id="7b8af-158">Gli elementi di dati a livello di modulo sono variabili, costanti, enumerazioni e delegati.</span><span class="sxs-lookup"><span data-stu-id="7b8af-158">Data elements at module level are variables, constants, enumerations, and delegates.</span></span>  
  
## <a name="procedure-level-programming-elements"></a><span data-ttu-id="7b8af-159">Elementi di programmazione a livello di routine</span><span class="sxs-lookup"><span data-stu-id="7b8af-159">Procedure-Level Programming Elements</span></span>  
 <span data-ttu-id="7b8af-160">La maggior parte dei contenuti di *a livello di routine* gli elementi sono eseguibili che costituiscono il codice in fase di esecuzione del programma.</span><span class="sxs-lookup"><span data-stu-id="7b8af-160">Most of the contents of *procedure-level* elements are executable statements, which constitute the run-time code of your program.</span></span> <span data-ttu-id="7b8af-161">Tutto il codice eseguibile deve essere in una procedura (`Function`, `Sub`, `Operator`, `Get`, `Set`, `AddHandler`, `RemoveHandler`, `RaiseEvent`).</span><span class="sxs-lookup"><span data-stu-id="7b8af-161">All executable code must be in some procedure (`Function`, `Sub`, `Operator`, `Get`, `Set`, `AddHandler`, `RemoveHandler`, `RaiseEvent`).</span></span> <span data-ttu-id="7b8af-162">Per ulteriori informazioni, vedere [istruzioni](../../../visual-basic/programming-guide/language-features/statements.md).</span><span class="sxs-lookup"><span data-stu-id="7b8af-162">For more information, see [Statements](../../../visual-basic/programming-guide/language-features/statements.md).</span></span>  
  
 <span data-ttu-id="7b8af-163">Gli elementi di dati a livello di routine sono limitati a costanti e variabili locali.</span><span class="sxs-lookup"><span data-stu-id="7b8af-163">Data elements at procedure level are limited to local variables and constants.</span></span>  
  
## <a name="the-main-procedure"></a><span data-ttu-id="7b8af-164">La procedura principale</span><span class="sxs-lookup"><span data-stu-id="7b8af-164">The Main Procedure</span></span>  
 <span data-ttu-id="7b8af-165">Il `Main` procedura è la prima parte di codice da eseguire quando l'applicazione è stata caricata.</span><span class="sxs-lookup"><span data-stu-id="7b8af-165">The `Main` procedure is the first code to run when your application has been loaded.</span></span> <span data-ttu-id="7b8af-166">`Main`serve come punto di partenza e controllo generale per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="7b8af-166">`Main` serves as the starting point and overall control for your application.</span></span> <span data-ttu-id="7b8af-167">Esistono quattro tipi di `Main`:</span><span class="sxs-lookup"><span data-stu-id="7b8af-167">There are four varieties of `Main`:</span></span>  
  
-   `Sub Main()`  
  
-   `Sub Main(ByVal cmdArgs() As String)`  
  
-   `Function Main() As Integer`  
  
-   `Function Main(ByVal cmdArgs() As String) As Integer`  
  
 <span data-ttu-id="7b8af-168">Il più comune di questa procedura è `Sub Main()`.</span><span class="sxs-lookup"><span data-stu-id="7b8af-168">The most common variety of this procedure is `Sub Main()`.</span></span> <span data-ttu-id="7b8af-169">Per ulteriori informazioni, vedere [routine Main in Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md).</span><span class="sxs-lookup"><span data-stu-id="7b8af-169">For more information, see [Main Procedure in Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b8af-170">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7b8af-170">See Also</span></span>  
 <span data-ttu-id="7b8af-171">[Routine Main in Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="7b8af-171">[Main Procedure in Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md) </span></span>  
<span data-ttu-id="7b8af-172"> [Convenzioni di denominazione di Visual Basic](../../../visual-basic/programming-guide/program-structure/naming-conventions.md) </span><span class="sxs-lookup"><span data-stu-id="7b8af-172"> [Visual Basic Naming Conventions](../../../visual-basic/programming-guide/program-structure/naming-conventions.md) </span></span>  
<span data-ttu-id="7b8af-173"> [Limitazioni di Visual Basic](../../../visual-basic/programming-guide/program-structure/limitations.md)</span><span class="sxs-lookup"><span data-stu-id="7b8af-173"> [Visual Basic Limitations](../../../visual-basic/programming-guide/program-structure/limitations.md)</span></span>
