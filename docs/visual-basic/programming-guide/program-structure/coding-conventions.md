---
title: Convenzioni di codifica di Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- coding conventions [Visual Basic], Visual Basic
- examples [Visual Basic], coding conventions
- Visual Basic code, conventions
ms.assetid: c1df130b-fec6-49a5-becf-0a7e494a1d0f
ms.openlocfilehash: e036792cf33082fa78cf243887b8ac7db7f8ad5a
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56981491"
---
# <a name="visual-basic-coding-conventions"></a><span data-ttu-id="c685a-102">Convenzioni di codifica di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c685a-102">Visual Basic Coding Conventions</span></span>
<span data-ttu-id="c685a-103">Microsoft sviluppa esempi e documentazione che seguono le linee guida in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="c685a-103">Microsoft develops samples and documentation that follow the guidelines in this topic.</span></span> <span data-ttu-id="c685a-104">Se si seguono le stesse convenzioni di scrittura del codice, si potrebbero ottenere i vantaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="c685a-104">If you follow the same coding conventions, you may gain the following benefits:</span></span>  
  
-   <span data-ttu-id="c685a-105">Il codice avrà un aspetto coerente, in modo che chi legge possa concentrarsi meglio sul contenuto, non di layout.</span><span class="sxs-lookup"><span data-stu-id="c685a-105">Your code will have a consistent look, so that readers can better focus on content, not layout.</span></span>  
  
-   <span data-ttu-id="c685a-106">I lettori comprendono il codice più rapidamente poiché è possibile basarsi su presupposti basati sulle esperienze precedenti.</span><span class="sxs-lookup"><span data-stu-id="c685a-106">Readers understand your code more quickly because they can make assumptions based on previous experience.</span></span>  
  
-   <span data-ttu-id="c685a-107">È possibile copiare, modificare e gestire più facilmente il codice.</span><span class="sxs-lookup"><span data-stu-id="c685a-107">You can copy, change, and maintain the code more easily.</span></span>  
  
-   <span data-ttu-id="c685a-108">Per garantire che il codice dimostra le "procedure consigliate" per Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="c685a-108">You help ensure that your code demonstrates "best practices" for Visual Basic.</span></span>  
  
## <a name="naming-conventions"></a><span data-ttu-id="c685a-109">Convenzioni di denominazione</span><span class="sxs-lookup"><span data-stu-id="c685a-109">Naming Conventions</span></span>  
  
-   <span data-ttu-id="c685a-110">Per informazioni sulle convenzioni di denominazione, vedere [convenzioni di denominazione per](../../../standard/design-guidelines/naming-guidelines.md) argomento.</span><span class="sxs-lookup"><span data-stu-id="c685a-110">For information about naming guidelines, see [Naming Guidelines](../../../standard/design-guidelines/naming-guidelines.md) topic.</span></span>  
  
-   <span data-ttu-id="c685a-111">Non usare "My" o "my" come parte di un nome di variabile.</span><span class="sxs-lookup"><span data-stu-id="c685a-111">Do not use "My" or "my" as part of a variable name.</span></span> <span data-ttu-id="c685a-112">Questa pratica crea confusione con i `My` oggetti.</span><span class="sxs-lookup"><span data-stu-id="c685a-112">This practice creates confusion with the `My` objects.</span></span>  
  
-   <span data-ttu-id="c685a-113">Non è necessario modificare i nomi degli oggetti nel codice generato automaticamente per adattarli le linee guida.</span><span class="sxs-lookup"><span data-stu-id="c685a-113">You do not have to change the names of objects in auto-generated code to make them fit the guidelines.</span></span>  
  
## <a name="layout-conventions"></a><span data-ttu-id="c685a-114">Convenzioni di layout</span><span class="sxs-lookup"><span data-stu-id="c685a-114">Layout Conventions</span></span>  
  
