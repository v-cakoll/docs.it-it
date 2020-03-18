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
ms.openlocfilehash: 0571ec6dbc42f103ec922a6b2b13a52510640a78
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "75700601"
---
# <a name="main-and-command-line-arguments-c-programming-guide"></a><span data-ttu-id="afc9d-102">Main() e argomenti della riga di comando (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="afc9d-102">Main() and command-line arguments (C# Programming Guide)</span></span>

<span data-ttu-id="afc9d-103">Il metodo `Main` è il punto di ingresso di un'applicazione C#.</span><span class="sxs-lookup"><span data-stu-id="afc9d-103">The `Main` method is the entry point of a C# application.</span></span> <span data-ttu-id="afc9d-104">Le librerie e i `Main` servizi non richiedono un metodo come punto di ingresso. Quando l'applicazione viene `Main` avviata, il metodo è il primo metodo che viene richiamato.</span><span class="sxs-lookup"><span data-stu-id="afc9d-104">(Libraries and services do not require a `Main` method as an entry point.) When the application is started, the `Main` method is the first method that is invoked.</span></span>

 <span data-ttu-id="afc9d-105">In un programma C# può essere presente un solo punto di ingresso.</span><span class="sxs-lookup"><span data-stu-id="afc9d-105">There can only be one entry point in a C# program.</span></span> <span data-ttu-id="afc9d-106">Se sono presenti più classi con un metodo `Main`, è necessario compilare il programma con l'opzione del compilatore **/main** per specificare quale metodo `Main` deve essere usato come punto di ingresso.</span><span class="sxs-lookup"><span data-stu-id="afc9d-106">If you have more than one class that has a `Main` method, you must compile your program with the **/main** compiler option to specify which `Main` method to use as the entry point.</span></span> <span data-ttu-id="afc9d-107">Per altre informazioni, vedere [-main (opzioni del compilatore C)](../../language-reference/compiler-options/main-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="afc9d-107">For more information, see [-main (C# Compiler Options)](../../language-reference/compiler-options/main-compiler-option.md).</span></span>

