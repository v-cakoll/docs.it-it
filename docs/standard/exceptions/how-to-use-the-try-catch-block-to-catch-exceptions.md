---
title: 'Procedura: Usare il blocco try/catch per intercettare le eccezioni'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- exceptions, try/catch blocks
- try blocks
- try/catch blocks
- catch blocks
ms.assetid: a3ce6dfd-1f64-471b-8ad8-8cfaf406275d
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 852df5cb3eeea2ee5fa44ddce2f97e9c4f8d8b5a
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/16/2018
ms.locfileid: "45618087"
---
# <a name="how-to-use-the-trycatch-block-to-catch-exceptions"></a><span data-ttu-id="a74da-102">Come usare il blocco try/catch per rilevare le eccezioni</span><span class="sxs-lookup"><span data-stu-id="a74da-102">How to use the try/catch block to catch exceptions</span></span>

<span data-ttu-id="a74da-103">Inserire le sezioni di codice che potrebbero generare eccezioni in un blocco `try` e il codice che gestisce le eccezioni in un blocco `catch`.</span><span class="sxs-lookup"><span data-stu-id="a74da-103">Place the sections of code that might throw exceptions in a `try` block and place code that handles exceptions in a `catch` block.</span></span> <span data-ttu-id="a74da-104">Il blocco `catch` è una serie di istruzioni che iniziano con la parola chiave `catch`, seguita da un tipo di eccezione e un'azione da eseguire.</span><span class="sxs-lookup"><span data-stu-id="a74da-104">The `catch` block is a series of statements beginning with the keyword `catch`, followed by an exception type and an action to be taken.</span></span>

<span data-ttu-id="a74da-105">L'esempio di codice seguente usa un blocco `try`/`catch` per rilevare una possibile eccezione.</span><span class="sxs-lookup"><span data-stu-id="a74da-105">The following code example uses a `try`/`catch` block to catch a possible exception.</span></span> <span data-ttu-id="a74da-106">Il metodo `Main` contiene un blocco `try` con un'istruzione <xref:System.IO.StreamReader> che apre un file di dati denominato `data.txt` e scrive una stringa del file.</span><span class="sxs-lookup"><span data-stu-id="a74da-106">The `Main` method contains a `try` block with a <xref:System.IO.StreamReader> statement that opens a data file called `data.txt` and writes a string from the file.</span></span> <span data-ttu-id="a74da-107">Il blocco `try` è seguito da un blocco `catch` che rileva qualsiasi eccezione del blocco `try`.</span><span class="sxs-lookup"><span data-stu-id="a74da-107">Following the `try` block is a `catch` block that catches any exception that results from the `try` block.</span></span>

 [!code-cpp[CatchException#3](../../../samples/snippets/cpp/VS_Snippets_CLR/CatchException/CPP/catchexception2.cpp#3)]
 [!code-csharp[CatchException#3](../../../samples/snippets/csharp/VS_Snippets_CLR/CatchException/CS/catchexception2.cs#3)]
 [!code-vb[CatchException#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CatchException/VB/catchexception2.vb#3)]  

<span data-ttu-id="a74da-108">Common Language Runtime rileva le eccezioni non rilevate da un blocco catch.</span><span class="sxs-lookup"><span data-stu-id="a74da-108">The common language runtime catches exceptions that are not caught by a catch block.</span></span> <span data-ttu-id="a74da-109">A seconda della configurazione del runtime, viene visualizzata una finestra di dialogo di debug, viene interrotta l'esecuzione del programma e viene visualizzata una finestra di dialogo con le informazioni sull'eccezione o viene stampato un errore in STDERR.</span><span class="sxs-lookup"><span data-stu-id="a74da-109">Depending on how the runtime is configured, a debug dialog box appears, or the program stops executing and a dialog box with exception information appears, or an error is printed out to STDERR.</span></span>

> [!NOTE] 
> <span data-ttu-id="a74da-110">Quasi tutte le righe di codice possono causare un'eccezione, in particolare eccezioni generate da Common Language Runtime, ad esempio <xref:System.OutOfMemoryException>.</span><span class="sxs-lookup"><span data-stu-id="a74da-110">Almost any line of code can cause an exception, particularly exceptions that are thrown by the common language runtime itself, such as <xref:System.OutOfMemoryException>.</span></span> <span data-ttu-id="a74da-111">Sebbene nella maggior parte delle applicazioni non sia necessario gestire queste eccezioni, considerare questa eventualità quando si creano librerie che devono essere usate da altri utenti.</span><span class="sxs-lookup"><span data-stu-id="a74da-111">Most applications don't have to deal with these exceptions, but you should be aware of this possibility when writing libraries to be used by others.</span></span> <span data-ttu-id="a74da-112">Per suggerimenti su quando impostare il codice di un blocco Try, vedere [Procedure consigliate per le eccezioni](best-practices-for-exceptions.md).</span><span class="sxs-lookup"><span data-stu-id="a74da-112">For suggestions on when to set code in a Try block, see [Best Practices for Exceptions](best-practices-for-exceptions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a74da-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a74da-113">See also</span></span>

- [<span data-ttu-id="a74da-114">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="a74da-114">Exceptions</span></span>](index.md)
