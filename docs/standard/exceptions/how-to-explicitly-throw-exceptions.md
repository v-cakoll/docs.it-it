---
title: 'Procedura: generare eccezioni in modo esplicito'
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4eeb70c10d71a7c96136039342bcdcc7bc8ece20
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33570341"
---
# <a name="how-to-explicitly-throw-exceptions"></a><span data-ttu-id="e6c2d-102">Come generare in modo esplicito le eccezioni</span><span class="sxs-lookup"><span data-stu-id="e6c2d-102">How to explicitly throw exceptions</span></span>

<span data-ttu-id="e6c2d-103">È possibile generare in modo esplicito un'eccezione usando l'istruzione `throw`.</span><span class="sxs-lookup"><span data-stu-id="e6c2d-103">You can explicitly throw an exception using the `throw` statement.</span></span> <span data-ttu-id="e6c2d-104">È anche possibile generare di nuovo un'eccezione rilevata usando l'istruzione `throw`.</span><span class="sxs-lookup"><span data-stu-id="e6c2d-104">You can also throw a caught exception again using the `throw` statement.</span></span> <span data-ttu-id="e6c2d-105">Si consiglia di aggiungere informazioni a un'eccezione generata di nuovo per offrire ulteriori informazioni durante il debug.</span><span class="sxs-lookup"><span data-stu-id="e6c2d-105">It is good coding practice to add information to an exception that is re-thrown to provide more information when debugging.</span></span>

<span data-ttu-id="e6c2d-106">L'esempio di codice seguente usa un blocco `try`/`catch` per rilevare una possibile eccezione <xref:System.IO.FileNotFoundException>.</span><span class="sxs-lookup"><span data-stu-id="e6c2d-106">The following code example uses a `try`/`catch` block to catch a possible <xref:System.IO.FileNotFoundException>.</span></span> <span data-ttu-id="e6c2d-107">Il blocco `try` è seguito da un blocco `catch` che rileva <xref:System.IO.FileNotFoundException> e scrive un messaggio nella console se il file di dati non viene trovato.</span><span class="sxs-lookup"><span data-stu-id="e6c2d-107">Following the `try` block is a `catch` block that catches the <xref:System.IO.FileNotFoundException> and writes a message to the console if the data file is not found.</span></span> <span data-ttu-id="e6c2d-108">L'istruzione successiva è l'istruzione `throw` che genera una nuova eccezione <xref:System.IO.FileNotFoundException> e aggiunge informazioni di testo all'eccezione.</span><span class="sxs-lookup"><span data-stu-id="e6c2d-108">The next statement is the `throw` statement that throws a new <xref:System.IO.FileNotFoundException> and adds text information to the exception.</span></span>

[!code-csharp[Exception.Throwing#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Exception.Throwing/CS/throw.cs#1)]
[!code-vb[Exception.Throwing#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Exception.Throwing/VB/throw.vb#1)]  

## <a name="see-also"></a><span data-ttu-id="e6c2d-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e6c2d-109">See Also</span></span>  
[<span data-ttu-id="e6c2d-110">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="e6c2d-110">Exceptions</span></span>](index.md)
