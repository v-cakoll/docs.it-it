---
title: Interpolazione di stringhe - C#
description: Informazioni sul funzionamento dell'interpolazione di stringhe in C# 6
keywords: .NET, .NET Core, C#, stringa
author: mgroves
ms.author: wiwagn
ms.date: 03/06/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: f8806f6b-3ac7-4ee6-9b3e-c524d5301ae9
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: de8f77e44319731f87f00d227a5373a78bf40e32
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---

# <a name="string-interpolation-in-c"></a><span data-ttu-id="6e2bc-104">Interpolazione di stringhe in C#</span><span class="sxs-lookup"><span data-stu-id="6e2bc-104">String Interpolation in C#</span></span> #

<span data-ttu-id="6e2bc-105">Il termine interpolazione di stringhe indica il modo in cui i segnaposto presenti in una stringa vengono sostituiti dal valore di una variabile di tipo stringa.</span><span class="sxs-lookup"><span data-stu-id="6e2bc-105">String Interpolation is the way that placeholders in a string are replaced by the value of a string variable.</span></span> <span data-ttu-id="6e2bc-106">Prima di C# 6, per eseguire questa operazione veniva usato `System.String.Format`.</span><span class="sxs-lookup"><span data-stu-id="6e2bc-106">Before C# 6, the way to do this is with `System.String.Format`.</span></span> <span data-ttu-id="6e2bc-107">Questa procedura funziona correttamente, ma, poiché usa segnaposto numerati, la scrittura delle istruzioni risulta più complessa e prolissa.</span><span class="sxs-lookup"><span data-stu-id="6e2bc-107">This works okay, but since it uses numbered placeholders, it can be harder to read and more verbose.</span></span>

<span data-ttu-id="6e2bc-108">L'interpolazione di stringhe è stata integrata in altri linguaggi di programmazione per un certo periodo di tempo.</span><span class="sxs-lookup"><span data-stu-id="6e2bc-108">Other programming languages have had string interpolation built into the language for a while.</span></span> <span data-ttu-id="6e2bc-109">Ad esempio, in PHP:</span><span class="sxs-lookup"><span data-stu-id="6e2bc-109">For instance, in PHP:</span></span>

```php
$name = "Jonas";
echo "My name is $name.";
// This will output "My name is Jonas."
```

<span data-ttu-id="6e2bc-110">In C# 6 è stato definito lo stile di interpolazione di stringhe seguente:</span><span class="sxs-lookup"><span data-stu-id="6e2bc-110">In C# 6, we finally have that style of string interpolation.</span></span> <span data-ttu-id="6e2bc-111">è possibile usare `$` prima di una stringa per indicare che le variabili e/o le espressioni devono essere sostituite dai i relativi valori.</span><span class="sxs-lookup"><span data-stu-id="6e2bc-111">You can use a `$` before a string to indicate that it should substitute variables/expressions for their values.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6e2bc-112">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="6e2bc-112">Prerequisites</span></span>
<span data-ttu-id="6e2bc-113">È necessario configurare il computer per l'esecuzione di .NET core.</span><span class="sxs-lookup"><span data-stu-id="6e2bc-113">You’ll need to set up your machine to run .NET core.</span></span> <span data-ttu-id="6e2bc-114">Le istruzioni di installazione sono disponibili nella pagina [.NET Core](https://www.microsoft.com/net/core).</span><span class="sxs-lookup"><span data-stu-id="6e2bc-114">You can find the installation instructions on the [.NET Core](https://www.microsoft.com/net/core) page.</span></span>
<span data-ttu-id="6e2bc-115">Questa applicazione può essere eseguita in Windows, Ubuntu Linux, macOS o in un contenitore Docker.</span><span class="sxs-lookup"><span data-stu-id="6e2bc-115">You can run this application on Windows, Ubuntu Linux, macOS or in a Docker container.</span></span> <span data-ttu-id="6e2bc-116">È necessario installare l'editor di codice preferito.</span><span class="sxs-lookup"><span data-stu-id="6e2bc-116">You’ll need to install your favorite code editor.</span></span> <span data-ttu-id="6e2bc-117">Nelle descrizioni seguenti viene usato [Visual Studio Code](https://code.visualstudio.com/), un editor open source multipiattaforma,</span><span class="sxs-lookup"><span data-stu-id="6e2bc-117">The descriptions below use [Visual Studio Code](https://code.visualstudio.com/) which is an open source, cross platform editor.</span></span> <span data-ttu-id="6e2bc-118">ma è possibile usare gli strumenti con cui si ha maggiore familiarità.</span><span class="sxs-lookup"><span data-stu-id="6e2bc-118">However, you can use whatever tools you are comfortable with.</span></span>

