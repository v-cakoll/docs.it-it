---
title: Documentazione del codice con i commenti XML
description: Informazioni su come documentare il codice con commenti della documentazione XML e generare un file di documentazione XML in fase di compilazione.
ms.date: 01/21/2020
ms.technology: csharp-fundamentals
ms.assetid: 8e75e317-4a55-45f2-a866-e76124171838
ms.openlocfilehash: 1ed39c4733c36b3932fcb85bf50d4f4c0e53aa6f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79146317"
---
# <a name="document-your-code-with-xml-comments"></a><span data-ttu-id="e4696-103">Documentare il codice con commenti XMLDocument your code with XML comments</span><span class="sxs-lookup"><span data-stu-id="e4696-103">Document your code with XML comments</span></span>

<span data-ttu-id="e4696-104">I commenti in formato documentazione XML sono commenti speciali, aggiunti alla definizione di ogni tipo o membro definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="e4696-104">XML documentation comments are a special kind of comment, added above the definition of any user-defined type or member.</span></span>
<span data-ttu-id="e4696-105">Sono speciali perché possono essere elaborati dal compilatore per generare un file di documentazione XML in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="e4696-105">They are special because they can be processed by the compiler to generate an XML documentation file at compile time.</span></span>
<span data-ttu-id="e4696-106">Il file XML generato dal compilatore può essere distribuito insieme all'assembly .NET in modo che Visual Studio e altri IDE possano usare IntelliSense per visualizzare informazioni rapide su tipi o membri.</span><span class="sxs-lookup"><span data-stu-id="e4696-106">The compiler-generated XML file can be distributed alongside your .NET assembly so that Visual Studio and other IDEs can use IntelliSense to show quick information about types or members.</span></span> <span data-ttu-id="e4696-107">È anche possibile eseguire il file XML tramite strumenti, ad esempio [DocFX](https://dotnet.github.io/docfx/) e [Sandcastle](https://github.com/EWSoftware/SHFB) per generare i siti Web di riferimento all'API.</span><span class="sxs-lookup"><span data-stu-id="e4696-107">Additionally, the XML file can be run through tools like [DocFX](https://dotnet.github.io/docfx/) and [Sandcastle](https://github.com/EWSoftware/SHFB) to generate API reference websites.</span></span>

<span data-ttu-id="e4696-108">I commenti in formato documentazione XML, come tutti gli altri commenti, vengono ignorati dal compilatore.</span><span class="sxs-lookup"><span data-stu-id="e4696-108">XML documentation comments, like all other comments, are ignored by the compiler.</span></span>

<span data-ttu-id="e4696-109">È possibile generare il file XML in fase di compilazione eseguendo una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e4696-109">You can generate the XML file at compile time by doing one of the following:</span></span>

- <span data-ttu-id="e4696-110">Se si sviluppa un'applicazione con .NET Core dalla `GenerateDocumentationFile` riga di `<PropertyGroup>` comando, è possibile aggiungere un elemento alla sezione del file di progetto con estensione csproj.</span><span class="sxs-lookup"><span data-stu-id="e4696-110">If you are developing an application with .NET Core from the command line, you can add a `GenerateDocumentationFile` element to the `<PropertyGroup>` section of your .csproj project file.</span></span> <span data-ttu-id="e4696-111">È inoltre possibile specificare direttamente il percorso del file di documentazione [ `DocumentationFile` utilizzando](/visualstudio/msbuild/common-msbuild-project-properties)element .</span><span class="sxs-lookup"><span data-stu-id="e4696-111">You can also specify the path to the documentation file directly using [`DocumentationFile` element](/visualstudio/msbuild/common-msbuild-project-properties).</span></span> <span data-ttu-id="e4696-112">L'esempio seguente genera un file XML nella directory del progetto con lo stesso nome file radice dell'assembly:</span><span class="sxs-lookup"><span data-stu-id="e4696-112">The following example generates an XML file in the project directory with the same root filename as the assembly:</span></span>

   ```xml
   <GenerateDocumentationFile>true</GenerateDocumentationFile>
   ```

   <span data-ttu-id="e4696-113">L'espressione equivale alla seguente:</span><span class="sxs-lookup"><span data-stu-id="e4696-113">This is equivalent to the following:</span></span>

   ```xml
   <DocumentationFile>bin\$(Configuration)\$(TargetFramework)\$(AssemblyName).xml</DocumentationFile>
   ```

- <span data-ttu-id="e4696-114">Se si sviluppa un'applicazione tramite Visual Studio, fare clic con il pulsante destro del mouse sul progetto e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="e4696-114">If you are developing an application using Visual Studio, right-click on the project and select **Properties**.</span></span> <span data-ttu-id="e4696-115">Nella finestra di dialogo Proprietà selezionare la scheda **Genera** e controllare **File di documentazione XML**.</span><span class="sxs-lookup"><span data-stu-id="e4696-115">In the properties dialog, select the **Build** tab, and check **XML documentation file**.</span></span> <span data-ttu-id="e4696-116">È anche possibile modificare il percorso in cui il compilatore scrive il file.</span><span class="sxs-lookup"><span data-stu-id="e4696-116">You can also change the location to which the compiler writes the file.</span></span>

- <span data-ttu-id="e4696-117">Se si compila un'applicazione .NET Framework dalla riga di comando, aggiungere [l'opzione del compilatore -doc](language-reference/compiler-options/doc-compiler-option.md) durante la compilazione.</span><span class="sxs-lookup"><span data-stu-id="e4696-117">If you are compiling a .NET Framework application from the command line, add the [-doc compiler option](language-reference/compiler-options/doc-compiler-option.md) when compiling.</span></span>  

