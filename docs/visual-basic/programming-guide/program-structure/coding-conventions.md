---
title: Convenzioni per la scrittura del codice
ms.date: 07/20/2015
helpviewer_keywords:
- coding conventions [Visual Basic], Visual Basic
- examples [Visual Basic], coding conventions
- Visual Basic code, conventions
ms.assetid: c1df130b-fec6-49a5-becf-0a7e494a1d0f
ms.openlocfilehash: 36cd3a927d2fdf197e6b496d9308fc43a555d59b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346160"
---
# <a name="visual-basic-coding-conventions"></a><span data-ttu-id="ace4e-102">Convenzioni di codifica di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ace4e-102">Visual Basic Coding Conventions</span></span>
<span data-ttu-id="ace4e-103">Microsoft sviluppa esempi e documentazione che seguono le linee guida in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="ace4e-103">Microsoft develops samples and documentation that follow the guidelines in this topic.</span></span> <span data-ttu-id="ace4e-104">Se si seguono le stesse convenzioni di codifica, è possibile ottenere i vantaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="ace4e-104">If you follow the same coding conventions, you may gain the following benefits:</span></span>  
  
- <span data-ttu-id="ace4e-105">Il codice avrà un aspetto coerente, in modo che i lettori possano concentrarsi meglio sul contenuto, non sul layout.</span><span class="sxs-lookup"><span data-stu-id="ace4e-105">Your code will have a consistent look, so that readers can better focus on content, not layout.</span></span>  
  
- <span data-ttu-id="ace4e-106">I reader comprendono il codice più rapidamente, perché possono creare presupposti in base all'esperienza precedente.</span><span class="sxs-lookup"><span data-stu-id="ace4e-106">Readers understand your code more quickly because they can make assumptions based on previous experience.</span></span>  
  
- <span data-ttu-id="ace4e-107">È possibile copiare, modificare e gestire il codice più facilmente.</span><span class="sxs-lookup"><span data-stu-id="ace4e-107">You can copy, change, and maintain the code more easily.</span></span>  
  
- <span data-ttu-id="ace4e-108">È possibile assicurarsi che il codice consenta di illustrare "procedure consigliate" per Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="ace4e-108">You help ensure that your code demonstrates "best practices" for Visual Basic.</span></span>  
  
## <a name="naming-conventions"></a><span data-ttu-id="ace4e-109">Convenzioni di denominazione</span><span class="sxs-lookup"><span data-stu-id="ace4e-109">Naming Conventions</span></span>  
  
- <span data-ttu-id="ace4e-110">Per informazioni sulle linee guida per la denominazione, vedere l'argomento [linee guida](../../../standard/design-guidelines/naming-guidelines.md) per la denominazione.</span><span class="sxs-lookup"><span data-stu-id="ace4e-110">For information about naming guidelines, see [Naming Guidelines](../../../standard/design-guidelines/naming-guidelines.md) topic.</span></span>  
  
- <span data-ttu-id="ace4e-111">Non usare "My" o "My" come parte del nome di una variabile.</span><span class="sxs-lookup"><span data-stu-id="ace4e-111">Do not use "My" or "my" as part of a variable name.</span></span> <span data-ttu-id="ace4e-112">Questa procedura consente di creare confusione con gli oggetti `My`.</span><span class="sxs-lookup"><span data-stu-id="ace4e-112">This practice creates confusion with the `My` objects.</span></span>  
  
- <span data-ttu-id="ace4e-113">Non è necessario modificare i nomi degli oggetti nel codice generato automaticamente per adattarli alle linee guida.</span><span class="sxs-lookup"><span data-stu-id="ace4e-113">You do not have to change the names of objects in auto-generated code to make them fit the guidelines.</span></span>  
  
## <a name="layout-conventions"></a><span data-ttu-id="ace4e-114">Convenzioni di layout</span><span class="sxs-lookup"><span data-stu-id="ace4e-114">Layout Conventions</span></span>  
  