## <a name="create-the-application"></a><span data-ttu-id="6e2bc-119">Creare l'applicazione</span><span class="sxs-lookup"><span data-stu-id="6e2bc-119">Create the Application</span></span>

<span data-ttu-id="6e2bc-120">Dopo avere installato tutti gli strumenti, creare una nuova applicazione .NET Core.</span><span class="sxs-lookup"><span data-stu-id="6e2bc-120">Now that you've installed all the tools, create a new .NET Core application.</span></span> <span data-ttu-id="6e2bc-121">Per usare il generatore da riga di comando, creare una directory per il progetto, ad esempio `interpolated`, ed eseguire il comando seguente nella shell preferita:</span><span class="sxs-lookup"><span data-stu-id="6e2bc-121">To use the command line generator, create a directory for your project, such as `interpolated`, and execute the following command in your favorite shell:</span></span>

```
dotnet new console
```

<span data-ttu-id="6e2bc-122">Questo comando creerà un progetto .NET di base con un file di progetto, *interpolated.csproj*, e un file di codice sorgente, *Program.cs*.</span><span class="sxs-lookup"><span data-stu-id="6e2bc-122">This command will create a barebones .NET core project with a project file, *interpolated.csproj*, and a source code file, *Program.cs*.</span></span> <span data-ttu-id="6e2bc-123">Sarà necessario eseguire `dotnet restore` per ripristinare le dipendenze richieste per la compilazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="6e2bc-123">You will need to execute `dotnet restore` to restore the dependencies needed to compile this project.</span></span>