[!code-csharp[csProgGuideMain#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class1.cs#17)]

## <a name="overview"></a><span data-ttu-id="afc9d-108">Panoramica</span><span class="sxs-lookup"><span data-stu-id="afc9d-108">Overview</span></span>

- <span data-ttu-id="afc9d-109">Il metodo `Main` è il punto di ingresso di un programma eseguibile, ovvero il punto in cui il controllo del programma inizia e termina.</span><span class="sxs-lookup"><span data-stu-id="afc9d-109">The `Main` method is the entry point of an executable program; it is where the program control starts and ends.</span></span>
- <span data-ttu-id="afc9d-110">`Main` viene dichiarato in una classe o in un tipo struct.</span><span class="sxs-lookup"><span data-stu-id="afc9d-110">`Main` is declared inside a class or struct.</span></span> <span data-ttu-id="afc9d-111">`Main` deve essere [static](../../language-reference/keywords/static.md) e non [public](../../language-reference/keywords/public.md).</span><span class="sxs-lookup"><span data-stu-id="afc9d-111">`Main` must be [static](../../language-reference/keywords/static.md) and it need not be [public](../../language-reference/keywords/public.md).</span></span> <span data-ttu-id="afc9d-112">Nell'esempio precedente, riceve l'accesso predefinito di [private](../../language-reference/keywords/private.md).) Non è necessario che la classe o lo struct che lo contiene sia statico.</span><span class="sxs-lookup"><span data-stu-id="afc9d-112">(In the earlier example, it receives the default access of [private](../../language-reference/keywords/private.md).) The enclosing class or struct is not required to be static.</span></span>
- <span data-ttu-id="afc9d-113">Il tipo restituito da `Main` può essere `void`, `int` o, a partire da C# 7.1, `Task` o `Task<int>`.</span><span class="sxs-lookup"><span data-stu-id="afc9d-113">`Main` can either have a `void`, `int`, or, starting with C# 7.1, `Task`, or `Task<int>` return type.</span></span>
- <span data-ttu-id="afc9d-114">Se e `Main` solo `Task` se `Task<int>`restituisce `Main` o , [`async`](../../language-reference/keywords/async.md) la dichiarazione di può includere il modificatore .</span><span class="sxs-lookup"><span data-stu-id="afc9d-114">If and only if `Main` returns a `Task` or `Task<int>`, the declaration of `Main` may include the [`async`](../../language-reference/keywords/async.md) modifier.</span></span> <span data-ttu-id="afc9d-115">Si noti che questo esclude specificamente un metodo `async void Main`.</span><span class="sxs-lookup"><span data-stu-id="afc9d-115">Note that this specifically excludes an `async void Main` method.</span></span>
- <span data-ttu-id="afc9d-116">Il metodo `Main` può essere dichiarato con o senza un parametro `string[]` contenente argomenti della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="afc9d-116">The `Main` method can be declared with or without a `string[]` parameter that contains command-line arguments.</span></span> <span data-ttu-id="afc9d-117">Quando si utilizza Visual Studio per creare applicazioni Windows, <xref:System.Environment.GetCommandLineArgs> è possibile aggiungere il parametro manualmente oppure utilizzare il metodo per ottenere gli argomenti della riga di [comando.](command-line-arguments.md)</span><span class="sxs-lookup"><span data-stu-id="afc9d-117">When using Visual Studio to create Windows applications, you can add the parameter manually or else use the <xref:System.Environment.GetCommandLineArgs> method to obtain the [command-line arguments](command-line-arguments.md).</span></span> <span data-ttu-id="afc9d-118">I parametri vengono letti come argomenti della riga di comando a indice zero.</span><span class="sxs-lookup"><span data-stu-id="afc9d-118">Parameters are read as zero-indexed command-line arguments.</span></span> <span data-ttu-id="afc9d-119">A differenza di C e C, il nome del programma non viene `args` considerato come il primo argomento <xref:System.Environment.GetCommandLineArgs> della riga di comando nella matrice, ma è il primo elemento del metodo.</span><span class="sxs-lookup"><span data-stu-id="afc9d-119">Unlike C and C++, the name of the program is not treated as the first command-line argument in the `args` array, but it is the first element of the <xref:System.Environment.GetCommandLineArgs> method.</span></span>

<span data-ttu-id="afc9d-120">Di seguito è riportato un elenco di firme valide: `Main`</span><span class="sxs-lookup"><span data-stu-id="afc9d-120">The following is a list of valid `Main` signatures:</span></span>

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

<span data-ttu-id="afc9d-121">L'aggiunta dei tipi restituiti `async`, `Task` e `Task<int>` semplifica il codice del programma quando è necessario avviare le applicazioni console e per operazioni asincrone `await` in `Main`.</span><span class="sxs-lookup"><span data-stu-id="afc9d-121">The addition of `async` and `Task`, `Task<int>` return types simplifies program code when console applications need to start and `await` asynchronous operations in `Main`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="afc9d-122">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="afc9d-122">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="afc9d-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="afc9d-123">See also</span></span>

- [<span data-ttu-id="afc9d-124">Compilazione dalla riga di comando con csc.exe</span><span class="sxs-lookup"><span data-stu-id="afc9d-124">Command-line Building With csc.exe</span></span>](../../language-reference/compiler-options/command-line-building-with-csc-exe.md)
- [<span data-ttu-id="afc9d-125">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="afc9d-125">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="afc9d-126">Metodi</span><span class="sxs-lookup"><span data-stu-id="afc9d-126">Methods</span></span>](../classes-and-structs/methods.md)
- [<span data-ttu-id="afc9d-127">Contenuto di un programma C#</span><span class="sxs-lookup"><span data-stu-id="afc9d-127">Inside a C# Program</span></span>](../inside-a-program/index.md)