- <span data-ttu-id="ace4e-115">Inserire le schede come spazi e utilizzare i rientri intelligenti con rientri di quattro spazi.</span><span class="sxs-lookup"><span data-stu-id="ace4e-115">Insert tabs as spaces, and use smart indenting with four-space indents.</span></span>  
  
- <span data-ttu-id="ace4e-116">Usare un **elenco semplice (riformattazione) del codice** per riformattare il codice nell'editor di codice.</span><span class="sxs-lookup"><span data-stu-id="ace4e-116">Use **Pretty listing (reformatting) of code** to reformat your code in the code editor.</span></span> <span data-ttu-id="ace4e-117">Per ulteriori informazioni, vedere [Opzioni, editor di testo, di base (Visual Basic)](/visualstudio/ide/reference/options-text-editor-basic-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="ace4e-117">For more information, see [Options, Text Editor, Basic (Visual Basic)](/visualstudio/ide/reference/options-text-editor-basic-visual-basic).</span></span>  
  
- <span data-ttu-id="ace4e-118">Usare una sola istruzione per riga.</span><span class="sxs-lookup"><span data-stu-id="ace4e-118">Use only one statement per line.</span></span> <span data-ttu-id="ace4e-119">Non usare il carattere separatore di riga Visual Basic (:).</span><span class="sxs-lookup"><span data-stu-id="ace4e-119">Don't use the Visual Basic line separator character (:).</span></span>  
  
- <span data-ttu-id="ace4e-120">Evitare di usare il carattere di continuazione di riga esplicito "_" a favore della continuazione di riga implicita laddove il linguaggio lo consente.</span><span class="sxs-lookup"><span data-stu-id="ace4e-120">Avoid using the explicit line continuation character "_" in favor of implicit line continuation wherever the language allows it.</span></span>  
  
- <span data-ttu-id="ace4e-121">Usare una sola dichiarazione per riga.</span><span class="sxs-lookup"><span data-stu-id="ace4e-121">Use only one declaration per line.</span></span>  
  
- <span data-ttu-id="ace4e-122">Se l' **elenco (riformattazione) del codice** non formatta automaticamente le righe di continuazione, rientrare manualmente le righe di continuazione una tabulazione.</span><span class="sxs-lookup"><span data-stu-id="ace4e-122">If **Pretty listing (reformatting) of code** doesn't format continuation lines automatically, manually indent continuation lines one tab stop.</span></span> <span data-ttu-id="ace4e-123">Tuttavia, allinea sempre gli elementi in un elenco.</span><span class="sxs-lookup"><span data-stu-id="ace4e-123">However, always left-align items in a list.</span></span>  
  
    ```vb  
    a As Integer,  
    b As Integer  
    ```  
  
- <span data-ttu-id="ace4e-124">Aggiungere almeno una riga vuota tra le definizioni di metodo e proprietà.</span><span class="sxs-lookup"><span data-stu-id="ace4e-124">Add at least one blank line between method and property definitions.</span></span>  
  
## <a name="commenting-conventions"></a><span data-ttu-id="ace4e-125">Convenzioni relative ai commenti</span><span class="sxs-lookup"><span data-stu-id="ace4e-125">Commenting Conventions</span></span>  
  
- <span data-ttu-id="ace4e-126">Inserire i commenti su una riga separata anziché alla fine di una riga di codice.</span><span class="sxs-lookup"><span data-stu-id="ace4e-126">Put comments on a separate line instead of at the end of a line of code.</span></span>  
  
- <span data-ttu-id="ace4e-127">Inizia il testo del commento con una lettera maiuscola e termina il testo del commento con un punto.</span><span class="sxs-lookup"><span data-stu-id="ace4e-127">Start comment text with an uppercase letter, and end comment text with a period.</span></span>  
  
