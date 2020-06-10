---
title: 'Procedura: generare eccezioni in modo esplicito'
description: Informazioni su come generare un'eccezione in modo esplicito in .NET usando l'istruzione throw di C# o l'istruzione Visual Basic Throw.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- exceptions, try/catch blocks
- FileNotFoundException class
- try/catch blocks
- exceptions, throwing
- implicitly throwing exceptions
ms.assetid: 72bdd157-caa9-4478-9ee3-cb4500b84528
ms.openlocfilehash: 2dd939f9edd58ba91ea74df5d6930087849f0560
ms.sourcegitcommit: 7137e12f54c4e83a94ae43ec320f8cf59c1772ea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/10/2020
ms.locfileid: "84662784"
---
# <a name="how-to-explicitly-throw-exceptions"></a><span data-ttu-id="f533a-103">Come generare in modo esplicito le eccezioni</span><span class="sxs-lookup"><span data-stu-id="f533a-103">How to explicitly throw exceptions</span></span>

<span data-ttu-id="f533a-104">È possibile generare in modo esplicito un'eccezione usando l' [`throw`](../../csharp/language-reference/keywords/throw.md) istruzione C# o Visual Basic [`Throw`](../../visual-basic/language-reference/statements/throw-statement.md) .</span><span class="sxs-lookup"><span data-stu-id="f533a-104">You can explicitly throw an exception using the C# [`throw`](../../csharp/language-reference/keywords/throw.md) or the Visual Basic [`Throw`](../../visual-basic/language-reference/statements/throw-statement.md) statement.</span></span> <span data-ttu-id="f533a-105">È anche possibile generare di nuovo un'eccezione rilevata usando l'istruzione `throw`.</span><span class="sxs-lookup"><span data-stu-id="f533a-105">You can also throw a caught exception again using the `throw` statement.</span></span> <span data-ttu-id="f533a-106">Si consiglia di aggiungere informazioni a un'eccezione generata di nuovo per offrire ulteriori informazioni durante il debug.</span><span class="sxs-lookup"><span data-stu-id="f533a-106">It is good coding practice to add information to an exception that is re-thrown to provide more information when debugging.</span></span>

<span data-ttu-id="f533a-107">L'esempio di codice seguente usa un blocco `try`/`catch` per rilevare una possibile eccezione <xref:System.IO.FileNotFoundException>.</span><span class="sxs-lookup"><span data-stu-id="f533a-107">The following code example uses a `try`/`catch` block to catch a possible <xref:System.IO.FileNotFoundException>.</span></span> <span data-ttu-id="f533a-108">Il blocco `try` è seguito da un blocco `catch` che rileva <xref:System.IO.FileNotFoundException> e scrive un messaggio nella console se il file di dati non viene trovato.</span><span class="sxs-lookup"><span data-stu-id="f533a-108">Following the `try` block is a `catch` block that catches the <xref:System.IO.FileNotFoundException> and writes a message to the console if the data file is not found.</span></span> <span data-ttu-id="f533a-109">L'istruzione successiva è l'istruzione `throw` che genera una nuova eccezione <xref:System.IO.FileNotFoundException> e aggiunge informazioni di testo all'eccezione.</span><span class="sxs-lookup"><span data-stu-id="f533a-109">The next statement is the `throw` statement that throws a new <xref:System.IO.FileNotFoundException> and adds text information to the exception.</span></span>

[!code-csharp[Exception.Throwing#1](~/samples/snippets/csharp/VS_Snippets_CLR/Exception.Throwing/CS/throw.cs#1)]
[!code-vb[Exception.Throwing#1](~/samples/snippets/visualbasic/VS_Snippets_CLR/Exception.Throwing/VB/throw.vb#1)]  

## <a name="see-also"></a><span data-ttu-id="f533a-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f533a-110">See also</span></span>

- [<span data-ttu-id="f533a-111">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="f533a-111">Exceptions</span></span>](index.md)