-   <span data-ttu-id="c685a-115">Inserire le tabulazioni come spazi e utilizzare i rientri con rientri di quattro spazi.</span><span class="sxs-lookup"><span data-stu-id="c685a-115">Insert tabs as spaces, and use smart indenting with four-space indents.</span></span>  
  
-   <span data-ttu-id="c685a-116">Uso **riformatta il listato riformattazione del codice** per riformattare il codice nell'editor del codice.</span><span class="sxs-lookup"><span data-stu-id="c685a-116">Use **Pretty listing (reformatting) of code** to reformat your code in the code editor.</span></span> <span data-ttu-id="c685a-117">Per altre informazioni, vedere [opzioni, Editor di testo, base (Visual Basic)](/visualstudio/ide/reference/options-text-editor-basic-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="c685a-117">For more information, see [Options, Text Editor, Basic (Visual Basic)](/visualstudio/ide/reference/options-text-editor-basic-visual-basic).</span></span>  
  
-   <span data-ttu-id="c685a-118">Usare una sola istruzione per riga.</span><span class="sxs-lookup"><span data-stu-id="c685a-118">Use only one statement per line.</span></span> <span data-ttu-id="c685a-119">Non usare il carattere separatore di riga Visual Basic (:).</span><span class="sxs-lookup"><span data-stu-id="c685a-119">Don't use the Visual Basic line separator character (:).</span></span>  
  
-   <span data-ttu-id="c685a-120">Evitare di usare il carattere di continuazione di riga esplicito "_" a favore di continuazione riga implicita, ogni volta che il linguaggio lo consente.</span><span class="sxs-lookup"><span data-stu-id="c685a-120">Avoid using the explicit line continuation character "_" in favor of implicit line continuation wherever the language allows it.</span></span>  
  
-   <span data-ttu-id="c685a-121">Usare una sola dichiarazione per riga.</span><span class="sxs-lookup"><span data-stu-id="c685a-121">Use only one declaration per line.</span></span>  
  
-   <span data-ttu-id="c685a-122">Se **riformatta il listato riformattazione del codice** non le righe di continuazione formato automaticamente, manualmente rientro continuazione le righe di una tabulazione.</span><span class="sxs-lookup"><span data-stu-id="c685a-122">If **Pretty listing (reformatting) of code** doesn't format continuation lines automatically, manually indent continuation lines one tab stop.</span></span> <span data-ttu-id="c685a-123">Tuttavia, sempre Allinea a sinistra-elementi in un elenco.</span><span class="sxs-lookup"><span data-stu-id="c685a-123">However, always left-align items in a list.</span></span>  
  
    ```  
    a As Integer,  
    b As Integer  
    ```  
  
-   <span data-ttu-id="c685a-124">Aggiungere almeno una riga vuota tra le definizioni di metodo e proprietà.</span><span class="sxs-lookup"><span data-stu-id="c685a-124">Add at least one blank line between method and property definitions.</span></span>  
  
## <a name="commenting-conventions"></a><span data-ttu-id="c685a-125">Convenzioni relative ai commenti</span><span class="sxs-lookup"><span data-stu-id="c685a-125">Commenting Conventions</span></span>  
  
-   <span data-ttu-id="c685a-126">Inserire i commenti su una riga separata anziché alla fine di una riga di codice.</span><span class="sxs-lookup"><span data-stu-id="c685a-126">Put comments on a separate line instead of at the end of a line of code.</span></span>  
  
-   <span data-ttu-id="c685a-127">Avviare il testo di commento con una lettera maiuscola e terminarlo con un punto.</span><span class="sxs-lookup"><span data-stu-id="c685a-127">Start comment text with an uppercase letter, and end comment text with a period.</span></span>  
  