<span data-ttu-id="e4696-118">I commenti in formato documentazione XML usano tre barre (`///`) e un corpo di commento in formato XML.</span><span class="sxs-lookup"><span data-stu-id="e4696-118">XML documentation comments use triple forward slashes (`///`) and an XML formatted comment body.</span></span> <span data-ttu-id="e4696-119">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="e4696-119">For example:</span></span>

[!code-csharp[XML Documentation Comment](../../samples/snippets/csharp/concepts/codedoc/xml-comment.cs)]

## <a name="walkthrough"></a><span data-ttu-id="e4696-120">Procedura dettagliata</span><span class="sxs-lookup"><span data-stu-id="e4696-120">Walkthrough</span></span>

<span data-ttu-id="e4696-121">Esaminiamo la documentazione di una libreria matematica molto semplice per semplificare la comprensione/contributo dei nuovi sviluppatori e l'utilizzo da parte degli sviluppatori di terze parti.</span><span class="sxs-lookup"><span data-stu-id="e4696-121">Let's walk through documenting a very basic math library to make it easy for new developers to understand/contribute and for third-party developers to use.</span></span>

<span data-ttu-id="e4696-122">Questo è il codice per la semplice libreria matematica:</span><span class="sxs-lookup"><span data-stu-id="e4696-122">Here's code for the simple math library:</span></span>

[!code-csharp[Sample Library](../../samples/snippets/csharp/concepts/codedoc/sample-library.cs)]

<span data-ttu-id="e4696-123">La libreria di esempio supporta`add`quattro `subtract` `multiply`operazioni `divide`aritmetiche `int` `double` principali ( , , , e ) e i tipi di dati .</span><span class="sxs-lookup"><span data-stu-id="e4696-123">The sample library supports four major arithmetic operations (`add`, `subtract`, `multiply`, and `divide`) on `int` and `double` data types.</span></span>

<span data-ttu-id="e4696-124">Ora vuoi essere in grado di creare un documento di riferimento API dal tuo codice per gli sviluppatori di terze parti che usano la tua libreria ma non hanno accesso al codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="e4696-124">Now you want to be able to create an API reference document from your code for third-party developers who use your library but don't have access to the source code.</span></span>
<span data-ttu-id="e4696-125">Come accennato in precedenza, è possibile usare tag della documentazione XML a questo scopo.</span><span class="sxs-lookup"><span data-stu-id="e4696-125">As mentioned earlier XML documentation tags can be used to achieve this.</span></span> <span data-ttu-id="e4696-126">Verranno ora presentati i tag XML standard supportati dal compilatore C#.</span><span class="sxs-lookup"><span data-stu-id="e4696-126">You will now be introduced to the standard XML tags the C# compiler supports.</span></span>

## <a name="summary"></a><span data-ttu-id="e4696-127">\<summary></span><span class="sxs-lookup"><span data-stu-id="e4696-127">\<summary></span></span>

<span data-ttu-id="e4696-128">Il tag `<summary>` aggiunge brevi informazioni su un tipo o membro.</span><span class="sxs-lookup"><span data-stu-id="e4696-128">The `<summary>` tag adds brief information about a type or member.</span></span>
<span data-ttu-id="e4696-129">Ne viene illustrato l'uso aggiungendolo alla definizione di classe `Math` e al primo metodo `Add`.</span><span class="sxs-lookup"><span data-stu-id="e4696-129">I'll demonstrate its use by adding it to the `Math` class definition and the first `Add` method.</span></span> <span data-ttu-id="e4696-130">È possibile applicarlo al resto del codice.</span><span class="sxs-lookup"><span data-stu-id="e4696-130">Feel free to apply it to the rest of your code.</span></span>

[!code-csharp[Summary Tag](~/samples/snippets/csharp/concepts/codedoc/summary-tag.cs)]

<span data-ttu-id="e4696-131">Il `<summary>` tag è importante e si consiglia di includerlo perché il relativo contenuto è l'origine primaria di informazioni sul tipo o sul membro in IntelliSense o in un documento di riferimento API.</span><span class="sxs-lookup"><span data-stu-id="e4696-131">The `<summary>` tag is important, and we recommend that you include it because its content is the primary source of type or member information in IntelliSense or an API reference document.</span></span>

## <a name="remarks"></a><span data-ttu-id="e4696-132">\<remarks></span><span class="sxs-lookup"><span data-stu-id="e4696-132">\<remarks></span></span>

