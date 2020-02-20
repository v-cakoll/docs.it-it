---
title: Convenzioni di codifica C# - Guida per programmatori C#
ms.date: 07/20/2015
helpviewer_keywords:
- coding conventions, C#
- Visual C#, coding conventions
- C# language, coding conventions
ms.assetid: f4f60de9-d49b-4fb6-bab1-20e19ea24710
ms.openlocfilehash: 77b173a420f26834855e0bdca3c8d04406ac65d4
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452006"
---
# <a name="c-coding-conventions-c-programming-guide"></a><span data-ttu-id="945a1-102">Convenzioni di codifica C# (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="945a1-102">C# Coding Conventions (C# Programming Guide)</span></span>

<span data-ttu-id="945a1-103">Le convenzioni di codifica hanno gli scopi seguenti:</span><span class="sxs-lookup"><span data-stu-id="945a1-103">Coding conventions serve the following purposes:</span></span>  
  
- <span data-ttu-id="945a1-104">Creano un aspetto coerente per il codice in modo che chi legge possa concentrarsi sul contenuto, non sul layout.</span><span class="sxs-lookup"><span data-stu-id="945a1-104">They create a consistent look to the code, so that readers can focus on content, not layout.</span></span>  
  
- <span data-ttu-id="945a1-105">Consentono a chi legge di comprendere il codice più rapidamente, formulando presupposti basati sulle esperienze precedenti.</span><span class="sxs-lookup"><span data-stu-id="945a1-105">They enable readers to understand the code more quickly by making assumptions based on previous experience.</span></span>  
  
- <span data-ttu-id="945a1-106">Facilitano la copia, la modifica e la gestione del codice.</span><span class="sxs-lookup"><span data-stu-id="945a1-106">They facilitate copying, changing, and maintaining the code.</span></span>  
  
- <span data-ttu-id="945a1-107">Illustrano procedure consigliate di C#.</span><span class="sxs-lookup"><span data-stu-id="945a1-107">They demonstrate C# best practices.</span></span>  

<span data-ttu-id="945a1-108">Le linee guida riportate in questo articolo sono utilizzate da Microsoft per sviluppare esempi e documentazione.</span><span class="sxs-lookup"><span data-stu-id="945a1-108">The guidelines in this article are used by Microsoft to develop samples and documentation.</span></span>  
  
## <a name="naming-conventions"></a><span data-ttu-id="945a1-109">Convenzioni di denominazione</span><span class="sxs-lookup"><span data-stu-id="945a1-109">Naming Conventions</span></span>  
  
- <span data-ttu-id="945a1-110">Negli esempi brevi che non includono [direttive using](../../language-reference/keywords/using-directive.md), usare qualifiche dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="945a1-110">In short examples that do not include [using directives](../../language-reference/keywords/using-directive.md), use namespace qualifications.</span></span> <span data-ttu-id="945a1-111">Se si è certi che uno spazio dei nomi viene importato per impostazione predefinita in un progetto, non è necessario specificare in modo completo i nomi da tale spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="945a1-111">If you know that a namespace is imported by default in a project, you do not have to fully qualify the names from that namespace.</span></span> <span data-ttu-id="945a1-112">I nomi completi possono essere interrotti dopo un punto (.) se sono troppo lunghi per una singola riga, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="945a1-112">Qualified names can be broken after a dot (.) if they are too long for a single line, as shown in the following example.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#1](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#1)]  
  
- <span data-ttu-id="945a1-113">Non è necessario modificare i nomi degli oggetti creati usando gli strumenti di progettazione di Visual Studio per adattarli ad altre linee guida.</span><span class="sxs-lookup"><span data-stu-id="945a1-113">You do not have to change the names of objects that were created by using the Visual Studio designer tools to make them fit other guidelines.</span></span>  
  
## <a name="layout-conventions"></a><span data-ttu-id="945a1-114">Convenzioni di layout</span><span class="sxs-lookup"><span data-stu-id="945a1-114">Layout Conventions</span></span>  

<span data-ttu-id="945a1-115">Un layout appropriato usa la formattazione per mettere in evidenza la struttura del codice e per facilitare la lettura del codice.</span><span class="sxs-lookup"><span data-stu-id="945a1-115">Good layout uses formatting to emphasize the structure of your code and to make the code easier to read.</span></span> <span data-ttu-id="945a1-116">Gli esempi Microsoft sono conformi alle convenzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="945a1-116">Microsoft examples and samples conform to the following conventions:</span></span>  
  
