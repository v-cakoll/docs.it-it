---
title: Main() e argomenti della riga di comando - Guida per programmatori C#
ms.date: 08/02/2017
f1_keywords:
- CS5001
- main_CSharpKeyword
- Main
helpviewer_keywords:
- Main method [C#]
- C# language, command-line arguments
- arguments [C#], command-line
- command line [C#], arguments
- command-line arguments [C#], Main method
ms.assetid: 73a17231-cf96-44ea-aa8a-54807c6fb1f4
ms.openlocfilehash: 190216b01ea416aedbca270a6d7a5acbf0c2e797
ms.sourcegitcommit: 5988e9a29cedb8757320817deda3c08c6f44a6aa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2020
ms.locfileid: "82200119"
---
# <a name="main-and-command-line-arguments-c-programming-guide"></a><span data-ttu-id="ea276-102">Main() e argomenti della riga di comando (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="ea276-102">Main() and command-line arguments (C# Programming Guide)</span></span>

<span data-ttu-id="ea276-103">Il metodo `Main` è il punto di ingresso di un'applicazione C#.</span><span class="sxs-lookup"><span data-stu-id="ea276-103">The `Main` method is the entry point of a C# application.</span></span> <span data-ttu-id="ea276-104">(Le librerie e i servizi non richiedono `Main` un metodo come punto di ingresso). Quando l'applicazione viene avviata, `Main` il metodo è il primo metodo richiamato.</span><span class="sxs-lookup"><span data-stu-id="ea276-104">(Libraries and services do not require a `Main` method as an entry point.) When the application is started, the `Main` method is the first method that is invoked.</span></span>

 <span data-ttu-id="ea276-105">In un programma C# può essere presente un solo punto di ingresso.</span><span class="sxs-lookup"><span data-stu-id="ea276-105">There can only be one entry point in a C# program.</span></span> <span data-ttu-id="ea276-106">Se sono presenti più classi con un metodo `Main`, è necessario compilare il programma con l'opzione del compilatore **/main** per specificare quale metodo `Main` deve essere usato come punto di ingresso.</span><span class="sxs-lookup"><span data-stu-id="ea276-106">If you have more than one class that has a `Main` method, you must compile your program with the **/main** compiler option to specify which `Main` method to use as the entry point.</span></span> <span data-ttu-id="ea276-107">Per ulteriori informazioni, vedere [-Main (opzioni del compilatore C#)](../../language-reference/compiler-options/main-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="ea276-107">For more information, see [-main (C# Compiler Options)](../../language-reference/compiler-options/main-compiler-option.md).</span></span>

[!code-csharp[csProgGuideMain#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class1.cs#17)]

## <a name="overview"></a><span data-ttu-id="ea276-108">Panoramica</span><span class="sxs-lookup"><span data-stu-id="ea276-108">Overview</span></span>

- <span data-ttu-id="ea276-109">Il metodo `Main` è il punto di ingresso di un programma eseguibile, ovvero il punto in cui il controllo del programma inizia e termina.</span><span class="sxs-lookup"><span data-stu-id="ea276-109">The `Main` method is the entry point of an executable program; it is where the program control starts and ends.</span></span>
- <span data-ttu-id="ea276-110">`Main` viene dichiarato in una classe o in un tipo struct.</span><span class="sxs-lookup"><span data-stu-id="ea276-110">`Main` is declared inside a class or struct.</span></span> <span data-ttu-id="ea276-111">`Main` deve essere [static](../../language-reference/keywords/static.md) e non [public](../../language-reference/keywords/public.md).</span><span class="sxs-lookup"><span data-stu-id="ea276-111">`Main` must be [static](../../language-reference/keywords/static.md) and it need not be [public](../../language-reference/keywords/public.md).</span></span> <span data-ttu-id="ea276-112">Nell'esempio precedente riceve l'accesso predefinito di [private](../../language-reference/keywords/private.md). La classe o lo struct contenitore non deve essere statico.</span><span class="sxs-lookup"><span data-stu-id="ea276-112">(In the earlier example, it receives the default access of [private](../../language-reference/keywords/private.md).) The enclosing class or struct is not required to be static.</span></span>
- <span data-ttu-id="ea276-113">Il tipo restituito da `Main` può essere `void`, `int` o, a partire da C# 7.1, `Task` o `Task<int>`.</span><span class="sxs-lookup"><span data-stu-id="ea276-113">`Main` can either have a `void`, `int`, or, starting with C# 7.1, `Task`, or `Task<int>` return type.</span></span>
- <span data-ttu-id="ea276-114">Se e solo se `Main` restituisce `Task` o `Task<int>`, la dichiarazione di `Main` può includere il [`async`](../../language-reference/keywords/async.md) modificatore.</span><span class="sxs-lookup"><span data-stu-id="ea276-114">If and only if `Main` returns a `Task` or `Task<int>`, the declaration of `Main` may include the [`async`](../../language-reference/keywords/async.md) modifier.</span></span> <span data-ttu-id="ea276-115">Si noti che questo esclude specificamente un metodo `async void Main`.</span><span class="sxs-lookup"><span data-stu-id="ea276-115">Note that this specifically excludes an `async void Main` method.</span></span>
- <span data-ttu-id="ea276-116">Il metodo `Main` può essere dichiarato con o senza un parametro `string[]` contenente argomenti della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="ea276-116">The `Main` method can be declared with or without a `string[]` parameter that contains command-line arguments.</span></span> <span data-ttu-id="ea276-117">Quando si usa Visual Studio per creare applicazioni Windows, è possibile aggiungere il parametro manualmente oppure usare il <xref:System.Environment.GetCommandLineArgs> metodo per ottenere gli [argomenti della riga di comando](command-line-arguments.md).</span><span class="sxs-lookup"><span data-stu-id="ea276-117">When using Visual Studio to create Windows applications, you can add the parameter manually or else use the <xref:System.Environment.GetCommandLineArgs> method to obtain the [command-line arguments](command-line-arguments.md).</span></span> <span data-ttu-id="ea276-118">I parametri vengono letti come argomenti della riga di comando a indice zero.</span><span class="sxs-lookup"><span data-stu-id="ea276-118">Parameters are read as zero-indexed command-line arguments.</span></span> <span data-ttu-id="ea276-119">Diversamente da C e C++, il nome del programma non viene trattato come primo argomento della riga di comando nella `args` matrice, ma è il primo elemento del <xref:System.Environment.GetCommandLineArgs> metodo.</span><span class="sxs-lookup"><span data-stu-id="ea276-119">Unlike C and C++, the name of the program is not treated as the first command-line argument in the `args` array, but it is the first element of the <xref:System.Environment.GetCommandLineArgs> method.</span></span>

<span data-ttu-id="ea276-120">Di seguito è riportato un elenco di `Main` firme valide:</span><span class="sxs-lookup"><span data-stu-id="ea276-120">The following is a list of valid `Main` signatures:</span></span>

```csharp
public static void Main() { }
public static int Main() { }
public static void Main(string[] args) { }
public static int Main(string[] args) { }
public static async Task Main() { }
public static async Task<int> Main() { }
public static async Task Main(string[] args) { }
public static async Task<int> Main(string[] args) { }
```

<span data-ttu-id="ea276-121">Negli esempi precedenti viene usato il modificatore della funzione di accesso public.</span><span class="sxs-lookup"><span data-stu-id="ea276-121">The preceding examples all use the public accessor modifier.</span></span> <span data-ttu-id="ea276-122">Tipico, ma non obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="ea276-122">That is typical, but not required.</span></span>

<span data-ttu-id="ea276-123">L'aggiunta dei tipi restituiti `async`, `Task` e `Task<int>` semplifica il codice del programma quando è necessario avviare le applicazioni console e per operazioni asincrone `await` in `Main`.</span><span class="sxs-lookup"><span data-stu-id="ea276-123">The addition of `async` and `Task`, `Task<int>` return types simplifies program code when console applications need to start and `await` asynchronous operations in `Main`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="ea276-124">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="ea276-124">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="ea276-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ea276-125">See also</span></span>

- [<span data-ttu-id="ea276-126">Compilazione dalla riga di comando con csc.exe</span><span class="sxs-lookup"><span data-stu-id="ea276-126">Command-line Building With csc.exe</span></span>](../../language-reference/compiler-options/command-line-building-with-csc-exe.md)
- [<span data-ttu-id="ea276-127">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="ea276-127">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="ea276-128">Metodi</span><span class="sxs-lookup"><span data-stu-id="ea276-128">Methods</span></span>](../classes-and-structs/methods.md)
- [<span data-ttu-id="ea276-129">All'interno di un programma C#</span><span class="sxs-lookup"><span data-stu-id="ea276-129">Inside a C# Program</span></span>](../inside-a-program/index.md)