<span data-ttu-id="6e2bc-124">Per eseguire il programma, usare `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="6e2bc-124">To execute the program, use `dotnet run`.</span></span> <span data-ttu-id="6e2bc-125">Nella console viene visualizzato "Hello, World".</span><span class="sxs-lookup"><span data-stu-id="6e2bc-125">You should see "Hello, World" output to the console.</span></span>

## <a name="intro-to-string-interpolation"></a><span data-ttu-id="6e2bc-126">Introduzione all'interpolazione di stringhe</span><span class="sxs-lookup"><span data-stu-id="6e2bc-126">Intro to String Interpolation</span></span>

<span data-ttu-id="6e2bc-127">Con `System.String.Format` vengono specificati i "segnaposto" presenti in una stringa che devono essere sostituiti dai parametri che seguono la stringa stessa.</span><span class="sxs-lookup"><span data-stu-id="6e2bc-127">With `System.String.Format`, you specify "placeholders" in a string that are replaced by the parameters following the string.</span></span> <span data-ttu-id="6e2bc-128">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="6e2bc-128">For instance:</span></span>

<span data-ttu-id="6e2bc-129">[!code-csharp[Esempio di String.Format](../../../samples/snippets/csharp/new-in-6/string-interpolation.cs#StringFormatExample)]</span><span class="sxs-lookup"><span data-stu-id="6e2bc-129">[!code-csharp[String.Format example](../../../samples/snippets/csharp/new-in-6/string-interpolation.cs#StringFormatExample)]</span></span>  

<span data-ttu-id="6e2bc-130">Verrà visualizzato l'output "My name is Matt Groves".</span><span class="sxs-lookup"><span data-stu-id="6e2bc-130">That will output "My name is Matt Groves".</span></span>

<span data-ttu-id="6e2bc-131">In C# 6, anziché usare `String.Format`, si definisce una stringa interpolata facendola precedere dal simbolo `$` e quindi usando le variabili direttamente nella stringa.</span><span class="sxs-lookup"><span data-stu-id="6e2bc-131">In C# 6, instead of using `String.Format`, you define an interpolated string by prepending it with the `$` symbol, and then using the variables directly in the string.</span></span> <span data-ttu-id="6e2bc-132">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="6e2bc-132">For instance:</span></span>

<span data-ttu-id="6e2bc-133">[!code-csharp[Esempio di interpolazione](../../../samples/snippets/csharp/new-in-6/string-interpolation.cs#InterpolationExample)]</span><span class="sxs-lookup"><span data-stu-id="6e2bc-133">[!code-csharp[Interpolation example](../../../samples/snippets/csharp/new-in-6/string-interpolation.cs#InterpolationExample)]</span></span>  

<span data-ttu-id="6e2bc-134">Non è necessario usare solo le variabili.</span><span class="sxs-lookup"><span data-stu-id="6e2bc-134">You don't have to use just variables.</span></span> <span data-ttu-id="6e2bc-135">È possibile usare qualsiasi espressione inclusa tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="6e2bc-135">You can use any expression within the brackets.</span></span> <span data-ttu-id="6e2bc-136">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="6e2bc-136">For instance:</span></span>

<span data-ttu-id="6e2bc-137">[!code-csharp[Esempio di espressione di interpolazione](../../../samples/snippets/csharp/new-in-6/string-interpolation.cs#InterpolationExpressionExample)]</span><span class="sxs-lookup"><span data-stu-id="6e2bc-137">[!code-csharp[Interpolation expression example](../../../samples/snippets/csharp/new-in-6/string-interpolation.cs#InterpolationExpressionExample)]</span></span>  

<span data-ttu-id="6e2bc-138">L'output sarà il seguente:</span><span class="sxs-lookup"><span data-stu-id="6e2bc-138">Which would output:</span></span>

```
This is line number 1
This is line number 2
This is line number 3
This is line number 4
This is line number 5
```

## <a name="how-string-interpolation-works"></a><span data-ttu-id="6e2bc-139">Funzionamento dell'interpolazione di stringhe</span><span class="sxs-lookup"><span data-stu-id="6e2bc-139">How string interpolation works</span></span>

<span data-ttu-id="6e2bc-140">Nel background, la sintassi dell'interpolazione di stringhe viene convertita in String.Format dal compilatore.</span><span class="sxs-lookup"><span data-stu-id="6e2bc-140">Behind the scenes, this string interpolation syntax is translated into String.Format by the compiler.</span></span> <span data-ttu-id="6e2bc-141">Di conseguenza, è possibile eseguire lo [stesso tipo di operazioni eseguite prima con String.Format](https://msdn.microsoft.com/en-us/library/dwhawy9k(v=vs.110).aspx).</span><span class="sxs-lookup"><span data-stu-id="6e2bc-141">So, you can do the [same type of stuff you've done before with String.Format](https://msdn.microsoft.com/en-us/library/dwhawy9k(v=vs.110).aspx).</span></span>

<span data-ttu-id="6e2bc-142">Ad esempio, è possibile aggiungere spaziatura interna e formattazione numerica:</span><span class="sxs-lookup"><span data-stu-id="6e2bc-142">For instance, you can add padding and numeric formatting:</span></span>

<span data-ttu-id="6e2bc-143">[!code-csharp[Esempio di formattazione di interpolazione](../../../samples/snippets/csharp/new-in-6/string-interpolation.cs#InterpolationFormattingExample)]</span><span class="sxs-lookup"><span data-stu-id="6e2bc-143">[!code-csharp[Interpolation formatting example](../../../samples/snippets/csharp/new-in-6/string-interpolation.cs#InterpolationFormattingExample)]</span></span>  

<span data-ttu-id="6e2bc-144">L'output del codice sopra riportato sarà simile a quanto segue:</span><span class="sxs-lookup"><span data-stu-id="6e2bc-144">The above would output something like:</span></span>

```
998        5,177.67
999        6,719.30
1000       9,910.61
1001       529.34
1002       1,349.86
1003       2,660.82
1004       6,227.77
```

<span data-ttu-id="6e2bc-145">Se un nome di variabile non viene trovato, verrà generato un errore in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="6e2bc-145">If a variable name is not found, then a compile time error will be generated.</span></span>

<span data-ttu-id="6e2bc-146">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="6e2bc-146">For instance:</span></span>

```csharp
var animal = "fox";
var localizeMe = $"The {adj} brown {animal} jumped over the lazy {otheranimal}";
var adj = "quick";
Console.WriteLine(localizeMe);
```

<span data-ttu-id="6e2bc-147">Se si compila il codice sopra riportato, verranno generati degli errori:</span><span class="sxs-lookup"><span data-stu-id="6e2bc-147">If you compile this, you'll get errors:</span></span>
 
* <span data-ttu-id="6e2bc-148">`Cannot use local variable 'adj' before it is declared`: la variabile `adj` non è stata dichiarata *prima* della stringa interpolata.</span><span class="sxs-lookup"><span data-stu-id="6e2bc-148">`Cannot use local variable 'adj' before it is declared` - the `adj` variable wasn't declared until *after* the interpolated string.</span></span>
* <span data-ttu-id="6e2bc-149">`The name 'otheranimal' does not exist in the current context`: la variabile denominata `otheranimal` non è mai stata dichiarata.</span><span class="sxs-lookup"><span data-stu-id="6e2bc-149">`The name 'otheranimal' does not exist in the current context` - a variable called `otheranimal` was never even declared</span></span>

## <a name="localization-and-internationalization"></a><span data-ttu-id="6e2bc-150">Localizzazione e internazionalizzazione</span><span class="sxs-lookup"><span data-stu-id="6e2bc-150">Localization and Internationalization</span></span>

<span data-ttu-id="6e2bc-151">Una stringa interpolata supporta `IFormattable` e `FormattableString`, caratteristica utile per l'internazionalizzazione.</span><span class="sxs-lookup"><span data-stu-id="6e2bc-151">An interpolated string supports `IFormattable` and `FormattableString`, which can be useful for internationalization.</span></span>

<span data-ttu-id="6e2bc-152">Per impostazione predefinita, una stringa interpolata usa le impostazioni cultura correnti.</span><span class="sxs-lookup"><span data-stu-id="6e2bc-152">By default, an interpolated string uses the current culture.</span></span> <span data-ttu-id="6e2bc-153">Per usare impostazioni cultura differenti, è possibile eseguire il cast della stringa come `IFormattable`.</span><span class="sxs-lookup"><span data-stu-id="6e2bc-153">To use a different culture, you could cast it as `IFormattable`</span></span>

<span data-ttu-id="6e2bc-154">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="6e2bc-154">For instance:</span></span>

<span data-ttu-id="6e2bc-155">[!code-csharp[Esempio di internazionalizzazione dell'interpolazione](../../../samples/snippets/csharp/new-in-6/string-interpolation.cs#InterpolationInternationalizationExample)]</span><span class="sxs-lookup"><span data-stu-id="6e2bc-155">[!code-csharp[Interpolation internationalization example](../../../samples/snippets/csharp/new-in-6/string-interpolation.cs#InterpolationInternationalizationExample)]</span></span>  

## <a name="conclusion"></a><span data-ttu-id="6e2bc-156">Conclusione</span><span class="sxs-lookup"><span data-stu-id="6e2bc-156">Conclusion</span></span> 

<span data-ttu-id="6e2bc-157">In questa esercitazione è stato illustrato come usare le funzionalità di interpolazione di stringhe di C# 6.</span><span class="sxs-lookup"><span data-stu-id="6e2bc-157">In this tutorial, you learned how to use string interpolation features of C# 6.</span></span> <span data-ttu-id="6e2bc-158">Si tratta fondamentalmente di un modo sintetico di scrivere semplici istruzioni `String.Format`, con alcune raccomandazioni per gli usi più avanzati.</span><span class="sxs-lookup"><span data-stu-id="6e2bc-158">It's basically a more concise way of writing simple `String.Format` statements, with some caveats for more advanced uses of it.</span></span>