<span data-ttu-id="e4696-133">Il tag `<remarks>` integra le informazioni sui tipi o membri definiti dal tag `<summary>`.</span><span class="sxs-lookup"><span data-stu-id="e4696-133">The `<remarks>` tag supplements the information about types or members that the `<summary>` tag provides.</span></span> <span data-ttu-id="e4696-134">In questo esempio, sarà sufficiente aggiungerlo alla classe.</span><span class="sxs-lookup"><span data-stu-id="e4696-134">In this example, you'll just add it to the class.</span></span>

[!code-csharp[Remarks Tag](~/samples/snippets/csharp/concepts/codedoc/remarks-tag.cs)]

## <a name="returns"></a><span data-ttu-id="e4696-135">\<returns></span><span class="sxs-lookup"><span data-stu-id="e4696-135">\<returns></span></span>

<span data-ttu-id="e4696-136">Il tag `<returns>` descrive il valore restituito di una dichiarazione di metodo.</span><span class="sxs-lookup"><span data-stu-id="e4696-136">The `<returns>` tag describes the return value of a method declaration.</span></span>
<span data-ttu-id="e4696-137">Come in precedenza, nell'esempio seguente viene illustrato il tag `<returns>` nel primo metodo `Add`.</span><span class="sxs-lookup"><span data-stu-id="e4696-137">As before, the following example illustrates the `<returns>` tag on the first `Add` method.</span></span> <span data-ttu-id="e4696-138">È possibile eseguire questa operazione su altri metodi.</span><span class="sxs-lookup"><span data-stu-id="e4696-138">You can do the same on other methods.</span></span>

[!code-csharp[Returns Tag](~/samples/snippets/csharp/concepts/codedoc/returns-tag.cs)]

## <a name="value"></a><span data-ttu-id="e4696-139">\<valore></span><span class="sxs-lookup"><span data-stu-id="e4696-139">\<value></span></span>

<span data-ttu-id="e4696-140">Il tag `<value>` è simile al tag `<returns>`, ad eccezione del fatto che viene usato per le proprietà.</span><span class="sxs-lookup"><span data-stu-id="e4696-140">The `<value>` tag is similar to the `<returns>` tag, except that you use it for properties.</span></span>
<span data-ttu-id="e4696-141">Se la libreria `Math` avesse una proprietà statica denominata `PI`, questo tag dovrebbe essere usato nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="e4696-141">Assuming your `Math` library had a static property called `PI`, here's how you'd use this tag:</span></span>

[!code-csharp[Value Tag](~/samples/snippets/csharp/concepts/codedoc/value-tag.cs)]

## <a name="example"></a><span data-ttu-id="e4696-142">\<example></span><span class="sxs-lookup"><span data-stu-id="e4696-142">\<example></span></span>

<span data-ttu-id="e4696-143">Si usa il tag `<example>` per includere un esempio nella documentazione XML.</span><span class="sxs-lookup"><span data-stu-id="e4696-143">You use the `<example>` tag to include an example in your XML documentation.</span></span>
<span data-ttu-id="e4696-144">Ciò comporta l'uso del tag `<code>` del figlio.</span><span class="sxs-lookup"><span data-stu-id="e4696-144">This involves using the child `<code>` tag.</span></span>

[!code-csharp[Example Tag](~/samples/snippets/csharp/concepts/codedoc/example-tag.cs)]

<span data-ttu-id="e4696-145">Il tag `code` mantiene le interruzioni di riga e il rientro per esempi più lunghi.</span><span class="sxs-lookup"><span data-stu-id="e4696-145">The `code` tag preserves line breaks and indentation for longer examples.</span></span>

## <a name="para"></a><span data-ttu-id="e4696-146">\<para></span><span class="sxs-lookup"><span data-stu-id="e4696-146">\<para></span></span>

<span data-ttu-id="e4696-147">Si usa il tag `<para>` per formattare il contenuto all'interno del tag padre.</span><span class="sxs-lookup"><span data-stu-id="e4696-147">You use the `<para>` tag to format the content within its parent tag.</span></span> <span data-ttu-id="e4696-148">`<para>` viene in genere usato all'interno di un tag, ad esempio `<remarks>` o `<returns>`, per dividere il testo in paragrafi.</span><span class="sxs-lookup"><span data-stu-id="e4696-148">`<para>` is usually used inside a tag, such as `<remarks>` or `<returns>`, to divide text into paragraphs.</span></span>
<span data-ttu-id="e4696-149">È possibile formattare il contenuto del tag `<remarks>` per la definizione delle classi.</span><span class="sxs-lookup"><span data-stu-id="e4696-149">You can format the contents of the `<remarks>` tag for your class definition.</span></span>

[!code-csharp[Para Tag](~/samples/snippets/csharp/concepts/codedoc/para-tag.cs)]

## <a name="c"></a><span data-ttu-id="e4696-150">\<c></span><span class="sxs-lookup"><span data-stu-id="e4696-150">\<c></span></span>

