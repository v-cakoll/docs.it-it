---
title: Convenzioni di codifica di Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- coding conventions [Visual Basic], Visual Basic
- examples [Visual Basic], coding conventions
- Visual Basic code, conventions
ms.assetid: c1df130b-fec6-49a5-becf-0a7e494a1d0f
ms.openlocfilehash: b686747b46529b53b0802a7deb38b5b4949f4d5e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33655361"
---
# <a name="visual-basic-coding-conventions"></a><span data-ttu-id="0596b-102">Convenzioni di codifica di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0596b-102">Visual Basic Coding Conventions</span></span>
<span data-ttu-id="0596b-103">Microsoft consente di sviluppare gli esempi e documentazione che seguire le istruzioni in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="0596b-103">Microsoft develops samples and documentation that follow the guidelines in this topic.</span></span> <span data-ttu-id="0596b-104">Se si seguono le stesse convenzioni di codifica, si potrebbero ottenere i vantaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="0596b-104">If you follow the same coding conventions, you may gain the following benefits:</span></span>  
  
-   <span data-ttu-id="0596b-105">Il codice avrà un aspetto coerenza, in modo che chi legge possa concentrarsi meglio sul contenuto, non di layout.</span><span class="sxs-lookup"><span data-stu-id="0596b-105">Your code will have a consistent look, so that readers can better focus on content, not layout.</span></span>  
  
-   <span data-ttu-id="0596b-106">Lettori di comprendere il codice più rapidamente perché sono possibile basarsi su presupposti basati sulle esperienze precedenti.</span><span class="sxs-lookup"><span data-stu-id="0596b-106">Readers understand your code more quickly because they can make assumptions based on previous experience.</span></span>  
  
-   <span data-ttu-id="0596b-107">È possibile copiare, modificare e gestire più facilmente il codice.</span><span class="sxs-lookup"><span data-stu-id="0596b-107">You can copy, change, and maintain the code more easily.</span></span>  
  
-   <span data-ttu-id="0596b-108">Per garantire che il codice viene illustrato "procedure consigliate" per Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="0596b-108">You help ensure that your code demonstrates "best practices" for Visual Basic.</span></span>  
  
## <a name="naming-conventions"></a><span data-ttu-id="0596b-109">Convenzioni di denominazione</span><span class="sxs-lookup"><span data-stu-id="0596b-109">Naming Conventions</span></span>  
  
-   <span data-ttu-id="0596b-110">Per informazioni sulle linee guida di denominazione, vedere [convenzioni di denominazione per](../../../standard/design-guidelines/naming-guidelines.md) argomento.</span><span class="sxs-lookup"><span data-stu-id="0596b-110">For information about naming guidelines, see [Naming Guidelines](../../../standard/design-guidelines/naming-guidelines.md) topic.</span></span>  
  
-   <span data-ttu-id="0596b-111">Non utilizzare "My" o "my" come parte di un nome di variabile.</span><span class="sxs-lookup"><span data-stu-id="0596b-111">Do not use "My" or "my" as part of a variable name.</span></span> <span data-ttu-id="0596b-112">Questa procedura crea confusione con i `My` oggetti.</span><span class="sxs-lookup"><span data-stu-id="0596b-112">This practice creates confusion with the `My` objects.</span></span>  
  
-   <span data-ttu-id="0596b-113">Non è necessario modificare i nomi degli oggetti nel codice generato automaticamente per adattare le linee guida.</span><span class="sxs-lookup"><span data-stu-id="0596b-113">You do not have to change the names of objects in auto-generated code to make them fit the guidelines.</span></span>  
  
## <a name="layout-conventions"></a><span data-ttu-id="0596b-114">Convenzioni di layout</span><span class="sxs-lookup"><span data-stu-id="0596b-114">Layout Conventions</span></span>  
  
-   <span data-ttu-id="0596b-115">Inserire le schede come spazi e utilizzare rientri intelligenti con rientri di quattro spazi.</span><span class="sxs-lookup"><span data-stu-id="0596b-115">Insert tabs as spaces, and use smart indenting with four-space indents.</span></span>  
  
