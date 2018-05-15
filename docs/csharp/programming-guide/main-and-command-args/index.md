---
title: Main() e argomenti della riga di comando (Guida per programmatori C#)
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
ms.openlocfilehash: 03d6e7185a0a16589fb612724be52ce51e813173
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="main-and-command-line-arguments-c-programming-guide"></a><span data-ttu-id="b6005-102">Main() e argomenti della riga di comando (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="b6005-102">Main() and command-line arguments (C# Programming Guide)</span></span>

<span data-ttu-id="b6005-103">Il metodo `Main` è il punto di ingresso di un'applicazione C#.</span><span class="sxs-lookup"><span data-stu-id="b6005-103">The `Main` method is the entry point of a C# application.</span></span> <span data-ttu-id="b6005-104">Le librerie e i servizi non richiedono un metodo `Main` come punto di ingresso. All'avvio dell'applicazione, `Main` è il primo metodo richiamato.</span><span class="sxs-lookup"><span data-stu-id="b6005-104">(Libraries and services do not require a `Main` method as an entry point.) When the application is started, the `Main` method is the first method that is invoked.</span></span>

 <span data-ttu-id="b6005-105">In un programma C# può essere presente un solo punto di ingresso.</span><span class="sxs-lookup"><span data-stu-id="b6005-105">There can only be one entry point in a C# program.</span></span> <span data-ttu-id="b6005-106">Se sono presenti più classi con un metodo `Main`, è necessario compilare il programma con l'opzione del compilatore **/main** per specificare quale metodo `Main` deve essere usato come punto di ingresso.</span><span class="sxs-lookup"><span data-stu-id="b6005-106">If you have more than one class that has a `Main` method, you must compile your program with the **/main** compiler option to specify which `Main` method to use as the entry point.</span></span> <span data-ttu-id="b6005-107">Per altre informazioni, vedere [/main (Opzioni del compilatore C#)](../../../csharp/language-reference/compiler-options/main-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="b6005-107">For more information, see [/main (C# Compiler Options)](../../../csharp/language-reference/compiler-options/main-compiler-option.md).</span></span>

 [!code-csharp[csProgGuideMain#17](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/main-and-command-line-arguments_1.cs)]

## <a name="overview"></a><span data-ttu-id="b6005-108">Panoramica</span><span class="sxs-lookup"><span data-stu-id="b6005-108">Overview</span></span>

- <span data-ttu-id="b6005-109">Il metodo `Main` è il punto di ingresso di un programma eseguibile, ovvero il punto in cui il controllo del programma inizia e termina.</span><span class="sxs-lookup"><span data-stu-id="b6005-109">The `Main` method is the entry point of an executable program; it is where the program control starts and ends.</span></span>
- <span data-ttu-id="b6005-110">`Main` viene dichiarato in una classe o in un tipo struct.</span><span class="sxs-lookup"><span data-stu-id="b6005-110">`Main` is declared inside a class or struct.</span></span> <span data-ttu-id="b6005-111">`Main` deve essere [static](../../../csharp/language-reference/keywords/static.md) e non [public](../../../csharp/language-reference/keywords/public.md).</span><span class="sxs-lookup"><span data-stu-id="b6005-111">`Main` must be [static](../../../csharp/language-reference/keywords/static.md) and it need not be [public](../../../csharp/language-reference/keywords/public.md).</span></span> <span data-ttu-id="b6005-112">Nell'esempio precedente riceve l'accesso predefinito di [private](../../../csharp/language-reference/keywords/private.md). Non è necessario che la classe o il tipo struct che lo contiene sia statico.</span><span class="sxs-lookup"><span data-stu-id="b6005-112">(In the earlier example, it receives the default access of [private](../../../csharp/language-reference/keywords/private.md).) The enclosing class or struct is not required to be static.</span></span>
- <span data-ttu-id="b6005-113">Il tipo restituito da `Main` può essere `void`, `int` o, a partire da C# 7.1, `Task` o `Task<int>`.</span><span class="sxs-lookup"><span data-stu-id="b6005-113">`Main` can either have a `void`, `int`, or, starting with C# 7.1, `Task`, or `Task<int>` return type.</span></span>
- <span data-ttu-id="b6005-114">Se e solo se `Main` restituisce `Task` o `Task<int>`, la dichiarazione di `Main` può includere il modificatore [`async`](../../language-reference/keywords/async.md).</span><span class="sxs-lookup"><span data-stu-id="b6005-114">If and only if `Main` returns a `Task` or `Task<int>`, the declaration of `Main` may include the [`async`](../../language-reference/keywords/async.md) modifier.</span></span> <span data-ttu-id="b6005-115">Si noti che questo esclude specificamente un metodo `async void Main`.</span><span class="sxs-lookup"><span data-stu-id="b6005-115">Note that this specifically excludes an `async void Main` method.</span></span>
- <span data-ttu-id="b6005-116">Il metodo `Main` può essere dichiarato con o senza un parametro `string[]` contenente argomenti della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="b6005-116">The `Main` method can be declared with or without a `string[]` parameter that contains command-line arguments.</span></span> <span data-ttu-id="b6005-117">Quando si usa Visual Studio per creare applicazioni Windows, è possibile aggiungere il parametro manualmente o usare la classe <xref:System.Environment> per ottenere gli argomenti della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="b6005-117">When using Visual Studio to create Windows applications, you can add the parameter manually or else use the <xref:System.Environment> class to obtain the command-line arguments.</span></span> <span data-ttu-id="b6005-118">I parametri vengono letti come argomenti della riga di comando a indice zero.</span><span class="sxs-lookup"><span data-stu-id="b6005-118">Parameters are read as zero-indexed command-line arguments.</span></span> <span data-ttu-id="b6005-119">A differenza di quanto avviene in C e C++, il nome del programma non viene considerato il primo argomento della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="b6005-119">Unlike C and C++, the name of the program is not treated as the first command-line argument.</span></span>

<span data-ttu-id="b6005-120">L'aggiunta dei tipi restituiti `async`, `Task` e `Task<int>` semplifica il codice del programma quando è necessario avviare le applicazioni console e per operazioni asincrone `await` in `Main`.</span><span class="sxs-lookup"><span data-stu-id="b6005-120">The addition of `async` and `Task`, `Task<int>` return types simplifies program code when console applications need to start and `await` asynchronous operations in `Main`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="b6005-121">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="b6005-121">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="b6005-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b6005-122">See also</span></span>
[<span data-ttu-id="b6005-123">Compilazione dalla riga di comando con csc.exe</span><span class="sxs-lookup"><span data-stu-id="b6005-123">Command-line Building With csc.exe</span></span>](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)  
[<span data-ttu-id="b6005-124">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="b6005-124">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
[<span data-ttu-id="b6005-125">Metodi</span><span class="sxs-lookup"><span data-stu-id="b6005-125">Methods</span></span>](../../../csharp/programming-guide/classes-and-structs/methods.md)  
[<span data-ttu-id="b6005-126">Contenuto di un programma C#</span><span class="sxs-lookup"><span data-stu-id="b6005-126">Inside a C# Program</span></span>](../../../csharp/programming-guide/inside-a-program/index.md)  