- <span data-ttu-id="945a1-117">Usare le impostazioni dell'Editor di codice predefinite (rientri intelligenti, rientri di quattro caratteri, tabulazioni salvate come spazi).</span><span class="sxs-lookup"><span data-stu-id="945a1-117">Use the default Code Editor settings (smart indenting, four-character indents, tabs saved as spaces).</span></span> <span data-ttu-id="945a1-118">Per altre informazioni, vedere [Opzioni, Editor di testo, C#, Formattazione](/visualstudio/ide/reference/options-text-editor-csharp-formatting).</span><span class="sxs-lookup"><span data-stu-id="945a1-118">For more information, see [Options, Text Editor, C#, Formatting](/visualstudio/ide/reference/options-text-editor-csharp-formatting).</span></span>  
  
- <span data-ttu-id="945a1-119">Scrivere una sola istruzione per riga.</span><span class="sxs-lookup"><span data-stu-id="945a1-119">Write only one statement per line.</span></span>  
  
- <span data-ttu-id="945a1-120">Scrivere una sola dichiarazione per riga.</span><span class="sxs-lookup"><span data-stu-id="945a1-120">Write only one declaration per line.</span></span>  
  
- <span data-ttu-id="945a1-121">Se le righe di continuazione non sono rientrate automaticamente, impostare un rientro con un punto di tabulazione (quattro spazi).</span><span class="sxs-lookup"><span data-stu-id="945a1-121">If continuation lines are not indented automatically, indent them one tab stop (four spaces).</span></span>  
  
- <span data-ttu-id="945a1-122">Aggiungere almeno una riga vuota tra le definizioni di metodo e proprietà.</span><span class="sxs-lookup"><span data-stu-id="945a1-122">Add at least one blank line between method definitions and property definitions.</span></span>  
  
- <span data-ttu-id="945a1-123">Usare le parentesi per rendere visibili le clausole in un'espressione, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="945a1-123">Use parentheses to make clauses in an expression apparent, as shown in the following code.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#2](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#2)]  
  
## <a name="commenting-conventions"></a><span data-ttu-id="945a1-124">Convenzioni relative ai commenti</span><span class="sxs-lookup"><span data-stu-id="945a1-124">Commenting Conventions</span></span>  
  
- <span data-ttu-id="945a1-125">Posizionare il commento su una riga separata, non alla fine di una riga di codice.</span><span class="sxs-lookup"><span data-stu-id="945a1-125">Place the comment on a separate line, not at the end of a line of code.</span></span>  
  
- <span data-ttu-id="945a1-126">Iniziare il commento con una lettera maiuscola.</span><span class="sxs-lookup"><span data-stu-id="945a1-126">Begin comment text with an uppercase letter.</span></span>  
  
- <span data-ttu-id="945a1-127">Terminare il commento con un punto finale.</span><span class="sxs-lookup"><span data-stu-id="945a1-127">End comment text with a period.</span></span>  
  