-   <span data-ttu-id="0596b-116">Utilizzare **listato di codice (riformattazione) di** per riformattare il codice nell'editor di codice.</span><span class="sxs-lookup"><span data-stu-id="0596b-116">Use **Pretty listing (reformatting) of code** to reformat your code in the code editor.</span></span> <span data-ttu-id="0596b-117">Per ulteriori informazioni, vedere [opzioni, Editor di testo, base (Visual Basic)](/visualstudio/ide/reference/options-text-editor-basic-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="0596b-117">For more information, see [Options, Text Editor, Basic (Visual Basic)](/visualstudio/ide/reference/options-text-editor-basic-visual-basic).</span></span>  
  
-   <span data-ttu-id="0596b-118">Utilizzare una sola istruzione per riga.</span><span class="sxs-lookup"><span data-stu-id="0596b-118">Use only one statement per line.</span></span> <span data-ttu-id="0596b-119">Non utilizzare il carattere separatore di riga Visual Basic (:).</span><span class="sxs-lookup"><span data-stu-id="0596b-119">Don't use the Visual Basic line separator character (:).</span></span>  
  
-   <span data-ttu-id="0596b-120">Evitare di utilizzare il carattere di continuazione di riga esplicite "_" a favore di continuazione di riga implicita, ogni volta che ne consente la lingua.</span><span class="sxs-lookup"><span data-stu-id="0596b-120">Avoid using the explicit line continuation character "_" in favor of implicit line continuation wherever the language allows it.</span></span>  
  
-   <span data-ttu-id="0596b-121">Utilizzare una sola dichiarazione per riga.</span><span class="sxs-lookup"><span data-stu-id="0596b-121">Use only one declaration per line.</span></span>  
  
-   <span data-ttu-id="0596b-122">Se **listato di codice (riformattazione) di** non le righe di continuazione formato automaticamente, manualmente rientro continuazione righe di una tabulazione.</span><span class="sxs-lookup"><span data-stu-id="0596b-122">If **Pretty listing (reformatting) of code** doesn't format continuation lines automatically, manually indent continuation lines one tab stop.</span></span> <span data-ttu-id="0596b-123">Tuttavia, sempre allineare a sinistra in un elenco di elementi.</span><span class="sxs-lookup"><span data-stu-id="0596b-123">However, always left-align items in a list.</span></span>  
  
    ```  
    a As Integer,  
    b As Integer  
    ```  
  
-   <span data-ttu-id="0596b-124">Aggiungere almeno una riga vuota tra le definizioni di metodo e proprietà.</span><span class="sxs-lookup"><span data-stu-id="0596b-124">Add at least one blank line between method and property definitions.</span></span>  
  
## <a name="commenting-conventions"></a><span data-ttu-id="0596b-125">Convenzioni relative ai commenti</span><span class="sxs-lookup"><span data-stu-id="0596b-125">Commenting Conventions</span></span>  
  
-   <span data-ttu-id="0596b-126">Inserire i commenti su una riga separata anziché alla fine di una riga di codice.</span><span class="sxs-lookup"><span data-stu-id="0596b-126">Put comments on a separate line instead of at the end of a line of code.</span></span>  
  
-   <span data-ttu-id="0596b-127">Avviare il testo di commento con una lettera maiuscola e testo del commento finale con un punto.</span><span class="sxs-lookup"><span data-stu-id="0596b-127">Start comment text with an uppercase letter, and end comment text with a period.</span></span>  
  
