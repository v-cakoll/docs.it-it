---
title: Convenzioni di codifica C# (Guida per programmatori C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- coding conventions, C#
- Visual C#, coding conventions
- C# language, coding conventions
ms.assetid: f4f60de9-d49b-4fb6-bab1-20e19ea24710
caps.latest.revision: 32
author: BillWagner
ms.author: wiwagn
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 9f32fdc0eb1954cdac30c39e05c74d43301d850c
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="c-coding-conventions-c-programming-guide"></a><span data-ttu-id="03b41-102">Convenzioni di codifica C# (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="03b41-102">C# Coding Conventions (C# Programming Guide)</span></span>
<span data-ttu-id="03b41-103">La [specifica del linguaggio C#](http://go.microsoft.com/fwlink/?LinkId=199552) non definisce uno standard di codifica.</span><span class="sxs-lookup"><span data-stu-id="03b41-103">The [C# Language Specification](http://go.microsoft.com/fwlink/?LinkId=199552) does not define a coding standard.</span></span> <span data-ttu-id="03b41-104">Tuttavia, le linee guida riportate in questo argomento vengono usate da Microsoft per sviluppare gli esempi e la documentazione.</span><span class="sxs-lookup"><span data-stu-id="03b41-104">However, the guidelines in this topic are used by Microsoft to develop samples and documentation.</span></span>  
  
 <span data-ttu-id="03b41-105">Le convenzioni di codifica hanno gli scopi seguenti:</span><span class="sxs-lookup"><span data-stu-id="03b41-105">Coding conventions serve the following purposes:</span></span>  
  
-   <span data-ttu-id="03b41-106">Creano un aspetto coerente per il codice in modo che chi legge possa concentrarsi sul contenuto, non sul layout.</span><span class="sxs-lookup"><span data-stu-id="03b41-106">They create a consistent look to the code, so that readers can focus on content, not layout.</span></span>  
  
-   <span data-ttu-id="03b41-107">Consentono a chi legge di comprendere il codice più rapidamente, formulando presupposti basati sulle esperienze precedenti.</span><span class="sxs-lookup"><span data-stu-id="03b41-107">They enable readers to understand the code more quickly by making assumptions based on previous experience.</span></span>  
  
-   <span data-ttu-id="03b41-108">Facilitano la copia, la modifica e la gestione del codice.</span><span class="sxs-lookup"><span data-stu-id="03b41-108">They facilitate copying, changing, and maintaining the code.</span></span>  
  
-   <span data-ttu-id="03b41-109">Illustrano procedure consigliate di C#.</span><span class="sxs-lookup"><span data-stu-id="03b41-109">They demonstrate C# best practices.</span></span>  
  
## <a name="naming-conventions"></a><span data-ttu-id="03b41-110">Convenzioni di denominazione</span><span class="sxs-lookup"><span data-stu-id="03b41-110">Naming Conventions</span></span>  
  
-   <span data-ttu-id="03b41-111">Negli esempi brevi che non includono [direttive using](../../../csharp/language-reference/keywords/using-directive.md), usare qualifiche dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="03b41-111">In short examples that do not include [using directives](../../../csharp/language-reference/keywords/using-directive.md), use namespace qualifications.</span></span> <span data-ttu-id="03b41-112">Se si è certi che uno spazio dei nomi viene importato per impostazione predefinita in un progetto, non è necessario specificare in modo completo i nomi da tale spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="03b41-112">If you know that a namespace is imported by default in a project, you do not have to fully qualify the names from that namespace.</span></span> <span data-ttu-id="03b41-113">I nomi completi possono essere interrotti dopo un punto (.) se sono troppo lunghi per una singola riga, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="03b41-113">Qualified names can be broken after a dot (.) if they are too long for a single line, as shown in the following example.</span></span>  
  
     <span data-ttu-id="03b41-114">[!code-cs[csProgGuideCodingConventions#1](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="03b41-114">[!code-cs[csProgGuideCodingConventions#1](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_1.cs)]</span></span>  
  
-   <span data-ttu-id="03b41-115">Non è necessario modificare i nomi degli oggetti creati usando gli strumenti di progettazione di Visual Studio per adattarli ad altre linee guida.</span><span class="sxs-lookup"><span data-stu-id="03b41-115">You do not have to change the names of objects that were created by using the Visual Studio designer tools to make them fit other guidelines.</span></span>  
  
## <a name="layout-conventions"></a><span data-ttu-id="03b41-116">Convenzioni di layout</span><span class="sxs-lookup"><span data-stu-id="03b41-116">Layout Conventions</span></span>  
 <span data-ttu-id="03b41-117">Un layout appropriato usa la formattazione per mettere in evidenza la struttura del codice e per facilitare la lettura del codice.</span><span class="sxs-lookup"><span data-stu-id="03b41-117">Good layout uses formatting to emphasize the structure of your code and to make the code easier to read.</span></span> <span data-ttu-id="03b41-118">Gli esempi Microsoft sono conformi alle convenzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="03b41-118">Microsoft examples and samples conform to the following conventions:</span></span>  
  
-   <span data-ttu-id="03b41-119">Usare le impostazioni dell'Editor di codice predefinite (rientri intelligenti, rientri di quattro caratteri, tabulazioni salvate come spazi).</span><span class="sxs-lookup"><span data-stu-id="03b41-119">Use the default Code Editor settings (smart indenting, four-character indents, tabs saved as spaces).</span></span> <span data-ttu-id="03b41-120">Per altre informazioni, vedere [Opzioni, Editor di testo, C#, Formattazione](/visualstudio/ide/reference/options-text-editor-csharp-formatting).</span><span class="sxs-lookup"><span data-stu-id="03b41-120">For more information, see [Options, Text Editor, C#, Formatting](/visualstudio/ide/reference/options-text-editor-csharp-formatting).</span></span>  
  
-   <span data-ttu-id="03b41-121">Scrivere una sola istruzione per riga.</span><span class="sxs-lookup"><span data-stu-id="03b41-121">Write only one statement per line.</span></span>  
  
-   <span data-ttu-id="03b41-122">Scrivere una sola dichiarazione per riga.</span><span class="sxs-lookup"><span data-stu-id="03b41-122">Write only one declaration per line.</span></span>  
  
-   <span data-ttu-id="03b41-123">Se le righe di continuazione non sono rientrate automaticamente, impostare un rientro con un punto di tabulazione (quattro spazi).</span><span class="sxs-lookup"><span data-stu-id="03b41-123">If continuation lines are not indented automatically, indent them one tab stop (four spaces).</span></span>  
  
-   <span data-ttu-id="03b41-124">Aggiungere almeno una riga vuota tra le definizioni di metodo e proprietà.</span><span class="sxs-lookup"><span data-stu-id="03b41-124">Add at least one blank line between method definitions and property definitions.</span></span>  
  
-   <span data-ttu-id="03b41-125">Usare le parentesi per rendere visibili le clausole in un'espressione, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="03b41-125">Use parentheses to make clauses in an expression apparent, as shown in the following code.</span></span>  
  
     <span data-ttu-id="03b41-126">[!code-cs[csProgGuideCodingConventions#2](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="03b41-126">[!code-cs[csProgGuideCodingConventions#2](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_2.cs)]</span></span>  
  
## <a name="commenting-conventions"></a><span data-ttu-id="03b41-127">Convenzioni relative ai commenti</span><span class="sxs-lookup"><span data-stu-id="03b41-127">Commenting Conventions</span></span>  
  
-   <span data-ttu-id="03b41-128">Posizionare il commento su una riga separata, non alla fine di una riga di codice.</span><span class="sxs-lookup"><span data-stu-id="03b41-128">Place the comment on a separate line, not at the end of a line of code.</span></span>  
  
-   <span data-ttu-id="03b41-129">Iniziare il commento con una lettera maiuscola.</span><span class="sxs-lookup"><span data-stu-id="03b41-129">Begin comment text with an uppercase letter.</span></span>  
  
-   <span data-ttu-id="03b41-130">Terminare il commento con un punto finale.</span><span class="sxs-lookup"><span data-stu-id="03b41-130">End comment text with a period.</span></span>  
  
-   <span data-ttu-id="03b41-131">Inserire uno spazio tra i delimitatori di commento (//) e il testo del commento, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="03b41-131">Insert one space between the comment delimiter (//) and the comment text, as shown in the following example.</span></span>  
  
     <span data-ttu-id="03b41-132">[!code-cs[csProgGuideCodingConventions#3](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="03b41-132">[!code-cs[csProgGuideCodingConventions#3](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_3.cs)]</span></span>  
  
-   <span data-ttu-id="03b41-133">Non creare blocchi formattati di asterischi intorno ai commenti.</span><span class="sxs-lookup"><span data-stu-id="03b41-133">Do not create formatted blocks of asterisks around comments.</span></span>  
  
## <a name="language-guidelines"></a><span data-ttu-id="03b41-134">Linee guida della lingua</span><span class="sxs-lookup"><span data-stu-id="03b41-134">Language Guidelines</span></span>  
 <span data-ttu-id="03b41-135">Nelle sezioni seguenti vengono descritte le procedure che il team C# deve seguire per preparare campioni ed esempi di codice.</span><span class="sxs-lookup"><span data-stu-id="03b41-135">The following sections describe practices that the C# team follows to prepare code examples and samples.</span></span>  
  
### <a name="string-data-type"></a><span data-ttu-id="03b41-136">Tipo di dati String</span><span class="sxs-lookup"><span data-stu-id="03b41-136">String Data Type</span></span>  
  
-   <span data-ttu-id="03b41-137">Usare l'operatore `+` per concatenare stringhe brevi, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="03b41-137">Use the `+` operator to concatenate short strings, as shown in the following code.</span></span>  
  
     <span data-ttu-id="03b41-138">[!code-cs[csProgGuideCodingConventions#6](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="03b41-138">[!code-cs[csProgGuideCodingConventions#6](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_4.cs)]</span></span>  
  
-   <span data-ttu-id="03b41-139">Per accodare stringhe nei cicli, specialmente quando si lavora con grandi quantità di testo, usare un oggetto <xref:System.Text.StringBuilder>.</span><span class="sxs-lookup"><span data-stu-id="03b41-139">To append strings in loops, especially when you are working with large amounts of text, use a <xref:System.Text.StringBuilder> object.</span></span>  
  
     <span data-ttu-id="03b41-140">[!code-cs[csProgGuideCodingConventions#7](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="03b41-140">[!code-cs[csProgGuideCodingConventions#7](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_5.cs)]</span></span>  
  
### <a name="implicitly-typed-local-variables"></a><span data-ttu-id="03b41-141">Variabili locali tipizzate in modo implicito</span><span class="sxs-lookup"><span data-stu-id="03b41-141">Implicitly Typed Local Variables</span></span>  
  
-   <span data-ttu-id="03b41-142">Usare la [tipizzazione implicita](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md) per le variabili locali quando il tipo della variabile è ovvio dal lato destro dell'assegnazione o il tipo preciso non è importante.</span><span class="sxs-lookup"><span data-stu-id="03b41-142">Use [implicit typing](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md) for local variables when the type of the variable is obvious from the right side of the assignment, or when the precise type is not important.</span></span>  
  
     <span data-ttu-id="03b41-143">[!code-cs[csProgGuideCodingConventions#8](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="03b41-143">[!code-cs[csProgGuideCodingConventions#8](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_6.cs)]</span></span>  
  
-   <span data-ttu-id="03b41-144">Non usare [var](../../../csharp/language-reference/keywords/var.md) quando il tipo non è evidente dal lato destro dell'assegnazione.</span><span class="sxs-lookup"><span data-stu-id="03b41-144">Do not use [var](../../../csharp/language-reference/keywords/var.md) when the type is not apparent from the right side of the assignment.</span></span>  
  
     <span data-ttu-id="03b41-145">[!code-cs[csProgGuideCodingConventions#9](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_7.cs)]</span><span class="sxs-lookup"><span data-stu-id="03b41-145">[!code-cs[csProgGuideCodingConventions#9](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_7.cs)]</span></span>  
  
-   <span data-ttu-id="03b41-146">Non basarsi sul nome della variabile per specificare il tipo della variabile.</span><span class="sxs-lookup"><span data-stu-id="03b41-146">Do not rely on the variable name to specify the type of the variable.</span></span> <span data-ttu-id="03b41-147">Potrebbe non essere corretto.</span><span class="sxs-lookup"><span data-stu-id="03b41-147">It might not be correct.</span></span>  
  
     <span data-ttu-id="03b41-148">[!code-cs[csProgGuideCodingConventions#10](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_8.cs)]</span><span class="sxs-lookup"><span data-stu-id="03b41-148">[!code-cs[csProgGuideCodingConventions#10](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_8.cs)]</span></span>  
  
-   <span data-ttu-id="03b41-149">Evitare l'uso di `var` al posto di [dynamic](../../../csharp/language-reference/keywords/dynamic.md).</span><span class="sxs-lookup"><span data-stu-id="03b41-149">Avoid the use of `var` in place of [dynamic](../../../csharp/language-reference/keywords/dynamic.md).</span></span>  
  
-   <span data-ttu-id="03b41-150">Usare la tipizzazione implicita per determinare il tipo della variabile del ciclo nei cicli [for](../../../csharp/language-reference/keywords/for.md) e [foreach](../../../csharp/language-reference/keywords/foreach-in.md).</span><span class="sxs-lookup"><span data-stu-id="03b41-150">Use implicit typing to determine the type of the loop variable in [for](../../../csharp/language-reference/keywords/for.md) and [foreach](../../../csharp/language-reference/keywords/foreach-in.md) loops.</span></span>  
  
     <span data-ttu-id="03b41-151">Nell'esempio seguente viene usata la tipizzazione implicita in un'istruzione `for`.</span><span class="sxs-lookup"><span data-stu-id="03b41-151">The following example uses implicit typing in a `for` statement.</span></span>  
  
     <span data-ttu-id="03b41-152">[!code-cs[csProgGuideCodingConventions#11](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_9.cs)]</span><span class="sxs-lookup"><span data-stu-id="03b41-152">[!code-cs[csProgGuideCodingConventions#11](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_9.cs)]</span></span>  
  
     <span data-ttu-id="03b41-153">Nell'esempio seguente viene usata la tipizzazione implicita in un'istruzione `foreach`.</span><span class="sxs-lookup"><span data-stu-id="03b41-153">The following example uses implicit typing in a `foreach` statement.</span></span>  
  
     <span data-ttu-id="03b41-154">[!code-cs[csProgGuideCodingConventions#12](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_10.cs)]</span><span class="sxs-lookup"><span data-stu-id="03b41-154">[!code-cs[csProgGuideCodingConventions#12](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_10.cs)]</span></span>  
  
### <a name="unsigned-data-type"></a><span data-ttu-id="03b41-155">Tipi di dati non firmati</span><span class="sxs-lookup"><span data-stu-id="03b41-155">Unsigned Data Type</span></span>  
  
-   <span data-ttu-id="03b41-156">In generale, usare `int` anziché tipi non firmati.</span><span class="sxs-lookup"><span data-stu-id="03b41-156">In general, use `int` rather than unsigned types.</span></span> <span data-ttu-id="03b41-157">L'utilizzo di `int` è comune in C# ed è più facile interagire con altre librerie, quando si usa `int`.</span><span class="sxs-lookup"><span data-stu-id="03b41-157">The use of `int` is common throughout C#, and it is easier to interact with other libraries when you use `int`.</span></span>  
  
### <a name="arrays"></a><span data-ttu-id="03b41-158">Matrici</span><span class="sxs-lookup"><span data-stu-id="03b41-158">Arrays</span></span>  
  
-   <span data-ttu-id="03b41-159">Usare la sintassi concisa quando si inizializzano le matrici nella riga della dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="03b41-159">Use the concise syntax when you initialize arrays on the declaration line.</span></span>  
  
     <span data-ttu-id="03b41-160">[!code-cs[csProgGuideCodingConventions#13](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_11.cs)]</span><span class="sxs-lookup"><span data-stu-id="03b41-160">[!code-cs[csProgGuideCodingConventions#13](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_11.cs)]</span></span>  
  
### <a name="delegates"></a><span data-ttu-id="03b41-161">Delegati</span><span class="sxs-lookup"><span data-stu-id="03b41-161">Delegates</span></span>  
  
-   <span data-ttu-id="03b41-162">Usare la sintassi concisa per creare istanze di un tipo delegato.</span><span class="sxs-lookup"><span data-stu-id="03b41-162">Use the concise syntax to create instances of a delegate type.</span></span>  
  
     <span data-ttu-id="03b41-163">[!code-cs[csProgGuideCodingConventions#14](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_12.cs)]</span><span class="sxs-lookup"><span data-stu-id="03b41-163">[!code-cs[csProgGuideCodingConventions#14](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_12.cs)]</span></span>  
  
     <span data-ttu-id="03b41-164">[!code-cs[csProgGuideCodingConventions#15](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_13.cs)]</span><span class="sxs-lookup"><span data-stu-id="03b41-164">[!code-cs[csProgGuideCodingConventions#15](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_13.cs)]</span></span>  
  
### <a name="try-catch-and-using-statements-in-exception-handling"></a><span data-ttu-id="03b41-165">Istruzioni try-catch e using nella gestione delle eccezioni</span><span class="sxs-lookup"><span data-stu-id="03b41-165">try-catch and using Statements in Exception Handling</span></span>  
  
-   <span data-ttu-id="03b41-166">Usare un'istruzione [try-catch](../../../csharp/language-reference/keywords/try-catch.md) per la gestione della maggior parte delle eccezioni.</span><span class="sxs-lookup"><span data-stu-id="03b41-166">Use a [try-catch](../../../csharp/language-reference/keywords/try-catch.md) statement for most exception handling.</span></span>  
  
     <span data-ttu-id="03b41-167">[!code-cs[csProgGuideCodingConventions#16](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_14.cs)]</span><span class="sxs-lookup"><span data-stu-id="03b41-167">[!code-cs[csProgGuideCodingConventions#16](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_14.cs)]</span></span>  
  
-   <span data-ttu-id="03b41-168">Semplificare il codice usando l'[istruzione using](../../../csharp/language-reference/keywords/using-statement.md) di C#.</span><span class="sxs-lookup"><span data-stu-id="03b41-168">Simplify your code by using the C# [using statement](../../../csharp/language-reference/keywords/using-statement.md).</span></span> <span data-ttu-id="03b41-169">Se si ha un'istruzione [try-finally](../../../csharp/language-reference/keywords/try-finally.md) in cui l'unico codice nel blocco `finally` è una chiamata al metodo <xref:System.IDisposable.Dispose%2A>, usare invece un'istruzione `using`.</span><span class="sxs-lookup"><span data-stu-id="03b41-169">If you have a [try-finally](../../../csharp/language-reference/keywords/try-finally.md) statement in which the only code in the `finally` block is a call to the <xref:System.IDisposable.Dispose%2A> method, use a `using` statement instead.</span></span>  
  
     <span data-ttu-id="03b41-170">[!code-cs[csProgGuideCodingConventions#17](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_15.cs)]</span><span class="sxs-lookup"><span data-stu-id="03b41-170">[!code-cs[csProgGuideCodingConventions#17](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_15.cs)]</span></span>  
  
### <a name="-and-124124-operators"></a><span data-ttu-id="03b41-171">Operatori && e &#124;&#124;</span><span class="sxs-lookup"><span data-stu-id="03b41-171">&& and &#124;&#124; Operators</span></span>  
  
-   <span data-ttu-id="03b41-172">Per evitare eccezioni e migliorare le prestazioni ignorando i confronti non necessari, usare [&&](../../../csharp/language-reference/operators/conditional-and-operator.md) invece di [&](../../../csharp/language-reference/operators/and-operator.md) e [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md) invece di [&#124;](../../../csharp/language-reference/operators/or-operator.md) quando si eseguono confronti, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="03b41-172">To avoid exceptions and increase performance by skipping unnecessary comparisons, use [&&](../../../csharp/language-reference/operators/conditional-and-operator.md) instead of [&](../../../csharp/language-reference/operators/and-operator.md) and [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md) instead of [&#124;](../../../csharp/language-reference/operators/or-operator.md) when you perform comparisons, as shown in the following example.</span></span>  
  
     <span data-ttu-id="03b41-173">[!code-cs[csProgGuideCodingConventions#18](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_16.cs)]</span><span class="sxs-lookup"><span data-stu-id="03b41-173">[!code-cs[csProgGuideCodingConventions#18](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_16.cs)]</span></span>  
  
### <a name="new-operator"></a><span data-ttu-id="03b41-174">Operatore New</span><span class="sxs-lookup"><span data-stu-id="03b41-174">New Operator</span></span>  
  
-   <span data-ttu-id="03b41-175">Usare il modulo conciso della creazione dell'istanza di oggetto, con la tipizzazione implicita, come illustrato nella dichiarazione seguente.</span><span class="sxs-lookup"><span data-stu-id="03b41-175">Use the concise form of object instantiation, with implicit typing, as shown in the following declaration.</span></span>  
  
     <span data-ttu-id="03b41-176">[!code-cs[csProgGuideCodingConventions#19](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_17.cs)]</span><span class="sxs-lookup"><span data-stu-id="03b41-176">[!code-cs[csProgGuideCodingConventions#19](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_17.cs)]</span></span>  
  
     <span data-ttu-id="03b41-177">La riga precedente è equivalente alla dichiarazione seguente.</span><span class="sxs-lookup"><span data-stu-id="03b41-177">The previous line is equivalent to the following declaration.</span></span>  
  
     <span data-ttu-id="03b41-178">[!code-cs[csProgGuideCodingConventions#20](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_18.cs)]</span><span class="sxs-lookup"><span data-stu-id="03b41-178">[!code-cs[csProgGuideCodingConventions#20](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_18.cs)]</span></span>  
  
-   <span data-ttu-id="03b41-179">Usare gli inizializzatori di oggetto per semplificare la creazione di un oggetto.</span><span class="sxs-lookup"><span data-stu-id="03b41-179">Use object initializers to simplify object creation.</span></span>  
  
     <span data-ttu-id="03b41-180">[!code-cs[csProgGuideCodingConventions#21](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_19.cs)]</span><span class="sxs-lookup"><span data-stu-id="03b41-180">[!code-cs[csProgGuideCodingConventions#21](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_19.cs)]</span></span>  
  
### <a name="event-handling"></a><span data-ttu-id="03b41-181">Gestione di eventi</span><span class="sxs-lookup"><span data-stu-id="03b41-181">Event Handling</span></span>  
  
-   <span data-ttu-id="03b41-182">Se si definisce un gestore eventi che non è necessario rimuovere successivamente, usare un'espressione lambda.</span><span class="sxs-lookup"><span data-stu-id="03b41-182">If you are defining an event handler that you do not need to remove later, use a lambda expression.</span></span>  
  
     <span data-ttu-id="03b41-183">[!code-cs[csProgGuideCodingConventions#22](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_20.cs)]</span><span class="sxs-lookup"><span data-stu-id="03b41-183">[!code-cs[csProgGuideCodingConventions#22](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_20.cs)]</span></span>  
  
     <span data-ttu-id="03b41-184">[!code-cs[csProgGuideCodingConventions#23](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_21.cs)]</span><span class="sxs-lookup"><span data-stu-id="03b41-184">[!code-cs[csProgGuideCodingConventions#23](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_21.cs)]</span></span>  
  
### <a name="static-members"></a><span data-ttu-id="03b41-185">Membri static</span><span class="sxs-lookup"><span data-stu-id="03b41-185">Static Members</span></span>  
  
-   <span data-ttu-id="03b41-186">Chiamare i membri [static](../../../csharp/language-reference/keywords/static.md) usando il nome della classe: *ClassName.StaticMember*.</span><span class="sxs-lookup"><span data-stu-id="03b41-186">Call [static](../../../csharp/language-reference/keywords/static.md) members by using the class name: *ClassName.StaticMember*.</span></span> <span data-ttu-id="03b41-187">Questa pratica rende più leggibile il codice semplificando l'accesso statico.</span><span class="sxs-lookup"><span data-stu-id="03b41-187">This practice makes code more readable by making static access clear.</span></span>  <span data-ttu-id="03b41-188">Non qualificare un membro statico definito in una classe base con il nome di una classe derivata.</span><span class="sxs-lookup"><span data-stu-id="03b41-188">Do not qualify a static member defined in a base class with the name of a derived class.</span></span>  <span data-ttu-id="03b41-189">Nonostante il codice venga compilato, la leggibilità del codice è fuorviante mentre il codice potrebbe essere interrotto in futuro, se si aggiunge un membro statico con lo stesso nome alla classe derivata.</span><span class="sxs-lookup"><span data-stu-id="03b41-189">While that code compiles, the code readability is misleading, and the code may break in the future if you add a static member with the same name to the derived class.</span></span>  
  
### <a name="linq-queries"></a><span data-ttu-id="03b41-190">Query LINQ</span><span class="sxs-lookup"><span data-stu-id="03b41-190">LINQ Queries</span></span>  
  
-   <span data-ttu-id="03b41-191">Usare nomi significativi per le variabili di query.</span><span class="sxs-lookup"><span data-stu-id="03b41-191">Use meaningful names for query variables.</span></span> <span data-ttu-id="03b41-192">Nell'esempio seguente viene usato `seattleCustomers` per i clienti che si trovano a Seattle.</span><span class="sxs-lookup"><span data-stu-id="03b41-192">The following example uses `seattleCustomers` for customers who are located in Seattle.</span></span>  
  
     <span data-ttu-id="03b41-193">[!code-cs[csProgGuideCodingConventions#25](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_22.cs)]</span><span class="sxs-lookup"><span data-stu-id="03b41-193">[!code-cs[csProgGuideCodingConventions#25](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_22.cs)]</span></span>  
  
-   <span data-ttu-id="03b41-194">Usare gli alias per assicurarsi che i nomi delle proprietà di tipi anonimi siano scritti correttamente in maiuscolo, usando la convenzione Pascal.</span><span class="sxs-lookup"><span data-stu-id="03b41-194">Use aliases to make sure that property names of anonymous types are correctly capitalized, using Pascal casing.</span></span>  
  
     <span data-ttu-id="03b41-195">[!code-cs[csProgGuideCodingConventions#26](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_23.cs)]</span><span class="sxs-lookup"><span data-stu-id="03b41-195">[!code-cs[csProgGuideCodingConventions#26](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_23.cs)]</span></span>  
  
-   <span data-ttu-id="03b41-196">Rinominare le proprietà quando i nomi delle proprietà nel risultato potrebbero risultare ambigui.</span><span class="sxs-lookup"><span data-stu-id="03b41-196">Rename properties when the property names in the result would be ambiguous.</span></span> <span data-ttu-id="03b41-197">Ad esempio, se la query restituisce un nome cliente un ID del server di distribuzione, anziché lasciarli come `Name` e `ID` nei risultati, rinominarli per spiegare che `Name` è il nome di un cliente e `ID` è l'ID di un server di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="03b41-197">For example, if your query returns a customer name and a distributor ID, instead of leaving them as `Name` and `ID` in the result, rename them to clarify that `Name` is the name of a customer, and `ID` is the ID of a distributor.</span></span>  
  
     <span data-ttu-id="03b41-198">[!code-cs[csProgGuideCodingConventions#27](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_24.cs)]</span><span class="sxs-lookup"><span data-stu-id="03b41-198">[!code-cs[csProgGuideCodingConventions#27](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_24.cs)]</span></span>  
  
-   <span data-ttu-id="03b41-199">Usare la tipizzazione implicita nella dichiarazione di variabili di query e variabili di intervallo.</span><span class="sxs-lookup"><span data-stu-id="03b41-199">Use implicit typing in the declaration of query variables and range variables.</span></span>  
  
     <span data-ttu-id="03b41-200">[!code-cs[csProgGuideCodingConventions#25](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_22.cs)]</span><span class="sxs-lookup"><span data-stu-id="03b41-200">[!code-cs[csProgGuideCodingConventions#25](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_22.cs)]</span></span>  
  
-   <span data-ttu-id="03b41-201">Allineare le clausole di query sotto la clausola [from](../../../csharp/language-reference/keywords/from-clause.md), come illustrato negli esempi precedenti.</span><span class="sxs-lookup"><span data-stu-id="03b41-201">Align query clauses under the [from](../../../csharp/language-reference/keywords/from-clause.md) clause, as shown in the previous examples.</span></span>  
  
-   <span data-ttu-id="03b41-202">Usare le clausole [where](../../../csharp/language-reference/keywords/where-clause.md) prima delle altre clausole di query, per garantire che le clausole di query successive agiscano su un set di dati ridotto e filtrato.</span><span class="sxs-lookup"><span data-stu-id="03b41-202">Use [where](../../../csharp/language-reference/keywords/where-clause.md) clauses before other query clauses to ensure that later query clauses operate on the reduced, filtered set of data.</span></span>  
  
     <span data-ttu-id="03b41-203">[!code-cs[csProgGuideCodingConventions#29](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_25.cs)]</span><span class="sxs-lookup"><span data-stu-id="03b41-203">[!code-cs[csProgGuideCodingConventions#29](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_25.cs)]</span></span>  
  
-   <span data-ttu-id="03b41-204">Usare più clausole `from` invece di una clausola [join](../../../csharp/language-reference/keywords/join-clause.md) per accedere a raccolte interne.</span><span class="sxs-lookup"><span data-stu-id="03b41-204">Use multiple `from` clauses instead of a [join](../../../csharp/language-reference/keywords/join-clause.md) clause to access inner collections.</span></span> <span data-ttu-id="03b41-205">Ad esempio, ogni raccolta di oggetti `Student` potrebbe contenere una raccolta di punteggi del test.</span><span class="sxs-lookup"><span data-stu-id="03b41-205">For example, a collection of `Student` objects might each contain a collection of test scores.</span></span> <span data-ttu-id="03b41-206">Quando viene eseguita la query seguente, viene restituito ogni punteggio superiore a 90, e il cognome dello studente che ha ricevuto il punteggio.</span><span class="sxs-lookup"><span data-stu-id="03b41-206">When the following query is executed, it returns each score that is over 90, along with the last name of the student who received the score.</span></span>  
  
     <span data-ttu-id="03b41-207">[!code-cs[csProgGuideCodingConventions#30](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_26.cs)]</span><span class="sxs-lookup"><span data-stu-id="03b41-207">[!code-cs[csProgGuideCodingConventions#30](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_26.cs)]</span></span>  
  
## <a name="security"></a><span data-ttu-id="03b41-208">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="03b41-208">Security</span></span>  
 <span data-ttu-id="03b41-209">Seguire le indicazioni in [Linee guida per la generazione di codice sicuro](../../../standard/security/secure-coding-guidelines.md).</span><span class="sxs-lookup"><span data-stu-id="03b41-209">Follow the guidelines in [Secure Coding Guidelines](../../../standard/security/secure-coding-guidelines.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03b41-210">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="03b41-210">See Also</span></span>  
 <span data-ttu-id="03b41-211">[Convenzioni di codifica di Visual Basic](../../../visual-basic/programming-guide/program-structure/coding-conventions.md) </span><span class="sxs-lookup"><span data-stu-id="03b41-211">[Visual Basic Coding Conventions](../../../visual-basic/programming-guide/program-structure/coding-conventions.md) </span></span>  
 [<span data-ttu-id="03b41-212">Linee guida per la generazione di codice sicuro</span><span class="sxs-lookup"><span data-stu-id="03b41-212">Secure Coding Guidelines</span></span>](../../../standard/security/secure-coding-guidelines.md)