<span data-ttu-id="e4696-151">Nella formattazione si usa il tag `<c>` per contrassegnare parte del testo come codice.</span><span class="sxs-lookup"><span data-stu-id="e4696-151">Still on the topic of formatting, you use the `<c>` tag for marking part of text as code.</span></span>
<span data-ttu-id="e4696-152">È simile al tag `<code>`, ma è inline.</span><span class="sxs-lookup"><span data-stu-id="e4696-152">It's like the `<code>` tag but inline.</span></span> <span data-ttu-id="e4696-153">È utile quando si vuole visualizzare un esempio breve di codice come parte del contenuto del tag.</span><span class="sxs-lookup"><span data-stu-id="e4696-153">It's useful when you want to show a quick code example as part of a tag's content.</span></span>
<span data-ttu-id="e4696-154">Ora viene aggiornata la documentazione per la classe `Math`.</span><span class="sxs-lookup"><span data-stu-id="e4696-154">Let's update the documentation for the `Math` class.</span></span>

[!code-csharp[C Tag](~/samples/snippets/csharp/concepts/codedoc/c-tag.cs)]

## <a name="exception"></a><span data-ttu-id="e4696-155">\<exception></span><span class="sxs-lookup"><span data-stu-id="e4696-155">\<exception></span></span>

<span data-ttu-id="e4696-156">Tramite il tag `<exception>` è possibile comunicare agli sviluppatori che un metodo può generare eccezioni specifiche.</span><span class="sxs-lookup"><span data-stu-id="e4696-156">By using the `<exception>` tag, you let your developers know that a method can throw specific exceptions.</span></span>
<span data-ttu-id="e4696-157">Esaminando la libreria `Math`, è possibile vedere che entrambi i metodi `Add` generano un'eccezione se viene soddisfatta una determinata condizione.</span><span class="sxs-lookup"><span data-stu-id="e4696-157">Looking at your `Math` library, you can see that both `Add` methods throw an exception if a certain condition is met.</span></span> <span data-ttu-id="e4696-158">Nonostante non sia così ovvio, anche il metodo `Divide` integer genera eccezioni se il parametro `b` è uguale a zero.</span><span class="sxs-lookup"><span data-stu-id="e4696-158">Not so obvious, though, is that integer `Divide` method throws as well if the `b` parameter is zero.</span></span> <span data-ttu-id="e4696-159">Aggiungere ora la documentazione sull'eccezione a questo metodo.</span><span class="sxs-lookup"><span data-stu-id="e4696-159">Now add exception documentation to this method.</span></span>

[!code-csharp[Exception Tag](~/samples/snippets/csharp/concepts/codedoc/exception-tag.cs)]

<span data-ttu-id="e4696-160">L'attributo `cref` rappresenta un riferimento ad un'eccezione disponibile dall'ambiente di compilazione corrente.</span><span class="sxs-lookup"><span data-stu-id="e4696-160">The `cref` attribute represents a reference to an exception that is available from the current compilation environment.</span></span>
<span data-ttu-id="e4696-161">Ciò può essere qualsiasi tipo definito nel progetto o in un assembly di riferimento.</span><span class="sxs-lookup"><span data-stu-id="e4696-161">This can be any type defined in the project or a referenced assembly.</span></span> <span data-ttu-id="e4696-162">Il compilatore genererà un avviso se il relativo valore non può essere risolto.</span><span class="sxs-lookup"><span data-stu-id="e4696-162">The compiler will issue a warning if its value cannot be resolved.</span></span>

## <a name="see"></a><span data-ttu-id="e4696-163">\<see></span><span class="sxs-lookup"><span data-stu-id="e4696-163">\<see></span></span>

<span data-ttu-id="e4696-164">Il tag `<see>` consente di creare un collegamento selezionabile per una pagina di documentazione per un altro elemento di codice.</span><span class="sxs-lookup"><span data-stu-id="e4696-164">The `<see>` tag lets you create a clickable link to a documentation page for another code element.</span></span> <span data-ttu-id="e4696-165">Nel prossimo esempio, verrà creato un collegamento selezionabile tra i due metodi `Add`.</span><span class="sxs-lookup"><span data-stu-id="e4696-165">In our next example, we'll create a clickable link between the two `Add` methods.</span></span>

[!code-csharp[See Tag](~/samples/snippets/csharp/concepts/codedoc/see-tag.cs)]

<span data-ttu-id="e4696-166">L'attributo `cref` è **obbligatorio** e rappresenta un riferimento a un tipo o al suo membro disponibile dall'ambiente di compilazione corrente.</span><span class="sxs-lookup"><span data-stu-id="e4696-166">The `cref` is a **required** attribute that represents a reference to a type or its member that is available from the current compilation environment.</span></span>
<span data-ttu-id="e4696-167">Ciò può essere qualsiasi tipo definito nel progetto o in un assembly di riferimento.</span><span class="sxs-lookup"><span data-stu-id="e4696-167">This can be any type defined in the project or a referenced assembly.</span></span>

