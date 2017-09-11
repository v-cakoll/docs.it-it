---
title: Documentazione del codice con i commenti XML
description: Informazioni su come documentare il codice con commenti della documentazione XML e generare un file di documentazione XML in fase di compilazione.
keywords: .NET, .NET Core
author: BillWagner
ms.author: wiwagn
ms.date: 02/14/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 8e75e317-4a55-45f2-a866-e76124171838
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 0cb5725a70d94173c8596f818dcaa6eb2de13bcc
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---

# <a name="documenting-your-code-with-xml-comments"></a><span data-ttu-id="7bd9e-104">Documentazione del codice con i commenti XML</span><span class="sxs-lookup"><span data-stu-id="7bd9e-104">Documenting your code with XML comments</span></span>

<span data-ttu-id="7bd9e-105">I commenti in formato documentazione XML sono commenti speciali, aggiunti alla definizione di ogni tipo o membro definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="7bd9e-105">XML documentation comments are a special kind of comment, added above the definition of any user-defined type or member.</span></span> <span data-ttu-id="7bd9e-106">Sono speciali perché possono essere elaborati dal compilatore per generare un file di documentazione XML in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="7bd9e-106">They are special because they can be processed by the compiler to generate an XML documentation file at compile time.</span></span>
<span data-ttu-id="7bd9e-107">Il file XML generato dal compilatore può essere distribuito insieme agli assembly .NET in modo che Visual Studio e altri IDE possano usare IntelliSense per visualizzare informazioni rapide su tipi o membri.</span><span class="sxs-lookup"><span data-stu-id="7bd9e-107">The compiler generated XML file can be distributed alongside your .NET assembly so that Visual Studio and other IDEs can use IntelliSense to show quick information about types or members.</span></span> <span data-ttu-id="7bd9e-108">È anche possibile eseguire il file XML tramite strumenti, ad esempio [DocFX](https://dotnet.github.io/docfx/) e [Sandcastle](https://github.com/EWSoftware/SHFB) per generare i siti Web di riferimento all'API.</span><span class="sxs-lookup"><span data-stu-id="7bd9e-108">Additionally, the XML file can be run through tools like [DocFX](https://dotnet.github.io/docfx/) and [Sandcastle](https://github.com/EWSoftware/SHFB) to generate API reference websites.</span></span>

<span data-ttu-id="7bd9e-109">I commenti in formato documentazione XML, come tutti gli altri commenti, vengono ignorati dal compilatore.</span><span class="sxs-lookup"><span data-stu-id="7bd9e-109">XML documentation comments, like all other comments, are ignored by the compiler.</span></span>

<span data-ttu-id="7bd9e-110">È possibile generare il file XML in fase di compilazione eseguendo una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7bd9e-110">You can generate the XML file at compile time by doing one of the following:</span></span>

- <span data-ttu-id="7bd9e-111">Se si sviluppa un'applicazione con .NET Core dalla riga di comando, è possibile aggiungere un [elemento DocumentationFile](http://docs.microsoft.com/visualstudio/msbuild/common-msbuild-project-properties) alla sezione `<PropertyGroup>` del file di progetto csproj.</span><span class="sxs-lookup"><span data-stu-id="7bd9e-111">If you are developing an application with .NET Core from the command line, you can add a [DocumentationFile element](http://docs.microsoft.com/visualstudio/msbuild/common-msbuild-project-properties) to the `<PropertyGroup>` section of your .csproj project file.</span></span> <span data-ttu-id="7bd9e-112">L'esempio seguente genera un file XML nella directory del progetto con lo stesso nome file radice del progetto:</span><span class="sxs-lookup"><span data-stu-id="7bd9e-112">The following example generates an XML file in the project directory with the same root filename as the project:</span></span>

   ```xml
   <DocumentationFile>$(MSBuildProjectName).xml</DocumentationFile>
   ```

   <span data-ttu-id="7bd9e-113">È anche possibile specificare l'esatto percorso assoluto o relativo e il nome del file XML.</span><span class="sxs-lookup"><span data-stu-id="7bd9e-113">You can also specify the exact absolute or relative path and name of the XML file.</span></span> <span data-ttu-id="7bd9e-114">L'esempio seguente genera il file XML nella stessa directory della versione di debug di un'applicazione:</span><span class="sxs-lookup"><span data-stu-id="7bd9e-114">The following example generates the XML file in the same directory as the debug version of an application:</span></span>

    ```xml
   <DocumentationFile>bin\Debug\netcoreapp1.0\App.xml</DocumentationFile>
   ```

- <span data-ttu-id="7bd9e-115">Se si sviluppa un'applicazione tramite Visual Studio, fare clic con il pulsante destro del mouse sul progetto e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="7bd9e-115">If you are developing an application using Visual Studio, right-click on the project and select **Properties**.</span></span> <span data-ttu-id="7bd9e-116">Nella finestra di dialogo Proprietà selezionare la scheda **Genera** e controllare **File di documentazione XML**.</span><span class="sxs-lookup"><span data-stu-id="7bd9e-116">In the properties dialog, select the **Build** tab, and check **XML documentation file**.</span></span> <span data-ttu-id="7bd9e-117">È anche possibile modificare il percorso in cui il compilatore scrive il file.</span><span class="sxs-lookup"><span data-stu-id="7bd9e-117">You can also change the location to which the compiler writes the file.</span></span> 

- <span data-ttu-id="7bd9e-118">Se si sta compilando un'applicazione .NET Framework dalla riga di comando, aggiungere l'[opzione di compilazione /doc](language-reference/compiler-options/doc-compiler-option.md) durante la compilazione.</span><span class="sxs-lookup"><span data-stu-id="7bd9e-118">If you are compiling a .NET Framework application from the command line, add the [/doc compiler option](language-reference/compiler-options/doc-compiler-option.md) when compiling.</span></span>  

<span data-ttu-id="7bd9e-119">I commenti in formato documentazione XML usano tre barre (`///`) e un corpo di commento in formato XML.</span><span class="sxs-lookup"><span data-stu-id="7bd9e-119">XML documentation comments use triple forward slashes (`///`) and an XML formatted comment body.</span></span> <span data-ttu-id="7bd9e-120">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="7bd9e-120">For example:</span></span>

<span data-ttu-id="7bd9e-121">[!code-csharp[Commento in formato documentazione XML](../../samples/snippets/csharp/concepts/codedoc/xml-comment.cs)]</span><span class="sxs-lookup"><span data-stu-id="7bd9e-121">[!code-csharp[XML Documentation Comment](../../samples/snippets/csharp/concepts/codedoc/xml-comment.cs)]</span></span>

## <a name="walkthrough"></a><span data-ttu-id="7bd9e-122">Procedura dettagliata</span><span class="sxs-lookup"><span data-stu-id="7bd9e-122">Walkthrough</span></span>

<span data-ttu-id="7bd9e-123">In questa sezione viene illustrato come documentare una semplice libreria matematica per descrivere il meccanismo che gli sviluppatori possono usare.</span><span class="sxs-lookup"><span data-stu-id="7bd9e-123">Let's walk through documenting a very basic math library to make it easy for new developers to understand/contribute and for third party developers to use.</span></span>

<span data-ttu-id="7bd9e-124">Questo è il codice per la semplice libreria matematica:</span><span class="sxs-lookup"><span data-stu-id="7bd9e-124">Here's code for the simple math library:</span></span>

<span data-ttu-id="7bd9e-125">[!code-csharp[Libreria di esempio](../../samples/snippets/csharp/concepts/codedoc/sample-library.cs)]</span><span class="sxs-lookup"><span data-stu-id="7bd9e-125">[!code-csharp[Sample Library](../../samples/snippets/csharp/concepts/codedoc/sample-library.cs)]</span></span>

<span data-ttu-id="7bd9e-126">La libreria di esempio supporta quattro operazioni aritmetiche principali, ovvero `add`, `subtract`, `multiply` e `divide` su tipi di dati `int` e `double`.</span><span class="sxs-lookup"><span data-stu-id="7bd9e-126">The sample library supports four major arithmetic operations `add`, `subtract`, `multiply` and `divide` on `int` and `double` data types.</span></span>

<span data-ttu-id="7bd9e-127">Si vuole ora creare un documento di riferimento all'API dal codice per sviluppatori di terze parti che usano la libreria ma non hanno accesso al codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="7bd9e-127">Now you want to be able to create an API reference document from your code for third party developers who use your library but don't have access to the source code.</span></span>
<span data-ttu-id="7bd9e-128">Come indicato precedentemente, è possibile usare i tag in formato documentazione XML per ottenere questo risultato. Verranno ora illustrati i tag XML standard supportati dal compilatore C#.</span><span class="sxs-lookup"><span data-stu-id="7bd9e-128">As mentioned earlier XML documentation tags can be used to achieve this, You will now be introduced to the standard XML tags the C# compiler supports.</span></span>

### <a name="ltsummarygt"></a><span data-ttu-id="7bd9e-129">&lt;summary&gt;</span><span class="sxs-lookup"><span data-stu-id="7bd9e-129">&lt;summary&gt;</span></span>

<span data-ttu-id="7bd9e-130">Il tag `<summary>` aggiunge brevi informazioni su un tipo o membro.</span><span class="sxs-lookup"><span data-stu-id="7bd9e-130">The `<summary>` tag adds brief information about a type or member.</span></span>
<span data-ttu-id="7bd9e-131">Ne viene illustrato l'uso aggiungendolo alla definizione di classe `Math` e al primo metodo `Add`.</span><span class="sxs-lookup"><span data-stu-id="7bd9e-131">I'll demonstrate its use by adding it to the `Math` class definition and the first `Add` method.</span></span> <span data-ttu-id="7bd9e-132">È possibile applicarlo al resto del codice.</span><span class="sxs-lookup"><span data-stu-id="7bd9e-132">Feel free to apply it to the rest of your code.</span></span>

<span data-ttu-id="7bd9e-133">[!code-csharp[Tag summary](../../samples/snippets/csharp/concepts/codedoc/summary-tag.cs)]</span><span class="sxs-lookup"><span data-stu-id="7bd9e-133">[!code-csharp[Summary Tag](../../samples/snippets/csharp/concepts/codedoc/summary-tag.cs)]</span></span>

<span data-ttu-id="7bd9e-134">Il tag `<summary>` è molto importante ed è consigliabile includerlo perché il suo contenuto è l'origine principale di informazioni sul tipo o sul membro in IntelliSense o in un documento di riferimento all'API.</span><span class="sxs-lookup"><span data-stu-id="7bd9e-134">The `<summary>` tag is very important, and we recommend that you include it because its content is the primary source of type or member information in IntelliSense or an API reference document.</span></span>

### <a name="ltremarksgt"></a><span data-ttu-id="7bd9e-135">&lt;remarks&gt;</span><span class="sxs-lookup"><span data-stu-id="7bd9e-135">&lt;remarks&gt;</span></span>

<span data-ttu-id="7bd9e-136">Il tag `<remarks>` integra le informazioni sui tipi o membri definiti dal tag `<summary>`.</span><span class="sxs-lookup"><span data-stu-id="7bd9e-136">The `<remarks>` tag supplements the information about types or members that the `<summary>` tag provides.</span></span> <span data-ttu-id="7bd9e-137">In questo esempio, sarà sufficiente aggiungerlo alla classe.</span><span class="sxs-lookup"><span data-stu-id="7bd9e-137">In this example, you'll just add it to the class.</span></span>

<span data-ttu-id="7bd9e-138">[!code-csharp[Tag remarks](../../samples/snippets/csharp/concepts/codedoc/remarks-tag.cs)]</span><span class="sxs-lookup"><span data-stu-id="7bd9e-138">[!code-csharp[Remarks Tag](../../samples/snippets/csharp/concepts/codedoc/remarks-tag.cs)]</span></span>

### <a name="ltreturnsgt"></a><span data-ttu-id="7bd9e-139">&lt;returns&gt;</span><span class="sxs-lookup"><span data-stu-id="7bd9e-139">&lt;returns&gt;</span></span>

<span data-ttu-id="7bd9e-140">Il tag `<returns>` descrive il valore restituito di una dichiarazione di metodo.</span><span class="sxs-lookup"><span data-stu-id="7bd9e-140">The `<returns>` tag describes the return value of a method declaration.</span></span>
<span data-ttu-id="7bd9e-141">Come in precedenza, nell'esempio seguente viene illustrato il tag `<returns>` nel primo metodo `Add`.</span><span class="sxs-lookup"><span data-stu-id="7bd9e-141">As before, the following example illustrates the `<returns>` tag on the first `Add` method.</span></span> <span data-ttu-id="7bd9e-142">È possibile eseguire questa operazione su altri metodi.</span><span class="sxs-lookup"><span data-stu-id="7bd9e-142">You can do the same on other methods.</span></span>

<span data-ttu-id="7bd9e-143">[!code-csharp[Tag returns](../../samples/snippets/csharp/concepts/codedoc/returns-tag.cs)]</span><span class="sxs-lookup"><span data-stu-id="7bd9e-143">[!code-csharp[Returns Tag](../../samples/snippets/csharp/concepts/codedoc/returns-tag.cs)]</span></span>

### <a name="ltvaluegt"></a><span data-ttu-id="7bd9e-144">&lt;value&gt;</span><span class="sxs-lookup"><span data-stu-id="7bd9e-144">&lt;value&gt;</span></span>

<span data-ttu-id="7bd9e-145">Il tag `<value>` è simile al tag `<returns>`, ad eccezione del fatto che viene usato per le proprietà.</span><span class="sxs-lookup"><span data-stu-id="7bd9e-145">The `<value>` tag is similar to the `<returns>` tag, except that you use it for properties.</span></span>
<span data-ttu-id="7bd9e-146">Se la libreria `Math` avesse una proprietà statica denominata `PI`, questo tag dovrebbe essere usato nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="7bd9e-146">Assuming your `Math` library had a static property called `PI`, here's how you'd use this tag:</span></span>

<span data-ttu-id="7bd9e-147">[!code-csharp[Tag value](../../samples/snippets/csharp/concepts/codedoc/value-tag.cs)]</span><span class="sxs-lookup"><span data-stu-id="7bd9e-147">[!code-csharp[Value Tag](../../samples/snippets/csharp/concepts/codedoc/value-tag.cs)]</span></span>

### <a name="ltexamplegt"></a><span data-ttu-id="7bd9e-148">&lt;example&gt;</span><span class="sxs-lookup"><span data-stu-id="7bd9e-148">&lt;example&gt;</span></span>

<span data-ttu-id="7bd9e-149">Si usa il tag `<example>` per includere un esempio nella documentazione XML.</span><span class="sxs-lookup"><span data-stu-id="7bd9e-149">You use the `<example>` tag to include an example in your XML documentation.</span></span>
<span data-ttu-id="7bd9e-150">Ciò comporta l'uso del tag `<code>` del figlio.</span><span class="sxs-lookup"><span data-stu-id="7bd9e-150">This involves using the child `<code>` tag.</span></span>

<span data-ttu-id="7bd9e-151">[!code-csharp[Tag example](../../samples/snippets/csharp/concepts/codedoc/example-tag.cs)]</span><span class="sxs-lookup"><span data-stu-id="7bd9e-151">[!code-csharp[Example Tag](../../samples/snippets/csharp/concepts/codedoc/example-tag.cs)]</span></span>

<span data-ttu-id="7bd9e-152">Il tag `code` mantiene le interruzioni di riga e il rientro per esempi più lunghi.</span><span class="sxs-lookup"><span data-stu-id="7bd9e-152">The `code` tag preserves line breaks and indentation for longer examples.</span></span>

### <a name="ltparagt"></a><span data-ttu-id="7bd9e-153">&lt;para&gt;</span><span class="sxs-lookup"><span data-stu-id="7bd9e-153">&lt;para&gt;</span></span>

<span data-ttu-id="7bd9e-154">Si usa il tag `<para>` per formattare il contenuto all'interno del tag padre.</span><span class="sxs-lookup"><span data-stu-id="7bd9e-154">You use the `<para>` tag to format the content within its parent tag.</span></span> <span data-ttu-id="7bd9e-155">`<para>` viene in genere usato all'interno di un tag, ad esempio `<remarks>` o `<returns>`, per dividere il testo in paragrafi.</span><span class="sxs-lookup"><span data-stu-id="7bd9e-155">`<para>` is usually used inside a tag, such as `<remarks>` or `<returns>`, to divide text into paragraphs.</span></span>
<span data-ttu-id="7bd9e-156">È possibile formattare il contenuto del tag `<remarks>` per la definizione delle classi.</span><span class="sxs-lookup"><span data-stu-id="7bd9e-156">You can format the contents of the `<remarks>` tag for your class definition.</span></span>

<span data-ttu-id="7bd9e-157">[!code-csharp[Tag para](../../samples/snippets/csharp/concepts/codedoc/para-tag.cs)]</span><span class="sxs-lookup"><span data-stu-id="7bd9e-157">[!code-csharp[Para Tag](../../samples/snippets/csharp/concepts/codedoc/para-tag.cs)]</span></span>

### <a name="ltcgt"></a><span data-ttu-id="7bd9e-158">&lt;c&gt;</span><span class="sxs-lookup"><span data-stu-id="7bd9e-158">&lt;c&gt;</span></span>

<span data-ttu-id="7bd9e-159">Nella formattazione si usa il tag `<c>` per contrassegnare parte del testo come codice.</span><span class="sxs-lookup"><span data-stu-id="7bd9e-159">Still on the topic of formatting, you use the `<c>` tag for marking part of text as code.</span></span>
<span data-ttu-id="7bd9e-160">È simile al tag `<code>`, ma è inline.</span><span class="sxs-lookup"><span data-stu-id="7bd9e-160">It's like the `<code>` tag but inline.</span></span> <span data-ttu-id="7bd9e-161">È utile quando si vuole visualizzare un esempio breve di codice come parte del contenuto del tag.</span><span class="sxs-lookup"><span data-stu-id="7bd9e-161">It's useful when you want to show a quick code example as part of a tag's content.</span></span>
<span data-ttu-id="7bd9e-162">Ora viene aggiornata la documentazione per la classe `Math`.</span><span class="sxs-lookup"><span data-stu-id="7bd9e-162">Let's update the documentation for the `Math` class.</span></span>

<span data-ttu-id="7bd9e-163">[!code-csharp[Tag C](../../samples/snippets/csharp/concepts/codedoc/c-tag.cs)]</span><span class="sxs-lookup"><span data-stu-id="7bd9e-163">[!code-csharp[C Tag](../../samples/snippets/csharp/concepts/codedoc/c-tag.cs)]</span></span>

### <a name="ltexceptiongt"></a><span data-ttu-id="7bd9e-164">&lt;exception&gt;</span><span class="sxs-lookup"><span data-stu-id="7bd9e-164">&lt;exception&gt;</span></span>

<span data-ttu-id="7bd9e-165">Tramite il tag `<exception>` è possibile comunicare agli sviluppatori che un metodo può generare eccezioni specifiche.</span><span class="sxs-lookup"><span data-stu-id="7bd9e-165">By using the `<exception>` tag, you let your developers know that a method can throw specific exceptions.</span></span>
<span data-ttu-id="7bd9e-166">Esaminando la libreria `Math`, è possibile vedere che entrambi i metodi `Add` generano un'eccezione se viene soddisfatta una determinata condizione.</span><span class="sxs-lookup"><span data-stu-id="7bd9e-166">Looking at your `Math` library, you can see that both `Add` methods throw an exception if a certain condition is met.</span></span> <span data-ttu-id="7bd9e-167">Nonostante non sia così ovvio, anche il metodo `Divide` integer genera eccezioni se il parametro `b` è uguale a zero.</span><span class="sxs-lookup"><span data-stu-id="7bd9e-167">Not so obvious, though, is that integer `Divide` method throws as well if the `b` parameter is zero.</span></span> <span data-ttu-id="7bd9e-168">Aggiungere ora la documentazione sull'eccezione a questo metodo.</span><span class="sxs-lookup"><span data-stu-id="7bd9e-168">Now add exception documentation to this method.</span></span>

<span data-ttu-id="7bd9e-169">[!code-csharp[Tag exception](../../samples/snippets/csharp/concepts/codedoc/exception-tag.cs)]</span><span class="sxs-lookup"><span data-stu-id="7bd9e-169">[!code-csharp[Exception Tag](../../samples/snippets/csharp/concepts/codedoc/exception-tag.cs)]</span></span>

<span data-ttu-id="7bd9e-170">L'attributo `cref` rappresenta un riferimento ad un'eccezione disponibile dall'ambiente di compilazione corrente.</span><span class="sxs-lookup"><span data-stu-id="7bd9e-170">The `cref` attribute represents a reference to an exception that is available from the current compilation environment.</span></span>
<span data-ttu-id="7bd9e-171">Ciò può essere qualsiasi tipo definito nel progetto o in un assembly di riferimento.</span><span class="sxs-lookup"><span data-stu-id="7bd9e-171">This can be any type defined in the project or a referenced assembly.</span></span> <span data-ttu-id="7bd9e-172">Il compilatore genererà un avviso se il relativo valore non può essere risolto.</span><span class="sxs-lookup"><span data-stu-id="7bd9e-172">The compiler will issue a warning if its value cannot be resolved.</span></span>

### <a name="ltseegt"></a><span data-ttu-id="7bd9e-173">&lt;see&gt;</span><span class="sxs-lookup"><span data-stu-id="7bd9e-173">&lt;see&gt;</span></span>

<span data-ttu-id="7bd9e-174">Il tag `<see>` consente di creare un collegamento selezionabile per una pagina di documentazione per un altro elemento di codice.</span><span class="sxs-lookup"><span data-stu-id="7bd9e-174">The `<see>` tag lets you create a clickable link to a documentation page for another code element.</span></span> <span data-ttu-id="7bd9e-175">Nel prossimo esempio, verrà creato un collegamento selezionabile tra i due metodi `Add`.</span><span class="sxs-lookup"><span data-stu-id="7bd9e-175">In our next example, we'll create a clickable link between the two `Add` methods.</span></span>

<span data-ttu-id="7bd9e-176">[!code-csharp[Tag see](../../samples/snippets/csharp/concepts/codedoc/see-tag.cs)]</span><span class="sxs-lookup"><span data-stu-id="7bd9e-176">[!code-csharp[See Tag](../../samples/snippets/csharp/concepts/codedoc/see-tag.cs)]</span></span>

<span data-ttu-id="7bd9e-177">L'attributo `cref` è **obbligatorio** e rappresenta un riferimento a un tipo o al suo membro disponibile dall'ambiente di compilazione corrente.</span><span class="sxs-lookup"><span data-stu-id="7bd9e-177">The `cref` is a **required** attribute that represents a reference to a type or its member that is available from the current compilation environment.</span></span> <span data-ttu-id="7bd9e-178">Ciò può essere qualsiasi tipo definito nel progetto o in un assembly di riferimento.</span><span class="sxs-lookup"><span data-stu-id="7bd9e-178">This can be any type defined in the project or a referenced assembly.</span></span>

### <a name="ltseealsogt"></a><span data-ttu-id="7bd9e-179">&lt;seealso&gt;</span><span class="sxs-lookup"><span data-stu-id="7bd9e-179">&lt;seealso&gt;</span></span>

<span data-ttu-id="7bd9e-180">Il tag `<seealso>` si usa allo stesso modo del tag `<see>`.</span><span class="sxs-lookup"><span data-stu-id="7bd9e-180">You use the `<seealso>` tag in the same way you do the `<see>` tag.</span></span> <span data-ttu-id="7bd9e-181">L'unica differenza è che il relativo contenuto viene in genere inserito in una sezione "Vedere anche".</span><span class="sxs-lookup"><span data-stu-id="7bd9e-181">The only difference is that its content is typically placed in a "See Also" section.</span></span> <span data-ttu-id="7bd9e-182">Di seguito si aggiungerà un tag `seealso` al metodo `Add` integer per fare riferimento ad altri metodi della classe che accettano parametri integer:</span><span class="sxs-lookup"><span data-stu-id="7bd9e-182">Here we'll add a `seealso` tag on the integer `Add` method to reference other methods in the class that accept integer parameters:</span></span>

<span data-ttu-id="7bd9e-183">[!code-csharp[Tag seealso](../../samples/snippets/csharp/concepts/codedoc/seealso-tag.cs)]</span><span class="sxs-lookup"><span data-stu-id="7bd9e-183">[!code-csharp[Seealso Tag](../../samples/snippets/csharp/concepts/codedoc/seealso-tag.cs)]</span></span>

<span data-ttu-id="7bd9e-184">L'attributo `cref` rappresenta un riferimento a un tipo o al suo membro disponibile dall'ambiente di compilazione corrente.</span><span class="sxs-lookup"><span data-stu-id="7bd9e-184">The `cref` attribute represents a reference to a type or its member that is available from the current compilation environment.</span></span>
<span data-ttu-id="7bd9e-185">Ciò può essere qualsiasi tipo definito nel progetto o in un assembly di riferimento.</span><span class="sxs-lookup"><span data-stu-id="7bd9e-185">This can be any type defined in the project or a referenced assembly.</span></span>

### <a name="ltparamgt"></a><span data-ttu-id="7bd9e-186">&lt;param&gt;</span><span class="sxs-lookup"><span data-stu-id="7bd9e-186">&lt;param&gt;</span></span>

<span data-ttu-id="7bd9e-187">Il tag `<param>` viene usato per descrivere i parametri del metodo.</span><span class="sxs-lookup"><span data-stu-id="7bd9e-187">You use the `<param>` tag to describe a method's parameters.</span></span> <span data-ttu-id="7bd9e-188">Di seguito viene illustrato un esempio sul metodo `Add` double. Il parametro descritto dal tag viene specificato nell'attributo `name` **obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="7bd9e-188">Here's an example on the double `Add` method: The parameter the tag describes is specified in the **required** `name` attribute.</span></span>

<span data-ttu-id="7bd9e-189">[!code-csharp[Tag param](../../samples/snippets/csharp/concepts/codedoc/param-tag.cs)]</span><span class="sxs-lookup"><span data-stu-id="7bd9e-189">[!code-csharp[Param Tag](../../samples/snippets/csharp/concepts/codedoc/param-tag.cs)]</span></span>

### <a name="lttypeparamgt"></a><span data-ttu-id="7bd9e-190">&lt;typeparam&gt;</span><span class="sxs-lookup"><span data-stu-id="7bd9e-190">&lt;typeparam&gt;</span></span>

<span data-ttu-id="7bd9e-191">Il tag `<typeparam>` viene usato allo stesso modo del tag `<param>`, ma in dichiarazioni di tipo o di metodo generico per descrivere un parametro generico.</span><span class="sxs-lookup"><span data-stu-id="7bd9e-191">You use `<typeparam>` tag just like the `<param>` tag but for generic type or method declarations to describe a generic parameter.</span></span>
<span data-ttu-id="7bd9e-192">Aggiungere un metodo generico semplice alla classe `Math` per verificare se una quantità è maggiore di un'altra.</span><span class="sxs-lookup"><span data-stu-id="7bd9e-192">Add a quick generic method to your `Math` class to check if one quantity is greater than another.</span></span>

<span data-ttu-id="7bd9e-193">[!code-csharp[Tag typeparam](../../samples/snippets/csharp/concepts/codedoc/typeparam-tag.cs)]</span><span class="sxs-lookup"><span data-stu-id="7bd9e-193">[!code-csharp[Typeparam Tag](../../samples/snippets/csharp/concepts/codedoc/typeparam-tag.cs)]</span></span>

### <a name="ltparamrefgt"></a><span data-ttu-id="7bd9e-194">&lt;paramref&gt;</span><span class="sxs-lookup"><span data-stu-id="7bd9e-194">&lt;paramref&gt;</span></span>

<span data-ttu-id="7bd9e-195">A volte è possibile che durante la descrizione dell'operazione di un metodo in un tag `<summary>` si vuole fare un riferimento a un parametro.</span><span class="sxs-lookup"><span data-stu-id="7bd9e-195">Sometimes you might be in the middle of describing what a method does in what could be a `<summary>` tag, and you might want to make a reference to a parameter.</span></span> <span data-ttu-id="7bd9e-196">Il tag `<paramref>` è molto utile per questa operazione.</span><span class="sxs-lookup"><span data-stu-id="7bd9e-196">The `<paramref>` tag is great for just this.</span></span> <span data-ttu-id="7bd9e-197">Ora si aggiorna il riepilogo del metodo `Add` basato su double.</span><span class="sxs-lookup"><span data-stu-id="7bd9e-197">Let's update the summary of our double based `Add` method.</span></span> <span data-ttu-id="7bd9e-198">Analogamente al tag `<param>`, il nome del parametro viene specificato nell'attributo `name` **obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="7bd9e-198">Like the `<param>` tag the parameter name is specified in the **required** `name` attribute.</span></span>

<span data-ttu-id="7bd9e-199">[!code-csharp[Tag paramref](../../samples/snippets/csharp/concepts/codedoc/paramref-tag.cs)]</span><span class="sxs-lookup"><span data-stu-id="7bd9e-199">[!code-csharp[Paramref Tag](../../samples/snippets/csharp/concepts/codedoc/paramref-tag.cs)]</span></span>

### <a name="lttypeparamrefgt"></a><span data-ttu-id="7bd9e-200">&lt;typeparamref&gt;</span><span class="sxs-lookup"><span data-stu-id="7bd9e-200">&lt;typeparamref&gt;</span></span>

<span data-ttu-id="7bd9e-201">Il tag `<typeparamref>` viene usato allo stesso modo del tag `<paramref>`, ma in dichiarazioni di tipo o di metodo generico per descrivere un parametro generico.</span><span class="sxs-lookup"><span data-stu-id="7bd9e-201">You use `<typeparamref>` tag just like the `<paramref>` tag but for generic type or method declarations to describe a generic parameter.</span></span>
<span data-ttu-id="7bd9e-202">È possibile usare lo stesso metodo generico creato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="7bd9e-202">You can use the same generic method you previously created.</span></span>

<span data-ttu-id="7bd9e-203">[!code-csharp[Tag typeparamref](../../samples/snippets/csharp/concepts/codedoc/typeparamref-tag.cs)]</span><span class="sxs-lookup"><span data-stu-id="7bd9e-203">[!code-csharp[Typeparamref Tag](../../samples/snippets/csharp/concepts/codedoc/typeparamref-tag.cs)]</span></span>

### <a name="ltlistgt"></a><span data-ttu-id="7bd9e-204">&lt;list&gt;</span><span class="sxs-lookup"><span data-stu-id="7bd9e-204">&lt;list&gt;</span></span>

<span data-ttu-id="7bd9e-205">Il tag `<list>` viene usato per formattare le informazioni sulla documentazione come elenco ordinato, elenco non ordinato o tabella.</span><span class="sxs-lookup"><span data-stu-id="7bd9e-205">You use the `<list>` tag to format documentation information as an ordered list, unordered list or table.</span></span>
<span data-ttu-id="7bd9e-206">Creare un elenco non ordinato di ogni operazione matematica supportata dalla libreria `Math`.</span><span class="sxs-lookup"><span data-stu-id="7bd9e-206">Make an unordered list of every math operation your `Math` library supports.</span></span>

<span data-ttu-id="7bd9e-207">[!code-csharp[Tag list](../../samples/snippets/csharp/concepts/codedoc/list-tag.cs)]</span><span class="sxs-lookup"><span data-stu-id="7bd9e-207">[!code-csharp[List Tag](../../samples/snippets/csharp/concepts/codedoc/list-tag.cs)]</span></span>

<span data-ttu-id="7bd9e-208">È possibile creare un elenco ordinato o una tabella sostituendo l'attributo `type` con `number` o `table` rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="7bd9e-208">You can make an ordered list or table by changing the `type` attribute to `number` or `table`, respectively.</span></span>

### <a name="putting-it-all-together"></a><span data-ttu-id="7bd9e-209">Riassumendo</span><span class="sxs-lookup"><span data-stu-id="7bd9e-209">Putting it all together</span></span>

<span data-ttu-id="7bd9e-210">Dopo aver eseguito questa esercitazione e applicato i tag al codice, dove necessario, il codice dovrebbe ora essere simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="7bd9e-210">If you've followed this tutorial and applied the tags to your code where necessary, your code should now look similar to the following:</span></span>

<span data-ttu-id="7bd9e-211">[!code-csharp[Libreria con tag](../../samples/snippets/csharp/concepts/codedoc/tagged-library.cs)]</span><span class="sxs-lookup"><span data-stu-id="7bd9e-211">[!code-csharp[Tagged Library](../../samples/snippets/csharp/concepts/codedoc/tagged-library.cs)]</span></span>

<span data-ttu-id="7bd9e-212">Dal codice, è possibile generare un sito Web di documentazione dettagliata completa di riferimenti incrociati.</span><span class="sxs-lookup"><span data-stu-id="7bd9e-212">From your code, you can generate a detailed documentation website complete with clickable cross-references.</span></span> <span data-ttu-id="7bd9e-213">Ciò però potrebbe rendere il codice più difficile da leggere.</span><span class="sxs-lookup"><span data-stu-id="7bd9e-213">But you're faced with another problem: your code has become hard to read.</span></span>
<span data-ttu-id="7bd9e-214">In quanto la presenza di un numero elevato di informazioni costituisce un problema molto serio per gli sviluppatori che vogliono contribuire al codice.</span><span class="sxs-lookup"><span data-stu-id="7bd9e-214">There's so much information to sift through that this is going to be a nightmare for any developer who wants to contribute to this code.</span></span> <span data-ttu-id="7bd9e-215">Fortunatamente c'è un tag XML che consente di affrontare questo problema:</span><span class="sxs-lookup"><span data-stu-id="7bd9e-215">Thankfully there's an XML tag that can help you deal with this:</span></span>

### <a name="ltincludegt"></a><span data-ttu-id="7bd9e-216">&lt;include&gt;</span><span class="sxs-lookup"><span data-stu-id="7bd9e-216">&lt;include&gt;</span></span>

<span data-ttu-id="7bd9e-217">Il tag `<include>` consente di fare riferimento ai commenti in un file XML separato che descrivono i tipi e i membri nel codice sorgente anziché inserire commenti in formato documentazione direttamente nel file del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="7bd9e-217">The `<include>` tag lets you refer to comments in a separate XML file that describe the types and members in your source code, as opposed to placing documentation comments directly in your source code file.</span></span>

<span data-ttu-id="7bd9e-218">Ora si spostano tutti i tag XML in un file XML separato denominato `docs.xml`.</span><span class="sxs-lookup"><span data-stu-id="7bd9e-218">Now you're going to move all your XML tags into a separate XML file named `docs.xml`.</span></span> <span data-ttu-id="7bd9e-219">È possibile assegnare al file un nome qualsiasi.</span><span class="sxs-lookup"><span data-stu-id="7bd9e-219">Feel free to name the file whatever you want.</span></span>

<span data-ttu-id="7bd9e-220">[!code-xml[Codice XML di esempio](../../samples/snippets/csharp/concepts/codedoc/include.xml)]</span><span class="sxs-lookup"><span data-stu-id="7bd9e-220">[!code-xml[Sample XML](../../samples/snippets/csharp/concepts/codedoc/include.xml)]</span></span>

<span data-ttu-id="7bd9e-221">Nel codice XML precedente, i commenti in formato documentazione di ogni membro vengono visualizzati direttamente all'interno di un tag denominato dopo le operazioni eseguite.</span><span class="sxs-lookup"><span data-stu-id="7bd9e-221">In the above XML, each member's documentation comments appear directly inside a tag named after what they do.</span></span> <span data-ttu-id="7bd9e-222">È possibile scegliere una strategia personalizzata.</span><span class="sxs-lookup"><span data-stu-id="7bd9e-222">You can choose your own strategy.</span></span> <span data-ttu-id="7bd9e-223">Ora che i commenti XML si trovano in un file separato, di seguito viene illustrato come il codice può essere reso più leggibile usando il tag `<include>`:</span><span class="sxs-lookup"><span data-stu-id="7bd9e-223">Now that you have your XML comments in a separate file, let's see how your code can be made more readable by using the `<include>` tag:</span></span>

<span data-ttu-id="7bd9e-224">[!code-csharp[Tag include](../../samples/snippets/csharp/concepts/codedoc/include-tag.cs)]</span><span class="sxs-lookup"><span data-stu-id="7bd9e-224">[!code-csharp[Include Tag](../../samples/snippets/csharp/concepts/codedoc/include-tag.cs)]</span></span>

<span data-ttu-id="7bd9e-225">Infine si avrà un codice di nuovo leggibile e nessuna informazione sulla documentazione è andata persa.</span><span class="sxs-lookup"><span data-stu-id="7bd9e-225">And there you have it: our code is back to being readable, and no documentation information has been lost.</span></span> 

<span data-ttu-id="7bd9e-226">L'attributo `filename` rappresenta il nome del file XML che contiene la documentazione.</span><span class="sxs-lookup"><span data-stu-id="7bd9e-226">The `filename` attribute represents the name of the XML file containing the documentation.</span></span>

<span data-ttu-id="7bd9e-227">L'attributo `path` rappresenta una query [XPath](https://msdn.microsoft.com/library/ms256115.aspx) nel presente `tag name` del `filename` specificato.</span><span class="sxs-lookup"><span data-stu-id="7bd9e-227">The `path` attribute represents an [XPath](https://msdn.microsoft.com/library/ms256115.aspx) query to the `tag name` present in the specified `filename`.</span></span>

<span data-ttu-id="7bd9e-228">L'attributo `name` rappresenta l'identificatore di nome nel tag che precede i commenti.</span><span class="sxs-lookup"><span data-stu-id="7bd9e-228">The `name` attribute represents the name specifier in the tag that precedes the comments.</span></span>

<span data-ttu-id="7bd9e-229">L'attributo `id` che può essere usato al posto di `name` rappresenta l'ID per il tag che precede i commenti.</span><span class="sxs-lookup"><span data-stu-id="7bd9e-229">The `id` attribute which can be used in place of `name` represents the ID for the tag that precedes the comments.</span></span>

### <a name="user-defined-tags"></a><span data-ttu-id="7bd9e-230">Tag definiti dall'utente</span><span class="sxs-lookup"><span data-stu-id="7bd9e-230">User Defined Tags</span></span>

<span data-ttu-id="7bd9e-231">Tutti i tag specificati in precedenza rappresentano i tag riconosciuti dal compilatore C#.</span><span class="sxs-lookup"><span data-stu-id="7bd9e-231">All the tags outlined above represent those that are recognized by the C# compiler.</span></span> <span data-ttu-id="7bd9e-232">Gli utenti comunque possono definire tag personalizzati.</span><span class="sxs-lookup"><span data-stu-id="7bd9e-232">However, a user is free to define their own tags.</span></span>
<span data-ttu-id="7bd9e-233">Alcuni strumenti, ad esempio Sandcastle, offrono supporto per altri tag, ad esempio [`<event>`](http://ewsoftware.github.io/XMLCommentsGuide/html/81bf7ad3-45dc-452f-90d5-87ce2494a182.htm), [`<note>`](http://ewsoftware.github.io/XMLCommentsGuide/html/4302a60f-e4f4-4b8d-a451-5f453c4ebd46.htm) e per [documentare gli spazi dei nomi](http://ewsoftware.github.io/XMLCommentsGuide/html/BD91FAD4-188D-4697-A654-7C07FD47EF31.htm).</span><span class="sxs-lookup"><span data-stu-id="7bd9e-233">Tools like Sandcastle bring support for extra tags like [`<event>`](http://ewsoftware.github.io/XMLCommentsGuide/html/81bf7ad3-45dc-452f-90d5-87ce2494a182.htm), [`<note>`](http://ewsoftware.github.io/XMLCommentsGuide/html/4302a60f-e4f4-4b8d-a451-5f453c4ebd46.htm) and even support [documenting namespaces](http://ewsoftware.github.io/XMLCommentsGuide/html/BD91FAD4-188D-4697-A654-7C07FD47EF31.htm).</span></span>
<span data-ttu-id="7bd9e-234">Gli strumenti di creazione della documentazione interna o personalizzata possono anche essere usati con i tag standard e con più formati di output da HTML a PDF.</span><span class="sxs-lookup"><span data-stu-id="7bd9e-234">Custom or in-house documentation generation tools can also be used with the standard tags and multiple output formats from HTML to PDF can be supported.</span></span>

## <a name="recommendations"></a><span data-ttu-id="7bd9e-235">Suggerimenti</span><span class="sxs-lookup"><span data-stu-id="7bd9e-235">Recommendations</span></span>

<span data-ttu-id="7bd9e-236">La documentazione del codice è consigliabile per vari motivi.</span><span class="sxs-lookup"><span data-stu-id="7bd9e-236">Documenting code is recommended for many reasons.</span></span> <span data-ttu-id="7bd9e-237">Di seguito vengono illustrate alcune procedure consigliate, scenari di uso generale e altre operazioni che è necessario conoscere quando si usano i tag in formato documentazione XML nel codice C#.</span><span class="sxs-lookup"><span data-stu-id="7bd9e-237">What follows are some best practices, general use case scenarios, and things that you should know when using XML documentation tags in your C# code.</span></span>

* <span data-ttu-id="7bd9e-238">Per mantenere una certa coerenza, tutti i tipi visibili pubblicamente e i loro membri devono essere documentati.</span><span class="sxs-lookup"><span data-stu-id="7bd9e-238">For the sake of consistency, all publicly visible types and their members should be documented.</span></span> <span data-ttu-id="7bd9e-239">Se necessario, è consigliabile eseguire un'operazione completa.</span><span class="sxs-lookup"><span data-stu-id="7bd9e-239">If you must do it, do it all.</span></span>
* <span data-ttu-id="7bd9e-240">I membri private possono anche essere documentati con commenti XML.</span><span class="sxs-lookup"><span data-stu-id="7bd9e-240">Private members can also be documented using XML comments.</span></span> <span data-ttu-id="7bd9e-241">Ciò espone tuttavia il funzionamento interno della libreria che potrebbe essere riservato.</span><span class="sxs-lookup"><span data-stu-id="7bd9e-241">However, this exposes the inner (potentially confidential) workings of your library.</span></span>
* <span data-ttu-id="7bd9e-242">Il minimo necessario è che i tipi e i loro membri abbiano i tag `<summary>` perché il loro contenuto è necessario per IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="7bd9e-242">At a bare minimum, types and their members should have a `<summary>` tag because its content is needed for IntelliSense.</span></span>
* <span data-ttu-id="7bd9e-243">Il testo della documentazione deve essere scritto usando frasi complete che terminano con un punto.</span><span class="sxs-lookup"><span data-stu-id="7bd9e-243">Documentation text should be written using complete sentences ending with full stops.</span></span>
* <span data-ttu-id="7bd9e-244">Le classi parziali sono completamente supportate e le informazioni sulla documentazione verranno concatenate in una singola voce per tale tipo.</span><span class="sxs-lookup"><span data-stu-id="7bd9e-244">Partial classes are fully supported, and documentation information will be concatenated into a single entry for that type.</span></span>
* <span data-ttu-id="7bd9e-245">Il compilatore verifica la sintassi dei tag `<exception>`, `<include>`, `<param>`, `<see>`, `<seealso>` e `<typeparam>`.</span><span class="sxs-lookup"><span data-stu-id="7bd9e-245">The compiler verifies the syntax of the `<exception>`, `<include>`, `<param>`, `<see>`, `<seealso>` and `<typeparam>` tags.</span></span>
- <span data-ttu-id="7bd9e-246">Il compilatore convalida i parametri che contengono i percorsi dei file e i riferimenti ad altre parti del codice.</span><span class="sxs-lookup"><span data-stu-id="7bd9e-246">The compiler validates the parameters that contain file paths and references to other parts of the code.</span></span>

## <a name="see-also"></a><span data-ttu-id="7bd9e-247">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7bd9e-247">See also</span></span>
[<span data-ttu-id="7bd9e-248">Commenti in formato documentazione XML (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="7bd9e-248">XML Documentation Comments (C# Programming Guide)</span></span>](programming-guide/xmldoc/xml-documentation-comments.md)

[<span data-ttu-id="7bd9e-249">Tag consigliati per i commenti della documentazione (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="7bd9e-249">Recommended Tags for Documentation Comments (C# Programming Guide)</span></span>](programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)

