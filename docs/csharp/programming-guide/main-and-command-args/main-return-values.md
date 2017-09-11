---
title: Valori restituiti da Main() (Guida per programmatori C#)
ms.date: 2017-08-02
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- Main method [C#], return values
ms.assetid: c2f5a1d8-1676-4bea-bc7e-44a97e72d5bc
caps.latest.revision: 20
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
ms.sourcegitcommit: d019d1c5757a961c03439d756e808ae13fd8a67b
ms.openlocfilehash: 50943bdd0b7726145797faf82719537a388dad89
ms.contentlocale: it-it
ms.lasthandoff: 08/03/2017

---

# <a name="main-return-values-c-programming-guide"></a><span data-ttu-id="7ab7e-102">Valori restituiti da Main() (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="7ab7e-102">Main() return values (C# Programming Guide)</span></span>

<span data-ttu-id="7ab7e-103">Il metodo `Main` può restituire `void`:</span><span class="sxs-lookup"><span data-stu-id="7ab7e-103">The `Main` method can return `void`:</span></span>

<span data-ttu-id="7ab7e-104">[!code-cs[csProgGuideMain#12](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/main-return-values_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="7ab7e-104">[!code-cs[csProgGuideMain#12](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/main-return-values_1.cs)]</span></span>

<span data-ttu-id="7ab7e-105">Può anche restituire `int`:</span><span class="sxs-lookup"><span data-stu-id="7ab7e-105">It can also return an `int`:</span></span>

<span data-ttu-id="7ab7e-106">[!code-cs[csProgGuideMain#13](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/main-return-values_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="7ab7e-106">[!code-cs[csProgGuideMain#13](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/main-return-values_2.cs)]</span></span>

<span data-ttu-id="7ab7e-107">Se il valore restituito da `Main` non viene usato, la restituzione di `void` consente di semplificare leggermente il codice.</span><span class="sxs-lookup"><span data-stu-id="7ab7e-107">If the return value from `Main` is not used, returning `void` allows for slightly simpler code.</span></span> <span data-ttu-id="7ab7e-108">Tuttavia, la restituzione di un valore intero consente al programma di comunicare le informazioni sullo stato ad altri programmi o script che richiamano il file eseguibile.</span><span class="sxs-lookup"><span data-stu-id="7ab7e-108">However, returning an integer enables the program to communicate status information to other programs or scripts that invoke the executable file.</span></span> <span data-ttu-id="7ab7e-109">Il valore restituito da `Main` viene considerato come codice di uscita per il processo.</span><span class="sxs-lookup"><span data-stu-id="7ab7e-109">The return value from `Main` is treated as the exit code for the process.</span></span> <span data-ttu-id="7ab7e-110">L'esempio seguente illustra come è possibile accedere al valore restituito da `Main`.</span><span class="sxs-lookup"><span data-stu-id="7ab7e-110">The following example shows how the return value from `Main` can be accessed.</span></span>

## <a name="example"></a><span data-ttu-id="7ab7e-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="7ab7e-111">Example</span></span>

<span data-ttu-id="7ab7e-112">Questo esempio usa gli strumenti della riga di comando [.NET Core](../../../core/index.md).</span><span class="sxs-lookup"><span data-stu-id="7ab7e-112">This example uses [.NET Core](../../../core/index.md) command line tools.</span></span> <span data-ttu-id="7ab7e-113">Per acquisire familiarità con gli strumenti della riga di comando .NET Core, vedere questa [introduzione](../../../core/tutorials/using-with-xplat-cli.md).</span><span class="sxs-lookup"><span data-stu-id="7ab7e-113">If you are unfamilar with .NET Core command line tools, you can learn about them in this [Get started topic](../../../core/tutorials/using-with-xplat-cli.md).</span></span>

<span data-ttu-id="7ab7e-114">Convertire il metodo `Main` in *program.cs* come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="7ab7e-114">Modify the `Main` method in *program.cs* as follows:</span></span>

<span data-ttu-id="7ab7e-115">[!code-cs[csProgGuideMain#14](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/main-return-values_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="7ab7e-115">[!code-cs[csProgGuideMain#14](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/main-return-values_3.cs)]</span></span>

<span data-ttu-id="7ab7e-116">Quando si esegue un programma in ambiente Windows, qualsiasi valore restituito dalla funzione `Main` viene archiviato in una variabile di ambiente.</span><span class="sxs-lookup"><span data-stu-id="7ab7e-116">When a program is executed in Windows, any value returned from the `Main` function is stored in an environment variable.</span></span> <span data-ttu-id="7ab7e-117">Questa variabile di ambiente può essere recuperata mediante `ERRORLEVEL` da un file batch o mediante `$LastExitCode` da PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7ab7e-117">This environment variable can be retrieved using `ERRORLEVEL` from a batch file, or `$LastExitCode` from powershell.</span></span>

<span data-ttu-id="7ab7e-118">È possibile compilare l'applicazione usando il comando [dotnet CLI](../../../core/tools/dotnet.md) `dotnet build`.</span><span class="sxs-lookup"><span data-stu-id="7ab7e-118">You can build the application using the [dotnet CLI](../../../core/tools/dotnet.md) `dotnet build` command.</span></span>

<span data-ttu-id="7ab7e-119">Quindi creare uno script di PowerShell per eseguire l'applicazione e visualizzare il risultato.</span><span class="sxs-lookup"><span data-stu-id="7ab7e-119">Next, create a Powershell script to run the application and display the result.</span></span> <span data-ttu-id="7ab7e-120">Incollare il codice seguente in un file di testo e salvarlo come `test.ps1` nella cartella che contiene il progetto.</span><span class="sxs-lookup"><span data-stu-id="7ab7e-120">Paste the following code into a text file and save it as `test.ps1` in the folder that contains the project.</span></span> <span data-ttu-id="7ab7e-121">Eseguire lo script di PowerShell digitando `test.ps1` al prompt di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7ab7e-121">Run the powershell script by typing `test.ps1` at the powershell prompt.</span></span>

<span data-ttu-id="7ab7e-122">Poiché il codice restituisce zero, il file batch indicherà un esito positivo.</span><span class="sxs-lookup"><span data-stu-id="7ab7e-122">Because the code returns zero, the batch file will report success.</span></span> <span data-ttu-id="7ab7e-123">Se tuttavia si modifica MainReturnValTest.cs in modo che restituisca un valore diverso da zero e quindi si ricompila il programma, l'esecuzione successiva dello script di PowerShell segnala un errore.</span><span class="sxs-lookup"><span data-stu-id="7ab7e-123">However, if you change MainReturnValTest.cs to return a non-zero value and then re-compile the program, subsequent execution of the powershell script will report failure.</span></span>

```powershell
dotnet run
if ($LastExitCode -eq 0) {
    Write-Host "Execution succeeded"
} else
{
    Write-Host "Execution Failed"
}
Write-Host "Return value = " $LastExitCode
```

## <a name="sample-output"></a><span data-ttu-id="7ab7e-124">Esempio di output</span><span class="sxs-lookup"><span data-stu-id="7ab7e-124">Sample output</span></span>

```txt
Execution succeeded
Return value = 0
```

## <a name="async-main-return-values"></a><span data-ttu-id="7ab7e-125">Valori restituiti da Async Main</span><span class="sxs-lookup"><span data-stu-id="7ab7e-125">Async Main return values</span></span>

<span data-ttu-id="7ab7e-126">I valori restituiti da Async Main trasferiscono il codice boilerplate necessario per la chiamata di metodi asincroni in `Main` a codice generato dal compilatore.</span><span class="sxs-lookup"><span data-stu-id="7ab7e-126">Async Main return values move the boilerplate code necessary for calling asynchronous methods in `Main` to code generated by the compiler.</span></span> <span data-ttu-id="7ab7e-127">In precedenza era necessario scrivere questo costrutto per chiamare codice asincrono e verificare che il programma rimanesse in esecuzione fino al completamento dell'operazione asincrona:</span><span class="sxs-lookup"><span data-stu-id="7ab7e-127">Previously, you would need to write this construct to call asynchronous code and ensure your program ran until the asynchronous operation completed:</span></span>

```csharp
public static void Main()
{
    AsyncConsoleWork().GetAwaiter().GetResult();
}

private static async Task<int> AsyncConsoleWork()
{
    // Main body here
    return 0;
}
```

<span data-ttu-id="7ab7e-128">Ora è possibile usare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="7ab7e-128">Now, this can be replaced by:</span></span>

<span data-ttu-id="7ab7e-129">[!code-csharp[AsyncMain](../../../../samples/snippets/csharp/main-arguments/program.cs#AsyncMain)]</span><span class="sxs-lookup"><span data-stu-id="7ab7e-129">[!code-csharp[AsyncMain](../../../../samples/snippets/csharp/main-arguments/program.cs#AsyncMain)]</span></span>

<span data-ttu-id="7ab7e-130">Il vantaggio della nuova sintassi è che il compilatore genera sempre il codice corretto.</span><span class="sxs-lookup"><span data-stu-id="7ab7e-130">The advantage of the new syntax is that the compiler always generates the correct code.</span></span>

## <a name="compiler-generated-code"></a><span data-ttu-id="7ab7e-131">Codice generato dal compilatore</span><span class="sxs-lookup"><span data-stu-id="7ab7e-131">Compiler generated code</span></span>

<span data-ttu-id="7ab7e-132">Quando il punto di ingresso dell'applicazione restituisce `Task` o `Task<int>` il compilatore genera un nuovo punto di ingresso che chiama il metodo del punto di ingresso dichiarato nel codice dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="7ab7e-132">When the application entry point returns a `Task` or `Task<int>`, the compiler generates a new entry point that calls the entry point method declared in the application code.</span></span> <span data-ttu-id="7ab7e-133">Supponendo che questo punto di ingresso sia denominato `$GeneratedMain`, il compilatore genera il codice seguente per questi punti di ingresso:</span><span class="sxs-lookup"><span data-stu-id="7ab7e-133">Assuming that this entry point is called `$GeneratedMain`, the compiler generates the following code for these entry points:</span></span>

- <span data-ttu-id="7ab7e-134">`static Task Main()`: il compilatore produce l'equivalente di `private static void $GeneratedMain() => Main().GetAwaiter().GetResult();`</span><span class="sxs-lookup"><span data-stu-id="7ab7e-134">`static Task Main()` results in the compiler emitting the equivalent of `private static void $GeneratedMain() => Main().GetAwaiter().GetResult();`</span></span>
- <span data-ttu-id="7ab7e-135">`static Task Main(string[])`: il compilatore produce l'equivalente di `private static void $GeneratedMain(string[] args) => Main(args).GetAwaiter().GetResult();`</span><span class="sxs-lookup"><span data-stu-id="7ab7e-135">`static Task Main(string[])` results in the compiler emitting the equivalent of `private static void $GeneratedMain(string[] args) => Main(args).GetAwaiter().GetResult();`</span></span>
- <span data-ttu-id="7ab7e-136">`static Task<int> Main()`: il compilatore produce l'equivalente di `private static int $GeneratedMain() => Main().GetAwaiter().GetResult();`</span><span class="sxs-lookup"><span data-stu-id="7ab7e-136">`static Task<int> Main()` results in the compiler emitting the equivalent of `private static int $GeneratedMain() => Main().GetAwaiter().GetResult();`</span></span>
- <span data-ttu-id="7ab7e-137">`static Task<int> Main(string[])`: il compilatore produce l'equivalente di `private static int $GeneratedMain(string[] args) => Main(args).GetAwaiter().GetResult();`</span><span class="sxs-lookup"><span data-stu-id="7ab7e-137">`static Task<int> Main(string[])` results in the compiler emitting the equivalent of `private static int $GeneratedMain(string[] args) => Main(args).GetAwaiter().GetResult();`</span></span>

> [!NOTE]
><span data-ttu-id="7ab7e-138">Se negli esempi si fosse usato il modificatore `async` sul metodo `Main` il compilatore avrebbe generato lo stesso codice.</span><span class="sxs-lookup"><span data-stu-id="7ab7e-138">If the examples used `async` modifier on the `Main` method, the compiler would generate the same code.</span></span>

## <a name="see-also"></a><span data-ttu-id="7ab7e-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7ab7e-139">See also</span></span>
<span data-ttu-id="7ab7e-140">[Guida per programmatori C#](../../programming-guide/index.md)
[Riferimenti per C#](../index.md)
[Main() e argomenti della riga di comando](index.md)
[Procedura: Visualizzare gli argomenti della riga di comando](../../programming-guide/main-and-command-args/how-to-display-command-line-arguments.md)
[Procedura: Accedere agli argomenti della riga di comando usando foreach](../../programming-guide/main-and-command-args/how-to-access-command-line-arguments-using-foreach.md)</span><span class="sxs-lookup"><span data-stu-id="7ab7e-140">[C# Programming Guide](../../programming-guide/index.md)
[C# Reference](../index.md)
[Main() and Command-Line Arguments](index.md)
[How to: Display Command Line Arguments](../../programming-guide/main-and-command-args/how-to-display-command-line-arguments.md)
[How to: Access Command-Line Arguments Using foreach](../../programming-guide/main-and-command-args/how-to-access-command-line-arguments-using-foreach.md)</span></span>