## <a name="seealso"></a><span data-ttu-id="e4696-168">\<seealso></span><span class="sxs-lookup"><span data-stu-id="e4696-168">\<seealso></span></span>

<span data-ttu-id="e4696-169">Il tag `<seealso>` si usa allo stesso modo del tag `<see>`.</span><span class="sxs-lookup"><span data-stu-id="e4696-169">You use the `<seealso>` tag in the same way you do the `<see>` tag.</span></span> <span data-ttu-id="e4696-170">L'unica differenza è che il relativo contenuto viene in genere inserito in una sezione "Vedere anche".</span><span class="sxs-lookup"><span data-stu-id="e4696-170">The only difference is that its content is typically placed in a "See Also" section.</span></span> <span data-ttu-id="e4696-171">Di seguito si aggiungerà un tag `seealso` al metodo `Add` integer per fare riferimento ad altri metodi della classe che accettano parametri integer:</span><span class="sxs-lookup"><span data-stu-id="e4696-171">Here we'll add a `seealso` tag on the integer `Add` method to reference other methods in the class that accept integer parameters:</span></span>

[!code-csharp[Seealso Tag](~/samples/snippets/csharp/concepts/codedoc/seealso-tag.cs)]

<span data-ttu-id="e4696-172">L'attributo `cref` rappresenta un riferimento a un tipo o al suo membro disponibile dall'ambiente di compilazione corrente.</span><span class="sxs-lookup"><span data-stu-id="e4696-172">The `cref` attribute represents a reference to a type or its member that is available from the current compilation environment.</span></span>
<span data-ttu-id="e4696-173">Ciò può essere qualsiasi tipo definito nel progetto o in un assembly di riferimento.</span><span class="sxs-lookup"><span data-stu-id="e4696-173">This can be any type defined in the project or a referenced assembly.</span></span>

## <a name="param"></a><span data-ttu-id="e4696-174">\<param></span><span class="sxs-lookup"><span data-stu-id="e4696-174">\<param></span></span>

<span data-ttu-id="e4696-175">Il tag `<param>` viene usato per descrivere i parametri del metodo.</span><span class="sxs-lookup"><span data-stu-id="e4696-175">You use the `<param>` tag to describe a method's parameters.</span></span> <span data-ttu-id="e4696-176">Ecco un esempio sul `Add` metodo double: il parametro descritto dal tag è specificato nell'attributo **obbligatorio.** `name`</span><span class="sxs-lookup"><span data-stu-id="e4696-176">Here's an example on the double `Add` method: The parameter the tag describes is specified in the **required** `name` attribute.</span></span>

[!code-csharp[Param Tag](~/samples/snippets/csharp/concepts/codedoc/param-tag.cs)]

## <a name="typeparam"></a><span data-ttu-id="e4696-177">\<typeparam></span><span class="sxs-lookup"><span data-stu-id="e4696-177">\<typeparam></span></span>

<span data-ttu-id="e4696-178">Il tag `<typeparam>` viene usato allo stesso modo del tag `<param>`, ma in dichiarazioni di tipo o di metodo generico per descrivere un parametro generico.</span><span class="sxs-lookup"><span data-stu-id="e4696-178">You use `<typeparam>` tag just like the `<param>` tag but for generic type or method declarations to describe a generic parameter.</span></span>
<span data-ttu-id="e4696-179">Aggiungere un metodo generico semplice alla classe `Math` per verificare se una quantità è maggiore di un'altra.</span><span class="sxs-lookup"><span data-stu-id="e4696-179">Add a quick generic method to your `Math` class to check if one quantity is greater than another.</span></span>

[!code-csharp[Typeparam Tag](~/samples/snippets/csharp/concepts/codedoc/typeparam-tag.cs)]

## <a name="paramref"></a><span data-ttu-id="e4696-180">\<paramref></span><span class="sxs-lookup"><span data-stu-id="e4696-180">\<paramref></span></span>

<span data-ttu-id="e4696-181">A volte è possibile che durante la descrizione dell'operazione di un metodo in un tag `<summary>` si vuole fare un riferimento a un parametro.</span><span class="sxs-lookup"><span data-stu-id="e4696-181">Sometimes you might be in the middle of describing what a method does in what could be a `<summary>` tag, and you might want to make a reference to a parameter.</span></span> <span data-ttu-id="e4696-182">Il tag `<paramref>` è molto utile per questa operazione.</span><span class="sxs-lookup"><span data-stu-id="e4696-182">The `<paramref>` tag is great for just this.</span></span> <span data-ttu-id="e4696-183">Ora si aggiorna il riepilogo del metodo `Add` basato su double.</span><span class="sxs-lookup"><span data-stu-id="e4696-183">Let's update the summary of our double based `Add` method.</span></span> <span data-ttu-id="e4696-184">Come `<param>` il tag, il nome del parametro viene specificato nell'attributo **obbligatorio.** `name`</span><span class="sxs-lookup"><span data-stu-id="e4696-184">Like the `<param>` tag, the parameter name is specified in the **required** `name` attribute.</span></span>