- <span data-ttu-id="ace4e-128">Inserire uno spazio tra il delimitatore di commento (') e il testo del commento.</span><span class="sxs-lookup"><span data-stu-id="ace4e-128">Insert one space between the comment delimiter (') and the comment text.</span></span>  
  
     [!code-vb[VbVbalrGuidelines#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#2)]  
  
- <span data-ttu-id="ace4e-129">Non racchiudere i commenti con blocchi formattati di asterischi.</span><span class="sxs-lookup"><span data-stu-id="ace4e-129">Do not surround comments with formatted blocks of asterisks.</span></span>  
  
## <a name="program-structure"></a><span data-ttu-id="ace4e-130">Struttura del programma</span><span class="sxs-lookup"><span data-stu-id="ace4e-130">Program Structure</span></span>  
  
- <span data-ttu-id="ace4e-131">Quando si utilizza il metodo `Main`, utilizzare il costrutto predefinito per le nuove applicazioni console e utilizzare `My` per gli argomenti della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="ace4e-131">When you use the `Main` method, use the default construct for new console applications, and use `My` for command-line arguments.</span></span>  
  
     [!code-vb[VbVbalrGuidelines#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#3)]  
  
## <a name="language-guidelines"></a><span data-ttu-id="ace4e-132">Linee guida della lingua</span><span class="sxs-lookup"><span data-stu-id="ace4e-132">Language Guidelines</span></span>  
  
### <a name="string-data-type"></a><span data-ttu-id="ace4e-133">Tipo di dati String</span><span class="sxs-lookup"><span data-stu-id="ace4e-133">String Data Type</span></span>  
  
- <span data-ttu-id="ace4e-134">Usare l'[interpolazione di stringhe](https://docs.microsoft.com/dotnet/visual-basic/programming-guide/language-features/strings/interpolated-strings) per concatenare stringhe brevi, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="ace4e-134">Use [string interpolation](https://docs.microsoft.com/dotnet/visual-basic/programming-guide/language-features/strings/interpolated-strings) to concatenate short strings, as shown in the following code.</span></span>
  
     ```vb
     MsgBox($"hello{vbCrLf}goodbye")
     ```
  
- <span data-ttu-id="ace4e-135">Per accodare stringhe nei cicli, utilizzare l'oggetto <xref:System.Text.StringBuilder>.</span><span class="sxs-lookup"><span data-stu-id="ace4e-135">To append strings in loops, use the <xref:System.Text.StringBuilder> object.</span></span>  
  
     [!code-vb[VbVbalrGuidelines#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#5)]  
  
### <a name="relaxed-delegates-in-event-handlers"></a><span data-ttu-id="ace4e-136">Delegati rilassati nei gestori eventi</span><span class="sxs-lookup"><span data-stu-id="ace4e-136">Relaxed Delegates in Event Handlers</span></span>  
 <span data-ttu-id="ace4e-137">Non qualificare in modo esplicito gli argomenti (oggetto e EventArgs) per i gestori eventi.</span><span class="sxs-lookup"><span data-stu-id="ace4e-137">Do not explicitly qualify the arguments (Object and EventArgs) to event handlers.</span></span> <span data-ttu-id="ace4e-138">Se non si utilizzano gli argomenti dell'evento passati a un evento, ad esempio Sender come oggetto, e come EventArgs, utilizzare delegati rilassati e lasciare gli argomenti dell'evento nel codice:</span><span class="sxs-lookup"><span data-stu-id="ace4e-138">If you are not using the event arguments that are passed to an event (for example, sender as Object, e as EventArgs), use relaxed delegates, and leave out the event arguments in your code:</span></span>  
  
 [!code-vb[VbVbalrGuidelines#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#7)]  
  
### <a name="unsigned-data-type"></a><span data-ttu-id="ace4e-139">Tipi di dati non firmati</span><span class="sxs-lookup"><span data-stu-id="ace4e-139">Unsigned Data Type</span></span>  
  
- <span data-ttu-id="ace4e-140">Utilizzare `Integer` anziché tipi non firmati, tranne nei casi in cui sono necessari.</span><span class="sxs-lookup"><span data-stu-id="ace4e-140">Use `Integer` rather than unsigned types, except where they are necessary.</span></span>  
  
### <a name="arrays"></a><span data-ttu-id="ace4e-141">Matrici</span><span class="sxs-lookup"><span data-stu-id="ace4e-141">Arrays</span></span>  
  
- <span data-ttu-id="ace4e-142">Utilizzare la sintassi breve quando si inizializzano le matrici nella riga della dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="ace4e-142">Use the short syntax when you initialize arrays on the declaration line.</span></span> <span data-ttu-id="ace4e-143">Ad esempio, usare la sintassi seguente.</span><span class="sxs-lookup"><span data-stu-id="ace4e-143">For example, use the following syntax.</span></span>  
  
     [!code-vb[VbVbalrGuidelines#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#8)]  
  
     <span data-ttu-id="ace4e-144">Non utilizzare la sintassi seguente.</span><span class="sxs-lookup"><span data-stu-id="ace4e-144">Do not use the following syntax.</span></span>  
  
     [!code-vb[VbVbalrGuidelines#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#9)]  
  
- <span data-ttu-id="ace4e-145">Inserire l'indicatore di matrice sul tipo, non sulla variabile.</span><span class="sxs-lookup"><span data-stu-id="ace4e-145">Put the array designator on the type, not on the variable.</span></span> <span data-ttu-id="ace4e-146">Usare, ad esempio, la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="ace4e-146">For example, use the following syntax:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#11)]  
  
     <span data-ttu-id="ace4e-147">Non usare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="ace4e-147">Do not use the following syntax:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#10)]  
  
- <span data-ttu-id="ace4e-148">Utilizzare la sintassi {} quando si dichiarano e inizializzano matrici di tipi di dati di base.</span><span class="sxs-lookup"><span data-stu-id="ace4e-148">Use the { } syntax when you declare and initialize arrays of basic data types.</span></span> <span data-ttu-id="ace4e-149">Usare, ad esempio, la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="ace4e-149">For example, use the following syntax:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#12)]  
  
     <span data-ttu-id="ace4e-150">Non usare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="ace4e-150">Do not use the following syntax:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#13)]  
  
### <a name="use-the-with-keyword"></a><span data-ttu-id="ace4e-151">Usare la parola chiave with</span><span class="sxs-lookup"><span data-stu-id="ace4e-151">Use the With Keyword</span></span>  
 <span data-ttu-id="ace4e-152">Quando si esegue una serie di chiamate a un oggetto, provare a usare la parola chiave `With`:</span><span class="sxs-lookup"><span data-stu-id="ace4e-152">When you make a series of calls to one object, consider using the `With` keyword:</span></span>  
  
 [!code-vb[VbVbalrGuidelines#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#15)]  
  
### <a name="use-the-trycatch-and-using-statements-when-you-use-exception-handling"></a><span data-ttu-id="ace4e-153">Usa il try... Intercettare e utilizzare le istruzioni quando si utilizza la gestione delle eccezioni</span><span class="sxs-lookup"><span data-stu-id="ace4e-153">Use the Try...Catch and Using Statements when you use Exception Handling</span></span>  
 <span data-ttu-id="ace4e-154">Non usare la proprietà `On Error Goto`.</span><span class="sxs-lookup"><span data-stu-id="ace4e-154">Do not use `On Error Goto`.</span></span>  
  
### <a name="use-the-isnot-keyword"></a><span data-ttu-id="ace4e-155">Usare la parola chiave non</span><span class="sxs-lookup"><span data-stu-id="ace4e-155">Use the IsNot Keyword</span></span>  
 <span data-ttu-id="ace4e-156">Usare la parola chiave `IsNot` anziché `Not...Is Nothing`.</span><span class="sxs-lookup"><span data-stu-id="ace4e-156">Use the `IsNot` keyword instead of `Not...Is Nothing`.</span></span>  
  
### <a name="new-keyword"></a><span data-ttu-id="ace4e-157">Nuova parola chiave</span><span class="sxs-lookup"><span data-stu-id="ace4e-157">New Keyword</span></span>  
  
- <span data-ttu-id="ace4e-158">Usare la creazione di un'istanza breve.</span><span class="sxs-lookup"><span data-stu-id="ace4e-158">Use short instantiation.</span></span> <span data-ttu-id="ace4e-159">Usare, ad esempio, la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="ace4e-159">For example, use the following syntax:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#21)]  
  
     <span data-ttu-id="ace4e-160">La riga precedente è equivalente alla seguente:</span><span class="sxs-lookup"><span data-stu-id="ace4e-160">The preceding line is equivalent to this:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#22)]  
  
- <span data-ttu-id="ace4e-161">Usare gli inizializzatori di oggetto per i nuovi oggetti anziché il costruttore senza parametri:</span><span class="sxs-lookup"><span data-stu-id="ace4e-161">Use object initializers for new objects instead of the parameterless constructor:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#23)]  
  
### <a name="event-handling"></a><span data-ttu-id="ace4e-162">Gestione di eventi</span><span class="sxs-lookup"><span data-stu-id="ace4e-162">Event Handling</span></span>  
  
- <span data-ttu-id="ace4e-163">Usare `Handles` anziché `AddHandler`:</span><span class="sxs-lookup"><span data-stu-id="ace4e-163">Use `Handles` rather than `AddHandler`:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#24)]  
  
- <span data-ttu-id="ace4e-164">Usare `AddressOf`e non creare un'istanza del delegato in modo esplicito:</span><span class="sxs-lookup"><span data-stu-id="ace4e-164">Use `AddressOf`, and do not instantiate the delegate explicitly:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#25)]  
  
- <span data-ttu-id="ace4e-165">Quando si definisce un evento, usare la sintassi abbreviata e consentire al compilatore di definire il delegato:</span><span class="sxs-lookup"><span data-stu-id="ace4e-165">When you define an event, use the short syntax, and let the compiler define the delegate:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#26)]  
  
- <span data-ttu-id="ace4e-166">Non verificare se un evento è `Nothing` (null) prima di chiamare il metodo `RaiseEvent`.</span><span class="sxs-lookup"><span data-stu-id="ace4e-166">Do not verify whether an event is `Nothing` (null) before you call the `RaiseEvent` method.</span></span> <span data-ttu-id="ace4e-167">`RaiseEvent` controlla la presenza di `Nothing` prima che venga generato l'evento.</span><span class="sxs-lookup"><span data-stu-id="ace4e-167">`RaiseEvent` checks for `Nothing` before it raises the event.</span></span>  
  
### <a name="using-shared-members"></a><span data-ttu-id="ace4e-168">Uso di membri condivisi</span><span class="sxs-lookup"><span data-stu-id="ace4e-168">Using Shared Members</span></span>  
 <span data-ttu-id="ace4e-169">Chiamare `Shared` membri utilizzando il nome della classe, non da una variabile di istanza.</span><span class="sxs-lookup"><span data-stu-id="ace4e-169">Call `Shared` members by using the class name, not from an instance variable.</span></span>  
  
### <a name="use-xml-literals"></a><span data-ttu-id="ace4e-170">Usare valori letterali XML</span><span class="sxs-lookup"><span data-stu-id="ace4e-170">Use XML Literals</span></span>  
 <span data-ttu-id="ace4e-171">I valori letterali XML semplificano le attività più comuni che si verificano quando si lavora con XML (ad esempio, caricamento, query e trasformazione).</span><span class="sxs-lookup"><span data-stu-id="ace4e-171">XML literals simplify the most common tasks that you encounter when you work with XML (for example, load, query, and transform).</span></span> <span data-ttu-id="ace4e-172">Quando si sviluppa con XML, attenersi alle seguenti linee guida:</span><span class="sxs-lookup"><span data-stu-id="ace4e-172">When you develop with XML, follow these guidelines:</span></span>  
  
- <span data-ttu-id="ace4e-173">Usare valori letterali XML per creare documenti e frammenti XML anziché chiamare direttamente le API XML.</span><span class="sxs-lookup"><span data-stu-id="ace4e-173">Use XML literals to create XML documents and fragments instead of calling XML APIs directly.</span></span>  
  
- <span data-ttu-id="ace4e-174">Importare gli spazi dei nomi XML a livello di file o di progetto per sfruttare le ottimizzazioni delle prestazioni per i valori letterali XML.</span><span class="sxs-lookup"><span data-stu-id="ace4e-174">Import XML namespaces at the file or project level to take advantage of the performance optimizations for XML literals.</span></span>  
  
- <span data-ttu-id="ace4e-175">Utilizzare le proprietà dell'asse XML per accedere a elementi e attributi in un documento XML.</span><span class="sxs-lookup"><span data-stu-id="ace4e-175">Use the XML axis properties to access elements and attributes in an XML document.</span></span>  
  
- <span data-ttu-id="ace4e-176">Usare espressioni incorporate per includere valori e per creare codice XML da valori esistenti anziché usare chiamate API, ad esempio il metodo `Add`:</span><span class="sxs-lookup"><span data-stu-id="ace4e-176">Use embedded expressions to include values and to create XML from existing values instead of using API calls such as the `Add` method:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#27)]  
  
### <a name="linq-queries"></a><span data-ttu-id="ace4e-177">Query LINQ</span><span class="sxs-lookup"><span data-stu-id="ace4e-177">LINQ Queries</span></span>  
  
- <span data-ttu-id="ace4e-178">Usare nomi significativi per le variabili di query:</span><span class="sxs-lookup"><span data-stu-id="ace4e-178">Use meaningful names for query variables:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#28)]  
  
- <span data-ttu-id="ace4e-179">Fornire nomi per gli elementi in una query per assicurarsi che i nomi delle proprietà dei tipi anonimi siano correttamente in maiuscolo con la combinazione di maiuscole e minuscole Pascal:</span><span class="sxs-lookup"><span data-stu-id="ace4e-179">Provide names for elements in a query to make sure that property names of anonymous types are correctly capitalized using Pascal casing:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#29)]  
  
- <span data-ttu-id="ace4e-180">Rinominare le proprietà quando i nomi delle proprietà nel risultato potrebbero risultare ambigui.</span><span class="sxs-lookup"><span data-stu-id="ace4e-180">Rename properties when the property names in the result would be ambiguous.</span></span> <span data-ttu-id="ace4e-181">Se, ad esempio, la query restituisce un nome cliente e un ID ordine, rinominarli anziché lasciarli come `Name` e `ID` nel risultato:</span><span class="sxs-lookup"><span data-stu-id="ace4e-181">For example, if your query returns a customer name and an order ID, rename them instead of leaving them as `Name` and `ID` in the result:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#30)]  
  
- <span data-ttu-id="ace4e-182">Usare l'inferenza del tipo nella dichiarazione di variabili di query e variabili di intervallo:</span><span class="sxs-lookup"><span data-stu-id="ace4e-182">Use type inference in the declaration of query variables and range variables:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#31)]  
  
- <span data-ttu-id="ace4e-183">Allineare le clausole di query sotto l'istruzione `From`:</span><span class="sxs-lookup"><span data-stu-id="ace4e-183">Align query clauses under the `From` statement:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#32)]  
  
- <span data-ttu-id="ace4e-184">Usare le clausole `Where` prima di altre clausole di query in modo che le clausole di query successive funzionino sul set di dati filtrato:</span><span class="sxs-lookup"><span data-stu-id="ace4e-184">Use `Where` clauses before other query clauses so that later query clauses operate on the filtered set of data:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#33)]  
  
- <span data-ttu-id="ace4e-185">Utilizzare la clausola `Join` per definire in modo esplicito un'operazione di join anziché utilizzare la clausola `Where` per definire in modo implicito un'operazione di join:</span><span class="sxs-lookup"><span data-stu-id="ace4e-185">Use the `Join` clause to explicitly define a join operation instead of using the `Where` clause to implicitly define a join operation:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#34)]  
  
## <a name="see-also"></a><span data-ttu-id="ace4e-186">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ace4e-186">See also</span></span>

- [<span data-ttu-id="ace4e-187">Linee guida per la generazione di codice sicuro</span><span class="sxs-lookup"><span data-stu-id="ace4e-187">Secure Coding Guidelines</span></span>](../../../standard/security/secure-coding-guidelines.md)
