---
title: 'Procedura: utilizzare eccezioni specifiche in un blocco catch'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- exceptions, try/catch blocks
- try/catch blocks
- catch blocks
ms.assetid: 12af9ff3-8587-4f31-90cf-6c2244e0fdae
ms.openlocfilehash: 6f0956c6418d894a5768463861151f86a1948850
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75708581"
---
# <a name="how-to-use-specific-exceptions-in-a-catch-block"></a><span data-ttu-id="198f3-102">Come usare eccezioni specifiche in un blocco catch</span><span class="sxs-lookup"><span data-stu-id="198f3-102">How to use specific exceptions in a catch block</span></span>

<span data-ttu-id="198f3-103">In generale, è buona norma intercettare un tipo di eccezione specifico invece che usare un'istruzione `catch` di base.</span><span class="sxs-lookup"><span data-stu-id="198f3-103">In general, it's good programming practice to catch a specific type of exception rather than use a basic `catch` statement.</span></span>

<span data-ttu-id="198f3-104">Quando si verifica un'eccezione, l'eccezione viene passata nello stack e a ogni blocco catch viene data la possibilità di gestirla.</span><span class="sxs-lookup"><span data-stu-id="198f3-104">When an exception occurs, it is passed up the stack and each catch block is given the opportunity to handle it.</span></span> <span data-ttu-id="198f3-105">L'ordine delle istruzioni catch è importante.</span><span class="sxs-lookup"><span data-stu-id="198f3-105">The order of catch statements is important.</span></span> <span data-ttu-id="198f3-106">Inserire i blocchi catch per il rilevamento di eccezioni specifiche prima di un blocco catch generale per il rilevamento delle eccezioni per evitare che il compilatore generi un errore.</span><span class="sxs-lookup"><span data-stu-id="198f3-106">Put catch blocks targeted to specific exceptions before a general exception catch block or the compiler might issue an error.</span></span> <span data-ttu-id="198f3-107">Il blocco catch appropriato viene determinato tramite la corrispondenza del tipo di eccezione al nome dell'eccezione specificato nel blocco catch.</span><span class="sxs-lookup"><span data-stu-id="198f3-107">The proper catch block is determined by matching the type of the exception to the name of the exception specified in the catch block.</span></span> <span data-ttu-id="198f3-108">Se non è presente alcun blocco catch specifico, l'eccezione viene rilevata da un blocco catch generale, se disponibile.</span><span class="sxs-lookup"><span data-stu-id="198f3-108">If there is no specific catch block, the exception is caught by a general catch block, if one exists.</span></span>

<span data-ttu-id="198f3-109">L'esempio di codice seguente usa un blocco `try`/`catch` per rilevare <xref:System.InvalidCastException>.</span><span class="sxs-lookup"><span data-stu-id="198f3-109">The following code example uses a `try`/`catch` block to catch an <xref:System.InvalidCastException>.</span></span> <span data-ttu-id="198f3-110">L'esempio crea una classe denominata `Employee` con un'unica proprietà, il livello del dipendente (`Emlevel`).</span><span class="sxs-lookup"><span data-stu-id="198f3-110">The sample creates a class called `Employee` with a single property, employee level (`Emlevel`).</span></span> <span data-ttu-id="198f3-111">Il metodo `PromoteEmployee` accetta un oggetto e incrementa il livello del dipendente.</span><span class="sxs-lookup"><span data-stu-id="198f3-111">A method, `PromoteEmployee`, takes an object and increments the employee level.</span></span> <span data-ttu-id="198f3-112">Un'eccezione <xref:System.InvalidCastException> si verifica quando viene passata un'istanza di <xref:System.DateTime> al metodo `PromoteEmployee`.</span><span class="sxs-lookup"><span data-stu-id="198f3-112">An <xref:System.InvalidCastException> occurs when a <xref:System.DateTime> instance is passed to the `PromoteEmployee` method.</span></span>

[!code-cpp[CatchException#2](../../../samples/snippets/cpp/VS_Snippets_CLR/CatchException/CPP/catchexception1.cpp#2)]
[!code-csharp[CatchException#2](../../../samples/snippets/csharp/VS_Snippets_CLR/CatchException/CS/catchexception1.cs#2)]
[!code-vb[CatchException#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CatchException/VB/catchexception1.vb#2)] 

## <a name="see-also"></a><span data-ttu-id="198f3-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="198f3-113">See also</span></span>

- [<span data-ttu-id="198f3-114">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="198f3-114">Exceptions</span></span>](index.md)