[!code-csharp[Paramref Tag](~/samples/snippets/csharp/concepts/codedoc/paramref-tag.cs)]

## <a name="typeparamref"></a><span data-ttu-id="e4696-185">\<typeparamref></span><span class="sxs-lookup"><span data-stu-id="e4696-185">\<typeparamref></span></span>

<span data-ttu-id="e4696-186">Il tag `<typeparamref>` viene usato allo stesso modo del tag `<paramref>`, ma in dichiarazioni di tipo o di metodo generico per descrivere un parametro generico.</span><span class="sxs-lookup"><span data-stu-id="e4696-186">You use `<typeparamref>` tag just like the `<paramref>` tag but for generic type or method declarations to describe a generic parameter.</span></span>
<span data-ttu-id="e4696-187">È possibile usare lo stesso metodo generico creato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="e4696-187">You can use the same generic method you previously created.</span></span>

[!code-csharp[Typeparamref Tag](~/samples/snippets/csharp/concepts/codedoc/typeparamref-tag.cs)]

## <a name="list"></a><span data-ttu-id="e4696-188">\<list></span><span class="sxs-lookup"><span data-stu-id="e4696-188">\<list></span></span>

<span data-ttu-id="e4696-189">Utilizzare il `<list>` tag per formattare le informazioni sulla documentazione come elenco ordinato, elenco non ordinato o tabella.</span><span class="sxs-lookup"><span data-stu-id="e4696-189">You use the `<list>` tag to format documentation information as an ordered list, unordered list, or table.</span></span> <span data-ttu-id="e4696-190">Creare un elenco non ordinato di ogni operazione matematica supportata dalla libreria `Math`.</span><span class="sxs-lookup"><span data-stu-id="e4696-190">Make an unordered list of every math operation your `Math` library supports.</span></span>

[!code-csharp[List Tag](~/samples/snippets/csharp/concepts/codedoc/list-tag.cs)]

<span data-ttu-id="e4696-191">È possibile creare un elenco ordinato o una tabella sostituendo l'attributo `type` con `number` o `table` rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="e4696-191">You can make an ordered list or table by changing the `type` attribute to `number` or `table`, respectively.</span></span>

## <a name="inheritdoc"></a><span data-ttu-id="e4696-192">\<eredita></span><span class="sxs-lookup"><span data-stu-id="e4696-192">\<inheritdoc></span></span>

<span data-ttu-id="e4696-193">È possibile `<inheritdoc>` utilizzare il tag per ereditare i commenti XML dalle classi base, dalle interfacce e da metodi simili.</span><span class="sxs-lookup"><span data-stu-id="e4696-193">You can use the `<inheritdoc>` tag to inherit XML comments from base classes, interfaces, and similar methods.</span></span> <span data-ttu-id="e4696-194">In questo modo si eliminano le operazioni di copia e incolla indesiderate di commenti XML duplicati e mantiene automaticamente sincronizzati i commenti XML.</span><span class="sxs-lookup"><span data-stu-id="e4696-194">This eliminates unwanted copying and pasting of duplicate XML comments and automatically keeps XML comments synchronized.</span></span>

[!code-csharp-interactive[InheritDoc Tag](~/samples/snippets/csharp/concepts/codedoc/inheritdoc-tag.cs)]

### <a name="put-it-all-together"></a><span data-ttu-id="e4696-195">Combinare tutti gli elementi</span><span class="sxs-lookup"><span data-stu-id="e4696-195">Put it all together</span></span>

<span data-ttu-id="e4696-196">Dopo aver eseguito questa esercitazione e applicato i tag al codice, dove necessario, il codice dovrebbe ora essere simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="e4696-196">If you've followed this tutorial and applied the tags to your code where necessary, your code should now look similar to the following:</span></span>

[!code-csharp[Tagged Library](~/samples/snippets/csharp/concepts/codedoc/tagged-library.cs)]

<span data-ttu-id="e4696-197">Dal codice, è possibile generare un sito Web di documentazione dettagliata completa di riferimenti incrociati.</span><span class="sxs-lookup"><span data-stu-id="e4696-197">From your code, you can generate a detailed documentation website complete with clickable cross-references.</span></span> <span data-ttu-id="e4696-198">Ciò però potrebbe rendere il codice più difficile da leggere.</span><span class="sxs-lookup"><span data-stu-id="e4696-198">But you're faced with another problem: your code has become hard to read.</span></span>
<span data-ttu-id="e4696-199">In quanto la presenza di un numero elevato di informazioni costituisce un problema molto serio per gli sviluppatori che vogliono contribuire al codice.</span><span class="sxs-lookup"><span data-stu-id="e4696-199">There's so much information to sift through that this is going to be a nightmare for any developer who wants to contribute to this code.</span></span>
<span data-ttu-id="e4696-200">Fortunatamente c'è un tag XML che consente di affrontare questo problema:</span><span class="sxs-lookup"><span data-stu-id="e4696-200">Thankfully there's an XML tag that can help you deal with this:</span></span>