-   <span data-ttu-id="c685a-128">Inserisci uno spazio tra il delimitatore di commento (') e il testo del commento.</span><span class="sxs-lookup"><span data-stu-id="c685a-128">Insert one space between the comment delimiter (') and the comment text.</span></span>  
  
     [!code-vb[VbVbalrGuidelines#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#2)]  
  
-   <span data-ttu-id="c685a-129">Non racchiudere i commenti con blocchi formattati di asterischi.</span><span class="sxs-lookup"><span data-stu-id="c685a-129">Do not surround comments with formatted blocks of asterisks.</span></span>  
  
## <a name="program-structure"></a><span data-ttu-id="c685a-130">Struttura del programma</span><span class="sxs-lookup"><span data-stu-id="c685a-130">Program Structure</span></span>  
  
-   <span data-ttu-id="c685a-131">Quando si usa la `Main` metodo, utilizzare il costrutto predefinito per le nuove applicazioni console e usare `My` per gli argomenti della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="c685a-131">When you use the `Main` method, use the default construct for new console applications, and use `My` for command-line arguments.</span></span>  
  
     [!code-vb[VbVbalrGuidelines#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#3)]  
  
## <a name="language-guidelines"></a><span data-ttu-id="c685a-132">Linee guida della lingua</span><span class="sxs-lookup"><span data-stu-id="c685a-132">Language Guidelines</span></span>  
  
### <a name="string-data-type"></a><span data-ttu-id="c685a-133">Tipo di dati String</span><span class="sxs-lookup"><span data-stu-id="c685a-133">String Data Type</span></span>  
  
-   <span data-ttu-id="c685a-134">Per concatenare le stringhe, usare una e commerciale (&).</span><span class="sxs-lookup"><span data-stu-id="c685a-134">To concatenate strings, use an ampersand (&).</span></span>  
  
     [!code-vb[VbVbalrGuidelines#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#4)]  
  
-   <span data-ttu-id="c685a-135">Per accodare stringhe nei cicli, usare il <xref:System.Text.StringBuilder> oggetto.</span><span class="sxs-lookup"><span data-stu-id="c685a-135">To append strings in loops, use the <xref:System.Text.StringBuilder> object.</span></span>  
  
     [!code-vb[VbVbalrGuidelines#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#5)]  
  
### <a name="relaxed-delegates-in-event-handlers"></a><span data-ttu-id="c685a-136">Delegati di tipo relaxed nei gestori eventi</span><span class="sxs-lookup"><span data-stu-id="c685a-136">Relaxed Delegates in Event Handlers</span></span>  
 <span data-ttu-id="c685a-137">Non qualificare esplicitamente gli argomenti (Object ed EventArgs) ai gestori di eventi.</span><span class="sxs-lookup"><span data-stu-id="c685a-137">Do not explicitly qualify the arguments (Object and EventArgs) to event handlers.</span></span> <span data-ttu-id="c685a-138">Se non si usa gli argomenti dell'evento che vengono passati a un evento (ad esempio mittente come Object e come EventArgs), usare delegati di tipo relaxed e omettere gli argomenti dell'evento nel codice:</span><span class="sxs-lookup"><span data-stu-id="c685a-138">If you are not using the event arguments that are passed to an event (for example, sender as Object, e as EventArgs), use relaxed delegates, and leave out the event arguments in your code:</span></span>  
  
 [!code-vb[VbVbalrGuidelines#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#7)]  
  
### <a name="unsigned-data-type"></a><span data-ttu-id="c685a-139">Tipi di dati non firmati</span><span class="sxs-lookup"><span data-stu-id="c685a-139">Unsigned Data Type</span></span>  
  
-   <span data-ttu-id="c685a-140">Usare `Integer` anziché tipi senza segno, tranne quando sono necessari.</span><span class="sxs-lookup"><span data-stu-id="c685a-140">Use `Integer` rather than unsigned types, except where they are necessary.</span></span>  
  
### <a name="arrays"></a><span data-ttu-id="c685a-141">Matrici</span><span class="sxs-lookup"><span data-stu-id="c685a-141">Arrays</span></span>  
  
-   <span data-ttu-id="c685a-142">Utilizzare la sintassi breve quando si inizializzano matrici nella riga della dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="c685a-142">Use the short syntax when you initialize arrays on the declaration line.</span></span> <span data-ttu-id="c685a-143">Ad esempio, usare la sintassi seguente.</span><span class="sxs-lookup"><span data-stu-id="c685a-143">For example, use the following syntax.</span></span>  
  
     [!code-vb[VbVbalrGuidelines#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#8)]  
  
     <span data-ttu-id="c685a-144">Non utilizzare la sintassi seguente.</span><span class="sxs-lookup"><span data-stu-id="c685a-144">Do not use the following syntax.</span></span>  
  
     [!code-vb[VbVbalrGuidelines#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#9)]  
  
-   <span data-ttu-id="c685a-145">Inserire l'identificatore di matrici nel tipo e non sulla variabile.</span><span class="sxs-lookup"><span data-stu-id="c685a-145">Put the array designator on the type, not on the variable.</span></span> <span data-ttu-id="c685a-146">Ad esempio, usare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="c685a-146">For example, use the following syntax:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#11)]  
  
     <span data-ttu-id="c685a-147">Non utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="c685a-147">Do not use the following syntax:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#10)]  
  
-   <span data-ttu-id="c685a-148">Usare la sintassi {} quando si dichiarano e inizializzano le matrici di tipi di dati di base.</span><span class="sxs-lookup"><span data-stu-id="c685a-148">Use the { } syntax when you declare and initialize arrays of basic data types.</span></span> <span data-ttu-id="c685a-149">Ad esempio, usare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="c685a-149">For example, use the following syntax:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#12](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_10.vb)]  
  
     <span data-ttu-id="c685a-150">Non utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="c685a-150">Do not use the following syntax:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#13)]  
  
### <a name="use-the-with-keyword"></a><span data-ttu-id="c685a-151">Usare la parola chiave</span><span class="sxs-lookup"><span data-stu-id="c685a-151">Use the With Keyword</span></span>  
 <span data-ttu-id="c685a-152">Quando si apporta una serie di chiamate a un oggetto, è consigliabile usare il `With` (parola chiave):</span><span class="sxs-lookup"><span data-stu-id="c685a-152">When you make a series of calls to one object, consider using the `With` keyword:</span></span>  
  
 [!code-vb[VbVbalrGuidelines#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#15)]  
  
### <a name="use-the-trycatch-and-using-statements-when-you-use-exception-handling"></a><span data-ttu-id="c685a-153">Utilizzare l'istruzione Try... Catch e le istruzioni Using quando si usa la gestione delle eccezioni</span><span class="sxs-lookup"><span data-stu-id="c685a-153">Use the Try...Catch and Using Statements when you use Exception Handling</span></span>  
 <span data-ttu-id="c685a-154">Non usare la proprietà `On Error Goto`.</span><span class="sxs-lookup"><span data-stu-id="c685a-154">Do not use `On Error Goto`.</span></span>  
  
### <a name="use-the-isnot-keyword"></a><span data-ttu-id="c685a-155">Usare la parola chiave IsNot</span><span class="sxs-lookup"><span data-stu-id="c685a-155">Use the IsNot Keyword</span></span>  
 <span data-ttu-id="c685a-156">Usare la `IsNot` parola chiave anziché `Not...Is Nothing`.</span><span class="sxs-lookup"><span data-stu-id="c685a-156">Use the `IsNot` keyword instead of `Not...Is Nothing`.</span></span>  
  
### <a name="new-keyword"></a><span data-ttu-id="c685a-157">Nuova parola chiave</span><span class="sxs-lookup"><span data-stu-id="c685a-157">New Keyword</span></span>  
  
-   <span data-ttu-id="c685a-158">Utilizzare la creazione di istanze breve.</span><span class="sxs-lookup"><span data-stu-id="c685a-158">Use short instantiation.</span></span> <span data-ttu-id="c685a-159">Ad esempio, usare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="c685a-159">For example, use the following syntax:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#21)]  
  
     <span data-ttu-id="c685a-160">La riga precedente equivale al seguente:</span><span class="sxs-lookup"><span data-stu-id="c685a-160">The preceding line is equivalent to this:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#22)]  
  
-   <span data-ttu-id="c685a-161">Usare gli inizializzatori di oggetto per i nuovi oggetti anziché il costruttore senza parametri:</span><span class="sxs-lookup"><span data-stu-id="c685a-161">Use object initializers for new objects instead of the parameterless constructor:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#23)]  
  
### <a name="event-handling"></a><span data-ttu-id="c685a-162">Gestione di eventi</span><span class="sxs-lookup"><span data-stu-id="c685a-162">Event Handling</span></span>  
  
-   <span data-ttu-id="c685a-163">Uso `Handles` anziché `AddHandler`:</span><span class="sxs-lookup"><span data-stu-id="c685a-163">Use `Handles` rather than `AddHandler`:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#24)]  
  
-   <span data-ttu-id="c685a-164">Usare `AddressOf`e non creare un'istanza del delegato in modo esplicito:</span><span class="sxs-lookup"><span data-stu-id="c685a-164">Use `AddressOf`, and do not instantiate the delegate explicitly:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#25)]  
  
-   <span data-ttu-id="c685a-165">Quando si definisce un evento, usare la sintassi breve e consentire al compilatore di definire il delegato:</span><span class="sxs-lookup"><span data-stu-id="c685a-165">When you define an event, use the short syntax, and let the compiler define the delegate:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#26)]  
  
-   <span data-ttu-id="c685a-166">Non verificare se un evento è `Nothing` (null) prima di chiamare il `RaiseEvent` (metodo).</span><span class="sxs-lookup"><span data-stu-id="c685a-166">Do not verify whether an event is `Nothing` (null) before you call the `RaiseEvent` method.</span></span> <span data-ttu-id="c685a-167">`RaiseEvent` verifica la presenza di `Nothing` prima che venga generato l'evento.</span><span class="sxs-lookup"><span data-stu-id="c685a-167">`RaiseEvent` checks for `Nothing` before it raises the event.</span></span>  
  
### <a name="using-shared-members"></a><span data-ttu-id="c685a-168">Utilizzo di membri condivisi</span><span class="sxs-lookup"><span data-stu-id="c685a-168">Using Shared Members</span></span>  
 <span data-ttu-id="c685a-169">Chiamare `Shared` membri tramite il nome della classe, non da una variabile di istanza.</span><span class="sxs-lookup"><span data-stu-id="c685a-169">Call `Shared` members by using the class name, not from an instance variable.</span></span>  
  
### <a name="use-xml-literals"></a><span data-ttu-id="c685a-170">Usare valori letterali XML</span><span class="sxs-lookup"><span data-stu-id="c685a-170">Use XML Literals</span></span>  
 <span data-ttu-id="c685a-171">Valori letterali XML semplificano le attività più comuni che si verificano quando si lavora con XML (ad esempio, query, trasformazione e caricamento).</span><span class="sxs-lookup"><span data-stu-id="c685a-171">XML literals simplify the most common tasks that you encounter when you work with XML (for example, load, query, and transform).</span></span> <span data-ttu-id="c685a-172">Quando si sviluppa con XML, seguire queste linee guida:</span><span class="sxs-lookup"><span data-stu-id="c685a-172">When you develop with XML, follow these guidelines:</span></span>  
  
-   <span data-ttu-id="c685a-173">Usare valori letterali XML per creare documenti e frammenti anziché chiamare direttamente API XML XML.</span><span class="sxs-lookup"><span data-stu-id="c685a-173">Use XML literals to create XML documents and fragments instead of calling XML APIs directly.</span></span>  
  
-   <span data-ttu-id="c685a-174">Importare spazi dei nomi XML a livello di file o progetto in modo da sfruttare le ottimizzazioni delle prestazioni per i valori letterali XML.</span><span class="sxs-lookup"><span data-stu-id="c685a-174">Import XML namespaces at the file or project level to take advantage of the performance optimizations for XML literals.</span></span>  
  
-   <span data-ttu-id="c685a-175">Usare le proprietà axis XML per accedere agli elementi e attributi in un documento XML.</span><span class="sxs-lookup"><span data-stu-id="c685a-175">Use the XML axis properties to access elements and attributes in an XML document.</span></span>  
  
-   <span data-ttu-id="c685a-176">Utilizzare le espressioni incorporate per includere i valori e creare XML da valori esistenti anziché con chiamate all'API, ad esempio il `Add` metodo:</span><span class="sxs-lookup"><span data-stu-id="c685a-176">Use embedded expressions to include values and to create XML from existing values instead of using API calls such as the `Add` method:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#27)]  
  
### <a name="linq-queries"></a><span data-ttu-id="c685a-177">Query LINQ</span><span class="sxs-lookup"><span data-stu-id="c685a-177">LINQ Queries</span></span>  
  
-   <span data-ttu-id="c685a-178">Usare nomi significativi per le variabili di query:</span><span class="sxs-lookup"><span data-stu-id="c685a-178">Use meaningful names for query variables:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#28)]  
  
-   <span data-ttu-id="c685a-179">Fornire nomi per gli elementi in una query per assicurarsi che i nomi di proprietà di tipi anonimi siano scritti correttamente in maiuscolo usando la convenzione Pascal maiuscole e minuscole:</span><span class="sxs-lookup"><span data-stu-id="c685a-179">Provide names for elements in a query to make sure that property names of anonymous types are correctly capitalized using Pascal casing:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#29)]  
  
-   <span data-ttu-id="c685a-180">Rinominare le proprietà quando i nomi delle proprietà nel risultato potrebbero risultare ambigui.</span><span class="sxs-lookup"><span data-stu-id="c685a-180">Rename properties when the property names in the result would be ambiguous.</span></span> <span data-ttu-id="c685a-181">Ad esempio, se la query restituisce un cliente, nome e un ID ordine, rinominarli anziché lasciarli come `Name` e `ID` nel risultato:</span><span class="sxs-lookup"><span data-stu-id="c685a-181">For example, if your query returns a customer name and an order ID, rename them instead of leaving them as `Name` and `ID` in the result:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#30)]  
  
-   <span data-ttu-id="c685a-182">Usare l'inferenza del tipo nella dichiarazione di variabili di query e variabili di intervallo:</span><span class="sxs-lookup"><span data-stu-id="c685a-182">Use type inference in the declaration of query variables and range variables:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#31)]  
  
-   <span data-ttu-id="c685a-183">Allineare le clausole di query sotto la `From` istruzione:</span><span class="sxs-lookup"><span data-stu-id="c685a-183">Align query clauses under the `From` statement:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#32)]  
  
-   <span data-ttu-id="c685a-184">Usare `Where` clausole prima delle altre clausole di query in modo che successive clausole di query agiscano sul set di dati filtrato:</span><span class="sxs-lookup"><span data-stu-id="c685a-184">Use `Where` clauses before other query clauses so that later query clauses operate on the filtered set of data:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#33)]  
  
-   <span data-ttu-id="c685a-185">Usare la `Join` clausola definire in modo esplicito un'operazione di join invece di usare il `Where` clausola per definire in modo implicito un'operazione di join:</span><span class="sxs-lookup"><span data-stu-id="c685a-185">Use the `Join` clause to explicitly define a join operation instead of using the `Where` clause to implicitly define a join operation:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#34)]  
  
## <a name="see-also"></a><span data-ttu-id="c685a-186">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c685a-186">See also</span></span>
- [<span data-ttu-id="c685a-187">Linee guida per la generazione di codice sicuro</span><span class="sxs-lookup"><span data-stu-id="c685a-187">Secure Coding Guidelines</span></span>](../../../standard/security/secure-coding-guidelines.md)