-   <span data-ttu-id="0596b-128">Inserire uno spazio tra il delimitatore di commento (') e il testo del commento.</span><span class="sxs-lookup"><span data-stu-id="0596b-128">Insert one space between the comment delimiter (') and the comment text.</span></span>  
  
     [!code-vb[VbVbalrGuidelines#2](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_1.vb)]  
  
-   <span data-ttu-id="0596b-129">Non racchiudere i commenti con blocchi formattati di asterischi.</span><span class="sxs-lookup"><span data-stu-id="0596b-129">Do not surround comments with formatted blocks of asterisks.</span></span>  
  
## <a name="program-structure"></a><span data-ttu-id="0596b-130">Struttura del programma</span><span class="sxs-lookup"><span data-stu-id="0596b-130">Program Structure</span></span>  
  
-   <span data-ttu-id="0596b-131">Quando si utilizza il `Main` metodo, utilizzare il costrutto predefinito per le nuove applicazioni console e `My` per gli argomenti della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="0596b-131">When you use the `Main` method, use the default construct for new console applications, and use `My` for command-line arguments.</span></span>  
  
     [!code-vb[VbVbalrGuidelines#3](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_2.vb)]  
  
## <a name="language-guidelines"></a><span data-ttu-id="0596b-132">Linee guida della lingua</span><span class="sxs-lookup"><span data-stu-id="0596b-132">Language Guidelines</span></span>  
  
### <a name="string-data-type"></a><span data-ttu-id="0596b-133">Tipo di dati String</span><span class="sxs-lookup"><span data-stu-id="0596b-133">String Data Type</span></span>  
  
-   <span data-ttu-id="0596b-134">Per concatenare stringhe, usare una e commerciale (&).</span><span class="sxs-lookup"><span data-stu-id="0596b-134">To concatenate strings, use an ampersand (&).</span></span>  
  
     [!code-vb[VbVbalrGuidelines#4](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_3.vb)]  
  
-   <span data-ttu-id="0596b-135">Per accodare stringhe nei cicli, utilizzare il <xref:System.Text.StringBuilder> oggetto.</span><span class="sxs-lookup"><span data-stu-id="0596b-135">To append strings in loops, use the <xref:System.Text.StringBuilder> object.</span></span>  
  
     [!code-vb[VbVbalrGuidelines#5](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_4.vb)]  
  
### <a name="relaxed-delegates-in-event-handlers"></a><span data-ttu-id="0596b-136">Delegati di tipo relaxed nei gestori eventi</span><span class="sxs-lookup"><span data-stu-id="0596b-136">Relaxed Delegates in Event Handlers</span></span>  
 <span data-ttu-id="0596b-137">Non qualificare in modo esplicito gli argomenti (oggetto ed EventArgs) ai gestori di eventi.</span><span class="sxs-lookup"><span data-stu-id="0596b-137">Do not explicitly qualify the arguments (Object and EventArgs) to event handlers.</span></span> <span data-ttu-id="0596b-138">Se non si utilizza gli argomenti dell'evento che vengono passati a un evento (ad esempio mittente come oggetto, e come EventArgs), utilizzare delegati di tipo relaxed e omettere gli argomenti dell'evento nel codice:</span><span class="sxs-lookup"><span data-stu-id="0596b-138">If you are not using the event arguments that are passed to an event (for example, sender as Object, e as EventArgs), use relaxed delegates, and leave out the event arguments in your code:</span></span>  
  
 [!code-vb[VbVbalrGuidelines#7](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_5.vb)]  
  
### <a name="unsigned-data-type"></a><span data-ttu-id="0596b-139">Tipi di dati non firmati</span><span class="sxs-lookup"><span data-stu-id="0596b-139">Unsigned Data Type</span></span>  
  
-   <span data-ttu-id="0596b-140">Utilizzare `Integer` anziché tipi non firmati, tranne quando sono necessari.</span><span class="sxs-lookup"><span data-stu-id="0596b-140">Use `Integer` rather than unsigned types, except where they are necessary.</span></span>  
  
### <a name="arrays"></a><span data-ttu-id="0596b-141">Matrici</span><span class="sxs-lookup"><span data-stu-id="0596b-141">Arrays</span></span>  
  
-   <span data-ttu-id="0596b-142">Utilizzare la sintassi breve, quando si inizializzano le matrici nella riga della dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="0596b-142">Use the short syntax when you initialize arrays on the declaration line.</span></span> <span data-ttu-id="0596b-143">Ad esempio, utilizzare la sintassi seguente.</span><span class="sxs-lookup"><span data-stu-id="0596b-143">For example, use the following syntax.</span></span>  
  
     [!code-vb[VbVbalrGuidelines#8](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_6.vb)]  
  
     <span data-ttu-id="0596b-144">Non utilizzare la sintassi seguente.</span><span class="sxs-lookup"><span data-stu-id="0596b-144">Do not use the following syntax.</span></span>  
  
     [!code-vb[VbVbalrGuidelines#9](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_7.vb)]  
  
-   <span data-ttu-id="0596b-145">Il tipo e non la variabile, inserire l'identificatore di matrice.</span><span class="sxs-lookup"><span data-stu-id="0596b-145">Put the array designator on the type, not on the variable.</span></span> <span data-ttu-id="0596b-146">Ad esempio, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="0596b-146">For example, use the following syntax:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#11](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_8.vb)]  
  
     <span data-ttu-id="0596b-147">Non utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="0596b-147">Do not use the following syntax:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#10](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_9.vb)]  
  
-   <span data-ttu-id="0596b-148">Quando è necessario dichiarare e inizializzare le matrici di tipi di dati di base, utilizzare la sintassi di {}.</span><span class="sxs-lookup"><span data-stu-id="0596b-148">Use the { } syntax when you declare and initialize arrays of basic data types.</span></span> <span data-ttu-id="0596b-149">Ad esempio, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="0596b-149">For example, use the following syntax:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#12](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_10.vb)]  
  
     <span data-ttu-id="0596b-150">Non utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="0596b-150">Do not use the following syntax:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#13](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_11.vb)]  
  
### <a name="use-the-with-keyword"></a><span data-ttu-id="0596b-151">Utilizzare la parola chiave</span><span class="sxs-lookup"><span data-stu-id="0596b-151">Use the With Keyword</span></span>  
 <span data-ttu-id="0596b-152">Quando si apporta una serie di chiamate a un oggetto, è consigliabile utilizzare il `With` (parola chiave):</span><span class="sxs-lookup"><span data-stu-id="0596b-152">When you make a series of calls to one object, consider using the `With` keyword:</span></span>  
  
 [!code-vb[VbVbalrGuidelines#15](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_12.vb)]  
  
### <a name="use-the-trycatch-and-using-statements-when-you-use-exception-handling"></a><span data-ttu-id="0596b-153">Utilizzare l'istruzione Try... Catch e utilizzo di istruzioni quando si utilizza Gestione delle eccezioni</span><span class="sxs-lookup"><span data-stu-id="0596b-153">Use the Try...Catch and Using Statements when you use Exception Handling</span></span>  
 <span data-ttu-id="0596b-154">Non utilizzare `On Error Goto`.</span><span class="sxs-lookup"><span data-stu-id="0596b-154">Do not use `On Error Goto`.</span></span>  
  
### <a name="use-the-isnot-keyword"></a><span data-ttu-id="0596b-155">Utilizzare la parola chiave IsNot</span><span class="sxs-lookup"><span data-stu-id="0596b-155">Use the IsNot Keyword</span></span>  
 <span data-ttu-id="0596b-156">Utilizzare il `IsNot` (parola chiave) anziché `Not...Is Nothing`.</span><span class="sxs-lookup"><span data-stu-id="0596b-156">Use the `IsNot` keyword instead of `Not...Is Nothing`.</span></span>  
  
### <a name="new-keyword"></a><span data-ttu-id="0596b-157">Nuova parola chiave</span><span class="sxs-lookup"><span data-stu-id="0596b-157">New Keyword</span></span>  
  
-   <span data-ttu-id="0596b-158">Utilizzare la creazione di istanze breve.</span><span class="sxs-lookup"><span data-stu-id="0596b-158">Use short instantiation.</span></span> <span data-ttu-id="0596b-159">Ad esempio, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="0596b-159">For example, use the following syntax:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#21](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_13.vb)]  
  
     <span data-ttu-id="0596b-160">La riga precedente è equivalente a questa:</span><span class="sxs-lookup"><span data-stu-id="0596b-160">The preceding line is equivalent to this:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#22](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_14.vb)]  
  
-   <span data-ttu-id="0596b-161">Usare gli inizializzatori di oggetto per i nuovi oggetti anziché il costruttore senza parametri:</span><span class="sxs-lookup"><span data-stu-id="0596b-161">Use object initializers for new objects instead of the parameterless constructor:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#23](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_15.vb)]  
  
### <a name="event-handling"></a><span data-ttu-id="0596b-162">Gestione di eventi</span><span class="sxs-lookup"><span data-stu-id="0596b-162">Event Handling</span></span>  
  
-   <span data-ttu-id="0596b-163">Utilizzare `Handles` anziché `AddHandler`:</span><span class="sxs-lookup"><span data-stu-id="0596b-163">Use `Handles` rather than `AddHandler`:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#24](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_16.vb)]  
  
-   <span data-ttu-id="0596b-164">Utilizzare `AddressOf`e non creare un'istanza di delegato in modo esplicito:</span><span class="sxs-lookup"><span data-stu-id="0596b-164">Use `AddressOf`, and do not instantiate the delegate explicitly:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#25](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_17.vb)]  
  
-   <span data-ttu-id="0596b-165">Quando si definisce un evento, utilizzare la sintassi breve e permettere al compilatore di definire il delegato:</span><span class="sxs-lookup"><span data-stu-id="0596b-165">When you define an event, use the short syntax, and let the compiler define the delegate:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#26](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_18.vb)]  
  
-   <span data-ttu-id="0596b-166">Verifica se un evento è `Nothing` (null) prima di chiamare il `RaiseEvent` metodo.</span><span class="sxs-lookup"><span data-stu-id="0596b-166">Do not verify whether an event is `Nothing` (null) before you call the `RaiseEvent` method.</span></span> <span data-ttu-id="0596b-167">`RaiseEvent` verifica la presenza di `Nothing` prima che venga generato l'evento.</span><span class="sxs-lookup"><span data-stu-id="0596b-167">`RaiseEvent` checks for `Nothing` before it raises the event.</span></span>  
  
### <a name="using-shared-members"></a><span data-ttu-id="0596b-168">Utilizzo di membri condivisi</span><span class="sxs-lookup"><span data-stu-id="0596b-168">Using Shared Members</span></span>  
 <span data-ttu-id="0596b-169">Chiamare `Shared` membri tramite il nome della classe, non una variabile di istanza.</span><span class="sxs-lookup"><span data-stu-id="0596b-169">Call `Shared` members by using the class name, not from an instance variable.</span></span>  
  
### <a name="use-xml-literals"></a><span data-ttu-id="0596b-170">Utilizzare valori letterali XML</span><span class="sxs-lookup"><span data-stu-id="0596b-170">Use XML Literals</span></span>  
 <span data-ttu-id="0596b-171">Valori letterali XML semplificano le attività più comuni che si verificano quando si lavora con XML (ad esempio, query, trasformazione e caricamento).</span><span class="sxs-lookup"><span data-stu-id="0596b-171">XML literals simplify the most common tasks that you encounter when you work with XML (for example, load, query, and transform).</span></span> <span data-ttu-id="0596b-172">Quando si sviluppa con XML, attenersi alle seguenti indicazioni:</span><span class="sxs-lookup"><span data-stu-id="0596b-172">When you develop with XML, follow these guidelines:</span></span>  
  
-   <span data-ttu-id="0596b-173">Per creare documenti e frammenti anziché chiamare direttamente le API XML XML, utilizzare i valori letterali XML.</span><span class="sxs-lookup"><span data-stu-id="0596b-173">Use XML literals to create XML documents and fragments instead of calling XML APIs directly.</span></span>  
  
-   <span data-ttu-id="0596b-174">Importare gli spazi dei nomi XML a livello di file o progetto in modo da sfruttare le ottimizzazioni delle prestazioni per i valori letterali XML.</span><span class="sxs-lookup"><span data-stu-id="0596b-174">Import XML namespaces at the file or project level to take advantage of the performance optimizations for XML literals.</span></span>  
  
-   <span data-ttu-id="0596b-175">Utilizzare le proprietà axis XML per accedere agli elementi e attributi in un documento XML.</span><span class="sxs-lookup"><span data-stu-id="0596b-175">Use the XML axis properties to access elements and attributes in an XML document.</span></span>  
  
-   <span data-ttu-id="0596b-176">Utilizzare le espressioni incorporate per includere i valori e creare XML da valori esistenti anziché come chiamate API di `Add` metodo:</span><span class="sxs-lookup"><span data-stu-id="0596b-176">Use embedded expressions to include values and to create XML from existing values instead of using API calls such as the `Add` method:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#27](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_19.vb)]  
  
### <a name="linq-queries"></a><span data-ttu-id="0596b-177">Query LINQ</span><span class="sxs-lookup"><span data-stu-id="0596b-177">LINQ Queries</span></span>  
  
-   <span data-ttu-id="0596b-178">Utilizzare nomi significativi per le variabili di query:</span><span class="sxs-lookup"><span data-stu-id="0596b-178">Use meaningful names for query variables:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#28](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_20.vb)]  
  
-   <span data-ttu-id="0596b-179">Fornire i nomi per gli elementi in una query per assicurarsi che i nomi delle proprietà di tipi anonimi sono in modo corretto utilizzando la convenzione Pascal maiuscole e minuscole:</span><span class="sxs-lookup"><span data-stu-id="0596b-179">Provide names for elements in a query to make sure that property names of anonymous types are correctly capitalized using Pascal casing:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#29](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_21.vb)]  
  
-   <span data-ttu-id="0596b-180">Rinominare le proprietà quando i nomi delle proprietà nel risultato potrebbero risultare ambigui.</span><span class="sxs-lookup"><span data-stu-id="0596b-180">Rename properties when the property names in the result would be ambiguous.</span></span> <span data-ttu-id="0596b-181">Ad esempio, se la query restituisce un cliente, nome e un ID ordine, rinominarli anziché lasciarli come `Name` e `ID` nel risultato:</span><span class="sxs-lookup"><span data-stu-id="0596b-181">For example, if your query returns a customer name and an order ID, rename them instead of leaving them as `Name` and `ID` in the result:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#30](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_22.vb)]  
  
-   <span data-ttu-id="0596b-182">Usare l'inferenza del tipo nella dichiarazione di variabili di query e variabili di intervallo:</span><span class="sxs-lookup"><span data-stu-id="0596b-182">Use type inference in the declaration of query variables and range variables:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#31](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_23.vb)]  
  
-   <span data-ttu-id="0596b-183">Allineare le clausole di query sotto il `From` istruzione:</span><span class="sxs-lookup"><span data-stu-id="0596b-183">Align query clauses under the `From` statement:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#32](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_24.vb)]  
  
-   <span data-ttu-id="0596b-184">Utilizzare `Where` clausole prima delle altre clausole di query in modo che successive clausole di query agiscano su set di dati filtrati:</span><span class="sxs-lookup"><span data-stu-id="0596b-184">Use `Where` clauses before other query clauses so that later query clauses operate on the filtered set of data:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#33](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_25.vb)]  
  
-   <span data-ttu-id="0596b-185">Utilizzare il `Join` clausola definire in modo esplicito un'operazione di join anziché il `Where` clausola per definire in modo implicito un'operazione di join:</span><span class="sxs-lookup"><span data-stu-id="0596b-185">Use the `Join` clause to explicitly define a join operation instead of using the `Where` clause to implicitly define a join operation:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#34](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_26.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="0596b-186">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0596b-186">See Also</span></span>  
 [<span data-ttu-id="0596b-187">Linee guida per la generazione di codice sicuro</span><span class="sxs-lookup"><span data-stu-id="0596b-187">Secure Coding Guidelines</span></span>](../../../standard/security/secure-coding-guidelines.md)