## <a name="include"></a><span data-ttu-id="e4696-201">\<include></span><span class="sxs-lookup"><span data-stu-id="e4696-201">\<include></span></span>

<span data-ttu-id="e4696-202">Il tag `<include>` consente di fare riferimento ai commenti in un file XML separato che descrivono i tipi e i membri nel codice sorgente anziché inserire commenti in formato documentazione direttamente nel file del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="e4696-202">The `<include>` tag lets you refer to comments in a separate XML file that describe the types and members in your source code, as opposed to placing documentation comments directly in your source code file.</span></span>

<span data-ttu-id="e4696-203">Ora si spostano tutti i tag XML in un file XML separato denominato `docs.xml`.</span><span class="sxs-lookup"><span data-stu-id="e4696-203">Now you're going to move all your XML tags into a separate XML file named `docs.xml`.</span></span> <span data-ttu-id="e4696-204">È possibile assegnare al file un nome qualsiasi.</span><span class="sxs-lookup"><span data-stu-id="e4696-204">Feel free to name the file whatever you want.</span></span>

[!code-xml[Sample XML](~/samples/snippets/csharp/concepts/codedoc/include.xml)]

<span data-ttu-id="e4696-205">Nel codice XML precedente, i commenti in formato documentazione di ogni membro vengono visualizzati direttamente all'interno di un tag denominato dopo le operazioni eseguite.</span><span class="sxs-lookup"><span data-stu-id="e4696-205">In the above XML, each member's documentation comments appear directly inside a tag named after what they do.</span></span> <span data-ttu-id="e4696-206">È possibile scegliere una strategia personalizzata.</span><span class="sxs-lookup"><span data-stu-id="e4696-206">You can choose your own strategy.</span></span>
<span data-ttu-id="e4696-207">Ora che i commenti XML si trovano in un file separato, di seguito viene illustrato come il codice può essere reso più leggibile usando il tag `<include>`:</span><span class="sxs-lookup"><span data-stu-id="e4696-207">Now that you have your XML comments in a separate file, let's see how your code can be made more readable by using the `<include>` tag:</span></span>

[!code-csharp[Include Tag](~/samples/snippets/csharp/concepts/codedoc/include-tag.cs)]

<span data-ttu-id="e4696-208">Infine si avrà un codice di nuovo leggibile e nessuna informazione sulla documentazione è andata persa.</span><span class="sxs-lookup"><span data-stu-id="e4696-208">And there you have it: our code is back to being readable, and no documentation information has been lost.</span></span>

<span data-ttu-id="e4696-209">L'attributo `file` rappresenta il nome del file XML che contiene la documentazione.</span><span class="sxs-lookup"><span data-stu-id="e4696-209">The `file` attribute represents the name of the XML file containing the documentation.</span></span>

<span data-ttu-id="e4696-210">L'attributo `path` rappresenta una query [XPath](../standard/data/xml/xpath-queries-and-namespaces.md) nel presente `tag name` del `file` specificato.</span><span class="sxs-lookup"><span data-stu-id="e4696-210">The `path` attribute represents an [XPath](../standard/data/xml/xpath-queries-and-namespaces.md) query to the `tag name` present in the specified `file`.</span></span>

<span data-ttu-id="e4696-211">L'attributo `name` rappresenta l'identificatore di nome nel tag che precede i commenti.</span><span class="sxs-lookup"><span data-stu-id="e4696-211">The `name` attribute represents the name specifier in the tag that precedes the comments.</span></span>

<span data-ttu-id="e4696-212">L'attributo `id` , che può `name`essere utilizzato al posto di , rappresenta l'ID per il tag che precede i commenti.</span><span class="sxs-lookup"><span data-stu-id="e4696-212">The `id` attribute, which can be used in place of `name`, represents the ID for the tag that precedes the comments.</span></span>

### <a name="user-defined-tags"></a><span data-ttu-id="e4696-213">Tag definiti dall'utente</span><span class="sxs-lookup"><span data-stu-id="e4696-213">User-defined tags</span></span>

