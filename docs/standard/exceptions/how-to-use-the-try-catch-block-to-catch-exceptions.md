---
title: 'Procedura: Usare il blocco try/catch per intercettare le eccezioni'
description: Utilizzare il blocco try per contenere istruzioni che potrebbero generare o generare un'eccezione. Inserire istruzioni per gestire le eccezioni in uno o più blocchi catch.
ms.date: 02/06/2019
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- exceptions, try/catch blocks
- try blocks
- try/catch blocks
- catch blocks
ms.assetid: a3ce6dfd-1f64-471b-8ad8-8cfaf406275d
ms.openlocfilehash: 60ed213ea777fe35873fd1e67555b7506e3ca587
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/15/2020
ms.locfileid: "84768911"
---
# <a name="how-to-use-the-trycatch-block-to-catch-exceptions"></a><span data-ttu-id="f1295-104">Come usare il blocco try/catch per rilevare le eccezioni</span><span class="sxs-lookup"><span data-stu-id="f1295-104">How to use the try/catch block to catch exceptions</span></span>

<span data-ttu-id="f1295-105">Inserire le istruzioni di codice che possono generare un'eccezione in un blocco `try` e inserire le istruzioni usate per gestire l'eccezione o le eccezioni in uno o più blocchi `catch` sotto il blocco `try`.</span><span class="sxs-lookup"><span data-stu-id="f1295-105">Place any code statements that might raise or throw an exception in a `try` block, and place statements used to handle the exception or exceptions in one or more `catch` blocks below the `try` block.</span></span> <span data-ttu-id="f1295-106">Ogni blocco `catch` include il tipo di eccezione e può contenere istruzioni aggiuntive necessarie per gestire quel tipo di eccezione.</span><span class="sxs-lookup"><span data-stu-id="f1295-106">Each `catch` block includes the exception type and can contain additional statements needed to handle that exception type.</span></span>

<span data-ttu-id="f1295-107">Nell'esempio seguente un oggetto <xref:System.IO.StreamReader> apre un file chiamato *data.txt* e recupera una riga dal file.</span><span class="sxs-lookup"><span data-stu-id="f1295-107">In the following example, a <xref:System.IO.StreamReader> opens a file called *data.txt* and retrieves a line from the file.</span></span> <span data-ttu-id="f1295-108">Dato che il codice può generare una qualsiasi delle tre eccezioni disponibili, viene inserito in un blocco `try`.</span><span class="sxs-lookup"><span data-stu-id="f1295-108">Since the code might throw any of three exceptions, it's placed in a `try` block.</span></span> <span data-ttu-id="f1295-109">Tre blocchi `catch` intercettano le eccezioni e le gestiscono mediante la visualizzazione dei risultati nella console.</span><span class="sxs-lookup"><span data-stu-id="f1295-109">Three `catch` blocks catch the exceptions and handle them by displaying the results to the console.</span></span>

[!code-csharp[CatchException#3](~/samples/snippets/csharp/VS_Snippets_CLR/CatchException/CS/catchexception2.cs#3)]
[!code-vb[CatchException#3](~/samples/snippets/visualbasic/VS_Snippets_CLR/CatchException/VB/catchexception2.vb#3)]

<span data-ttu-id="f1295-110">Common Language Runtime (CLR) rileva le eccezioni non gestite dai blocchi `catch`.</span><span class="sxs-lookup"><span data-stu-id="f1295-110">The Common Language Runtime (CLR) catches exceptions not handled by `catch` blocks.</span></span> <span data-ttu-id="f1295-111">Se un'eccezione viene rilevata da CLR, a seconda della configurazione di CLR può verificarsi uno dei risultati seguenti:</span><span class="sxs-lookup"><span data-stu-id="f1295-111">If an exception is caught by the CLR, one of the following results may occur depending on your CLR configuration:</span></span>

- <span data-ttu-id="f1295-112">Viene visualizzata la finestra di dialogo **Debug**.</span><span class="sxs-lookup"><span data-stu-id="f1295-112">A **Debug** dialog box appears.</span></span>
- <span data-ttu-id="f1295-113">Il programma interrompe l'esecuzione e viene visualizzata una finestra di dialogo con informazioni sull'eccezione.</span><span class="sxs-lookup"><span data-stu-id="f1295-113">The program stops execution and a dialog box with exception information appears.</span></span>
- <span data-ttu-id="f1295-114">Viene visualizzato un errore nel [flusso di output degli errori standard](xref:System.Console.Error).</span><span class="sxs-lookup"><span data-stu-id="f1295-114">An error prints out to the [standard error output stream](xref:System.Console.Error).</span></span>

> [!NOTE]
> <span data-ttu-id="f1295-115">La maggior parte del codice può generare un'eccezione. Alcune eccezioni, ad esempio <xref:System.OutOfMemoryException>, possono essere generate da CLR in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="f1295-115">Most code can throw an exception, and some exceptions, like <xref:System.OutOfMemoryException>, can be thrown by the CLR itself at any time.</span></span> <span data-ttu-id="f1295-116">Le applicazioni non sono necessarie per gestire queste eccezioni, ma tenere presente questa possibilità quando si creano librerie che devono essere usate da altri utenti.</span><span class="sxs-lookup"><span data-stu-id="f1295-116">While applications aren't required to deal with these exceptions, be aware of the possibility when writing libraries to be used by others.</span></span> <span data-ttu-id="f1295-117">Per suggerimenti su quando impostare il codice di un blocco `try`, vedere [Procedure consigliate per le eccezioni](best-practices-for-exceptions.md).</span><span class="sxs-lookup"><span data-stu-id="f1295-117">For suggestions on when to set code in a `try` block, see [Best Practices for Exceptions](best-practices-for-exceptions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f1295-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f1295-118">See also</span></span>

- [<span data-ttu-id="f1295-119">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="f1295-119">Exceptions</span></span>](index.md)
- [<span data-ttu-id="f1295-120">Gestione degli errori di I/O in .NET</span><span class="sxs-lookup"><span data-stu-id="f1295-120">Handling I/O errors in .NET</span></span>](../io/handling-io-errors.md)