- <span data-ttu-id="945a1-128">Inserire uno spazio tra i delimitatori di commento (//) e il testo del commento, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="945a1-128">Insert one space between the comment delimiter (//) and the comment text, as shown in the following example.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#3](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#3)]  
  
- <span data-ttu-id="945a1-129">Non creare blocchi formattati di asterischi intorno ai commenti.</span><span class="sxs-lookup"><span data-stu-id="945a1-129">Do not create formatted blocks of asterisks around comments.</span></span>  
  
## <a name="language-guidelines"></a><span data-ttu-id="945a1-130">Linee guida della lingua</span><span class="sxs-lookup"><span data-stu-id="945a1-130">Language Guidelines</span></span>  

<span data-ttu-id="945a1-131">Nelle sezioni seguenti vengono descritte le procedure che il team C# deve seguire per preparare campioni ed esempi di codice.</span><span class="sxs-lookup"><span data-stu-id="945a1-131">The following sections describe practices that the C# team follows to prepare code examples and samples.</span></span>  
  
### <a name="string-data-type"></a><span data-ttu-id="945a1-132">Tipo di dati String</span><span class="sxs-lookup"><span data-stu-id="945a1-132">String Data Type</span></span>  
  
- <span data-ttu-id="945a1-133">Usare l'[interpolazione di stringhe](../../language-reference/tokens/interpolated.md) per concatenare stringhe brevi, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="945a1-133">Use [string interpolation](../../language-reference/tokens/interpolated.md) to concatenate short strings, as shown in the following code.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#6](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#6)]  
  
- <span data-ttu-id="945a1-134">Per accodare stringhe nei cicli, specialmente quando si lavora con grandi quantità di testo, usare un oggetto <xref:System.Text.StringBuilder>.</span><span class="sxs-lookup"><span data-stu-id="945a1-134">To append strings in loops, especially when you are working with large amounts of text, use a <xref:System.Text.StringBuilder> object.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#7](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#7)]  
  
### <a name="implicitly-typed-local-variables"></a><span data-ttu-id="945a1-135">Variabili locali tipizzate in modo implicito</span><span class="sxs-lookup"><span data-stu-id="945a1-135">Implicitly Typed Local Variables</span></span>  
  
- <span data-ttu-id="945a1-136">Usare la [tipizzazione implicita](../classes-and-structs/implicitly-typed-local-variables.md) per le variabili locali quando il tipo della variabile è ovvio dal lato destro dell'assegnazione o il tipo preciso non è importante.</span><span class="sxs-lookup"><span data-stu-id="945a1-136">Use [implicit typing](../classes-and-structs/implicitly-typed-local-variables.md) for local variables when the type of the variable is obvious from the right side of the assignment, or when the precise type is not important.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#8](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#8)]  
  
- <span data-ttu-id="945a1-137">Non usare [var](../../language-reference/keywords/var.md) quando il tipo non è evidente dal lato destro dell'assegnazione.</span><span class="sxs-lookup"><span data-stu-id="945a1-137">Do not use [var](../../language-reference/keywords/var.md) when the type is not apparent from the right side of the assignment.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#9](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#9)]  
  
- <span data-ttu-id="945a1-138">Non basarsi sul nome della variabile per specificare il tipo della variabile.</span><span class="sxs-lookup"><span data-stu-id="945a1-138">Do not rely on the variable name to specify the type of the variable.</span></span> <span data-ttu-id="945a1-139">Potrebbe non essere corretto.</span><span class="sxs-lookup"><span data-stu-id="945a1-139">It might not be correct.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#10](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#10)]  
  
- <span data-ttu-id="945a1-140">Evitare l'uso di `var` al posto di [dynamic](../../language-reference/builtin-types/reference-types.md).</span><span class="sxs-lookup"><span data-stu-id="945a1-140">Avoid the use of `var` in place of [dynamic](../../language-reference/builtin-types/reference-types.md).</span></span>  
  
- <span data-ttu-id="945a1-141">Usare la tipizzazione implicita per determinare il tipo della variabile del ciclo nei cicli [for](../../language-reference/keywords/for.md) .</span><span class="sxs-lookup"><span data-stu-id="945a1-141">Use implicit typing to determine the type of the loop variable in [for](../../language-reference/keywords/for.md) loops.</span></span>  
  
     <span data-ttu-id="945a1-142">Nell'esempio seguente viene usata la tipizzazione implicita in un'istruzione `for`.</span><span class="sxs-lookup"><span data-stu-id="945a1-142">The following example uses implicit typing in a `for` statement.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#7](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#7)]  

- <span data-ttu-id="945a1-143">Non usare la tipizzazione implicita per determinare il tipo della variabile del ciclo nei cicli [foreach](../../language-reference/keywords/foreach-in.md) .</span><span class="sxs-lookup"><span data-stu-id="945a1-143">Do not use implicit typing to determine the type of the loop variable in [foreach](../../language-reference/keywords/foreach-in.md) loops.</span></span>

     <span data-ttu-id="945a1-144">Nell'esempio seguente viene usata la tipizzazione esplicita in un'istruzione `foreach`.</span><span class="sxs-lookup"><span data-stu-id="945a1-144">The following example uses explicit typing in a `foreach` statement.</span></span>

     [!code-csharp[csProgGuideCodingConventions#12](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#12)]

     > [!NOTE]
     > <span data-ttu-id="945a1-145">Prestare attenzione a non modificare accidentalmente un tipo di elemento della raccolta iterable.</span><span class="sxs-lookup"><span data-stu-id="945a1-145">Be careful not to accidentally change a type of an element of the iterable collection.</span></span> <span data-ttu-id="945a1-146">Ad esempio, è facile passare da <xref:System.Linq.IQueryable?displayProperty=nameWithType> a <xref:System.Collections.IEnumerable?displayProperty=nameWithType> in un'istruzione `foreach`, che modifica l'esecuzione di una query.</span><span class="sxs-lookup"><span data-stu-id="945a1-146">For example, it is easy to switch from <xref:System.Linq.IQueryable?displayProperty=nameWithType> to <xref:System.Collections.IEnumerable?displayProperty=nameWithType> in a `foreach` statement, which changes the execution of a query.</span></span>

### <a name="unsigned-data-type"></a><span data-ttu-id="945a1-147">Tipi di dati non firmati</span><span class="sxs-lookup"><span data-stu-id="945a1-147">Unsigned Data Type</span></span>  
  
<span data-ttu-id="945a1-148">In generale, usare `int` anziché tipi non firmati.</span><span class="sxs-lookup"><span data-stu-id="945a1-148">In general, use `int` rather than unsigned types.</span></span> <span data-ttu-id="945a1-149">L'utilizzo di `int` è comune in C# ed è più facile interagire con altre librerie, quando si usa `int`.</span><span class="sxs-lookup"><span data-stu-id="945a1-149">The use of `int` is common throughout C#, and it is easier to interact with other libraries when you use `int`.</span></span>  
  
### <a name="arrays"></a><span data-ttu-id="945a1-150">Matrici</span><span class="sxs-lookup"><span data-stu-id="945a1-150">Arrays</span></span>  
  
<span data-ttu-id="945a1-151">Usare la sintassi concisa quando si inizializzano le matrici nella riga della dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="945a1-151">Use the concise syntax when you initialize arrays on the declaration line.</span></span>  
  
[!code-csharp[csProgGuideCodingConventions#13](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#13)]  
  
### <a name="delegates"></a><span data-ttu-id="945a1-152">Delegati</span><span class="sxs-lookup"><span data-stu-id="945a1-152">Delegates</span></span>  
  
<span data-ttu-id="945a1-153">Usare la sintassi concisa per creare istanze di un tipo delegato.</span><span class="sxs-lookup"><span data-stu-id="945a1-153">Use the concise syntax to create instances of a delegate type.</span></span>  
  
[!code-csharp[csProgGuideCodingConventions#14](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#14)]  
  
[!code-csharp[csProgGuideCodingConventions#15](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#15)]  
  
### <a name="try-catch-and-using-statements-in-exception-handling"></a><span data-ttu-id="945a1-154">Istruzioni try-catch e using nella gestione delle eccezioni</span><span class="sxs-lookup"><span data-stu-id="945a1-154">try-catch and using Statements in Exception Handling</span></span>  
  
- <span data-ttu-id="945a1-155">Usare un'istruzione [try-catch](../../language-reference/keywords/try-catch.md) per la gestione della maggior parte delle eccezioni.</span><span class="sxs-lookup"><span data-stu-id="945a1-155">Use a [try-catch](../../language-reference/keywords/try-catch.md) statement for most exception handling.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#16](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#16)]  
  
- <span data-ttu-id="945a1-156">Semplificare il codice usando l'[istruzione using](../../language-reference/keywords/using-statement.md) di C#.</span><span class="sxs-lookup"><span data-stu-id="945a1-156">Simplify your code by using the C# [using statement](../../language-reference/keywords/using-statement.md).</span></span> <span data-ttu-id="945a1-157">Se si ha un'istruzione [try-finally](../../language-reference/keywords/try-finally.md) in cui l'unico codice nel blocco `finally` è una chiamata al metodo <xref:System.IDisposable.Dispose%2A>, usare invece un'istruzione `using`.</span><span class="sxs-lookup"><span data-stu-id="945a1-157">If you have a [try-finally](../../language-reference/keywords/try-finally.md) statement in which the only code in the `finally` block is a call to the <xref:System.IDisposable.Dispose%2A> method, use a `using` statement instead.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#17](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#17)]  
  
### <a name="-and-124124-operators"></a><span data-ttu-id="945a1-158">Operatori && e &#124;&#124;</span><span class="sxs-lookup"><span data-stu-id="945a1-158">&& and &#124;&#124; Operators</span></span>  
  
<span data-ttu-id="945a1-159">Per evitare eccezioni e migliorare le prestazioni ignorando i confronti non necessari, usare [&&](../../language-reference/operators/boolean-logical-operators.md#conditional-logical-and-operator-) invece di [&](../../language-reference/operators/boolean-logical-operators.md#logical-and-operator-) e [&#124;&#124;](../../language-reference/operators/boolean-logical-operators.md#conditional-logical-or-operator-) invece di [&#124;](../../language-reference/operators/boolean-logical-operators.md#logical-or-operator-) quando si eseguono confronti, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="945a1-159">To avoid exceptions and increase performance by skipping unnecessary comparisons, use [&&](../../language-reference/operators/boolean-logical-operators.md#conditional-logical-and-operator-) instead of [&](../../language-reference/operators/boolean-logical-operators.md#logical-and-operator-) and [&#124;&#124;](../../language-reference/operators/boolean-logical-operators.md#conditional-logical-or-operator-) instead of [&#124;](../../language-reference/operators/boolean-logical-operators.md#logical-or-operator-) when you perform comparisons, as shown in the following example.</span></span>  
  
[!code-csharp[csProgGuideCodingConventions#18](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#18)]  
  
### <a name="new-operator"></a><span data-ttu-id="945a1-160">Operatore New</span><span class="sxs-lookup"><span data-stu-id="945a1-160">New Operator</span></span>  
  
- <span data-ttu-id="945a1-161">Usare il modulo conciso della creazione dell'istanza di oggetto, con la tipizzazione implicita, come illustrato nella dichiarazione seguente.</span><span class="sxs-lookup"><span data-stu-id="945a1-161">Use the concise form of object instantiation, with implicit typing, as shown in the following declaration.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#19](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#19)]  
  
     <span data-ttu-id="945a1-162">La riga precedente è equivalente alla dichiarazione seguente.</span><span class="sxs-lookup"><span data-stu-id="945a1-162">The previous line is equivalent to the following declaration.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#20](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#20)]  
  
- <span data-ttu-id="945a1-163">Usare gli inizializzatori di oggetto per semplificare la creazione di un oggetto.</span><span class="sxs-lookup"><span data-stu-id="945a1-163">Use object initializers to simplify object creation.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#21](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#21)]  
  
### <a name="event-handling"></a><span data-ttu-id="945a1-164">Gestione di eventi</span><span class="sxs-lookup"><span data-stu-id="945a1-164">Event Handling</span></span>  
  
<span data-ttu-id="945a1-165">Se si definisce un gestore eventi che non è necessario rimuovere successivamente, usare un'espressione lambda.</span><span class="sxs-lookup"><span data-stu-id="945a1-165">If you are defining an event handler that you do not need to remove later, use a lambda expression.</span></span>  
  
[!code-csharp[csProgGuideCodingConventions#22](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#22)]  
  
[!code-csharp[csProgGuideCodingConventions#23](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#23)]  
  
### <a name="static-members"></a><span data-ttu-id="945a1-166">Membri static</span><span class="sxs-lookup"><span data-stu-id="945a1-166">Static Members</span></span>  
  
<span data-ttu-id="945a1-167">Chiamare i membri [static](../../language-reference/keywords/static.md) usando il nome della classe: *ClassName.StaticMember*.</span><span class="sxs-lookup"><span data-stu-id="945a1-167">Call [static](../../language-reference/keywords/static.md) members by using the class name: *ClassName.StaticMember*.</span></span> <span data-ttu-id="945a1-168">Questa pratica rende più leggibile il codice semplificando l'accesso statico.</span><span class="sxs-lookup"><span data-stu-id="945a1-168">This practice makes code more readable by making static access clear.</span></span>  <span data-ttu-id="945a1-169">Non qualificare un membro statico definito in una classe base con il nome di una classe derivata.</span><span class="sxs-lookup"><span data-stu-id="945a1-169">Do not qualify a static member defined in a base class with the name of a derived class.</span></span>  <span data-ttu-id="945a1-170">Nonostante il codice venga compilato, la leggibilità del codice è fuorviante mentre il codice potrebbe essere interrotto in futuro, se si aggiunge un membro statico con lo stesso nome alla classe derivata.</span><span class="sxs-lookup"><span data-stu-id="945a1-170">While that code compiles, the code readability is misleading, and the code may break in the future if you add a static member with the same name to the derived class.</span></span>  
  
### <a name="linq-queries"></a><span data-ttu-id="945a1-171">Query LINQ</span><span class="sxs-lookup"><span data-stu-id="945a1-171">LINQ Queries</span></span>  
  
- <span data-ttu-id="945a1-172">Usare nomi significativi per le variabili di query.</span><span class="sxs-lookup"><span data-stu-id="945a1-172">Use meaningful names for query variables.</span></span> <span data-ttu-id="945a1-173">Nell'esempio seguente viene usato `seattleCustomers` per i clienti che si trovano a Seattle.</span><span class="sxs-lookup"><span data-stu-id="945a1-173">The following example uses `seattleCustomers` for customers who are located in Seattle.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#25](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#25)]  
  
- <span data-ttu-id="945a1-174">Usare gli alias per assicurarsi che i nomi delle proprietà di tipi anonimi siano scritti correttamente in maiuscolo, usando la convenzione Pascal.</span><span class="sxs-lookup"><span data-stu-id="945a1-174">Use aliases to make sure that property names of anonymous types are correctly capitalized, using Pascal casing.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#26](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#26)]  
  
- <span data-ttu-id="945a1-175">Rinominare le proprietà quando i nomi delle proprietà nel risultato potrebbero risultare ambigui.</span><span class="sxs-lookup"><span data-stu-id="945a1-175">Rename properties when the property names in the result would be ambiguous.</span></span> <span data-ttu-id="945a1-176">Ad esempio, se la query restituisce un nome cliente un ID del server di distribuzione, anziché lasciarli come `Name` e `ID` nei risultati, rinominarli per spiegare che `Name` è il nome di un cliente e `ID` è l'ID di un server di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="945a1-176">For example, if your query returns a customer name and a distributor ID, instead of leaving them as `Name` and `ID` in the result, rename them to clarify that `Name` is the name of a customer, and `ID` is the ID of a distributor.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#27](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#27)]  
  
- <span data-ttu-id="945a1-177">Usare la tipizzazione implicita nella dichiarazione di variabili di query e variabili di intervallo.</span><span class="sxs-lookup"><span data-stu-id="945a1-177">Use implicit typing in the declaration of query variables and range variables.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#25](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#25)]  
  
- <span data-ttu-id="945a1-178">Allineare le clausole di query sotto la clausola [from](../../language-reference/keywords/from-clause.md), come illustrato negli esempi precedenti.</span><span class="sxs-lookup"><span data-stu-id="945a1-178">Align query clauses under the [from](../../language-reference/keywords/from-clause.md) clause, as shown in the previous examples.</span></span>  
  
- <span data-ttu-id="945a1-179">Usare le clausole [where](../../language-reference/keywords/where-clause.md) prima delle altre clausole di query, per garantire che le clausole di query successive agiscano su un set di dati ridotto e filtrato.</span><span class="sxs-lookup"><span data-stu-id="945a1-179">Use [where](../../language-reference/keywords/where-clause.md) clauses before other query clauses to ensure that later query clauses operate on the reduced, filtered set of data.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#29](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#29)]  
  
- <span data-ttu-id="945a1-180">Usare più clausole `from` invece di una clausola [join](../../language-reference/keywords/join-clause.md) per accedere a raccolte interne.</span><span class="sxs-lookup"><span data-stu-id="945a1-180">Use multiple `from` clauses instead of a [join](../../language-reference/keywords/join-clause.md) clause to access inner collections.</span></span> <span data-ttu-id="945a1-181">Ad esempio, ogni raccolta di oggetti `Student` potrebbe contenere una raccolta di punteggi del test.</span><span class="sxs-lookup"><span data-stu-id="945a1-181">For example, a collection of `Student` objects might each contain a collection of test scores.</span></span> <span data-ttu-id="945a1-182">Quando viene eseguita la query seguente, viene restituito ogni punteggio superiore a 90, e il cognome dello studente che ha ricevuto il punteggio.</span><span class="sxs-lookup"><span data-stu-id="945a1-182">When the following query is executed, it returns each score that is over 90, along with the last name of the student who received the score.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#30](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#30)]  
  
## <a name="security"></a><span data-ttu-id="945a1-183">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="945a1-183">Security</span></span>  

<span data-ttu-id="945a1-184">Seguire le indicazioni in [Linee guida per la generazione di codice sicuro](../../../standard/security/secure-coding-guidelines.md).</span><span class="sxs-lookup"><span data-stu-id="945a1-184">Follow the guidelines in [Secure Coding Guidelines](../../../standard/security/secure-coding-guidelines.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="945a1-185">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="945a1-185">See also</span></span>

- [<span data-ttu-id="945a1-186">Convenzioni di scrittura codice di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="945a1-186">Visual Basic Coding Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/coding-conventions.md)
- [<span data-ttu-id="945a1-187">Linee guida per la generazione di codice sicuro</span><span class="sxs-lookup"><span data-stu-id="945a1-187">Secure Coding Guidelines</span></span>](../../../standard/security/secure-coding-guidelines.md)