<span data-ttu-id="e4696-214">Tutti i tag specificati in precedenza rappresentano i tag riconosciuti dal compilatore C#.</span><span class="sxs-lookup"><span data-stu-id="e4696-214">All the tags outlined above represent those that are recognized by the C# compiler.</span></span> <span data-ttu-id="e4696-215">Gli utenti comunque possono definire tag personalizzati.</span><span class="sxs-lookup"><span data-stu-id="e4696-215">However, a user is free to define their own tags.</span></span>
<span data-ttu-id="e4696-216">Strumenti come Sandcastle portano il [ \<](https://ewsoftware.github.io/XMLCommentsGuide/html/81bf7ad3-45dc-452f-90d5-87ce2494a182.htm) supporto per tag aggiuntivi come>di eventi e [ \<>, ](https://ewsoftware.github.io/XMLCommentsGuide/html/4302a60f-e4f4-4b8d-a451-5f453c4ebd46.htm)e supportano anche gli spazi dei nomi di [documentazione.](https://ewsoftware.github.io/XMLCommentsGuide/html/BD91FAD4-188D-4697-A654-7C07FD47EF31.htm)</span><span class="sxs-lookup"><span data-stu-id="e4696-216">Tools like Sandcastle bring support for extra tags like [\<event>](https://ewsoftware.github.io/XMLCommentsGuide/html/81bf7ad3-45dc-452f-90d5-87ce2494a182.htm) and [\<note>](https://ewsoftware.github.io/XMLCommentsGuide/html/4302a60f-e4f4-4b8d-a451-5f453c4ebd46.htm), and even support [documenting namespaces](https://ewsoftware.github.io/XMLCommentsGuide/html/BD91FAD4-188D-4697-A654-7C07FD47EF31.htm).</span></span>
<span data-ttu-id="e4696-217">Gli strumenti di creazione della documentazione interna o personalizzata possono anche essere usati con i tag standard e con più formati di output da HTML a PDF.</span><span class="sxs-lookup"><span data-stu-id="e4696-217">Custom or in-house documentation generation tools can also be used with the standard tags and multiple output formats from HTML to PDF can be supported.</span></span>

## <a name="recommendations"></a><span data-ttu-id="e4696-218">Consigli</span><span class="sxs-lookup"><span data-stu-id="e4696-218">Recommendations</span></span>

<span data-ttu-id="e4696-219">La documentazione del codice è consigliabile per vari motivi.</span><span class="sxs-lookup"><span data-stu-id="e4696-219">Documenting code is recommended for many reasons.</span></span> <span data-ttu-id="e4696-220">Di seguito vengono illustrate alcune procedure consigliate, scenari di uso generale e altre operazioni che è necessario conoscere quando si usano i tag in formato documentazione XML nel codice C#.</span><span class="sxs-lookup"><span data-stu-id="e4696-220">What follows are some best practices, general use case scenarios, and things that you should know when using XML documentation tags in your C# code.</span></span>

- <span data-ttu-id="e4696-221">Per mantenere una certa coerenza, tutti i tipi visibili pubblicamente e i loro membri devono essere documentati.</span><span class="sxs-lookup"><span data-stu-id="e4696-221">For the sake of consistency, all publicly visible types and their members should be documented.</span></span> <span data-ttu-id="e4696-222">Se necessario, è consigliabile eseguire un'operazione completa.</span><span class="sxs-lookup"><span data-stu-id="e4696-222">If you must do it, do it all.</span></span>
- <span data-ttu-id="e4696-223">I membri private possono anche essere documentati con commenti XML.</span><span class="sxs-lookup"><span data-stu-id="e4696-223">Private members can also be documented using XML comments.</span></span> <span data-ttu-id="e4696-224">Ciò espone tuttavia il funzionamento interno della libreria che potrebbe essere riservato.</span><span class="sxs-lookup"><span data-stu-id="e4696-224">However, this exposes the inner (potentially confidential) workings of your library.</span></span>
- <span data-ttu-id="e4696-225">Il minimo necessario è che i tipi e i loro membri abbiano i tag `<summary>` perché il loro contenuto è necessario per IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="e4696-225">At a bare minimum, types and their members should have a `<summary>` tag because its content is needed for IntelliSense.</span></span>
- <span data-ttu-id="e4696-226">Il testo della documentazione deve essere scritto usando frasi complete che terminano con un punto.</span><span class="sxs-lookup"><span data-stu-id="e4696-226">Documentation text should be written using complete sentences ending with full stops.</span></span>
- <span data-ttu-id="e4696-227">Le classi parziali sono completamente supportate e le informazioni sulla documentazione verranno concatenate in una singola voce per tale tipo.</span><span class="sxs-lookup"><span data-stu-id="e4696-227">Partial classes are fully supported, and documentation information will be concatenated into a single entry for that type.</span></span>
- <span data-ttu-id="e4696-228">Il compilatore verifica la sintassi `<param>` `<see>`dei `<seealso>`tag `<typeparam>` `<exception>`, `<include>`, , , e .</span><span class="sxs-lookup"><span data-stu-id="e4696-228">The compiler verifies the syntax of the `<exception>`, `<include>`, `<param>`, `<see>`, `<seealso>`, and `<typeparam>` tags.</span></span>
- <span data-ttu-id="e4696-229">Il compilatore convalida i parametri che contengono i percorsi dei file e i riferimenti ad altre parti del codice.</span><span class="sxs-lookup"><span data-stu-id="e4696-229">The compiler validates the parameters that contain file paths and references to other parts of the code.</span></span>

## <a name="see-also"></a><span data-ttu-id="e4696-230">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e4696-230">See also</span></span>

- [<span data-ttu-id="e4696-231">Commenti in formato documentazione XML (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="e4696-231">XML Documentation Comments (C# Programming Guide)</span></span>](programming-guide/xmldoc/index.md)
- [<span data-ttu-id="e4696-232">Tag consigliati per i commenti relativi alla documentazione (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="e4696-232">Recommended Tags for Documentation Comments (C# Programming Guide)</span></span>](programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
