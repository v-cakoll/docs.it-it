---
title: Convenzione di chiamata DLL non valida
ms.date: 07/20/2015
f1_keywords:
- vbrID49
ms.assetid: 7c7def45-b0ab-450f-ad3f-4383dfd9aed7
ms.openlocfilehash: a60e44ce92b1805b0a5a6f1d4ce397c295eef202
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409881"
---
# <a name="bad-dll-calling-convention"></a><span data-ttu-id="169e4-102">Convenzione di chiamata DLL non valida</span><span class="sxs-lookup"><span data-stu-id="169e4-102">Bad DLL calling convention</span></span>
<span data-ttu-id="169e4-103">Gli argomenti passati a una libreria di collegamento dinamico (DLL) devono corrispondere esattamente a quelli previsti dalla routine.</span><span class="sxs-lookup"><span data-stu-id="169e4-103">Arguments passed to a dynamic-link library (DLL) must exactly match those expected by the routine.</span></span> <span data-ttu-id="169e4-104">Le convenzioni di chiamata gestiscono il numero, il tipo e l'ordine degli argomenti.</span><span class="sxs-lookup"><span data-stu-id="169e4-104">Calling conventions deal with number, type, and order of arguments.</span></span> <span data-ttu-id="169e4-105">È possibile che il programma chiami una routine in una DLL a cui viene passato il tipo o il numero di argomenti errato.</span><span class="sxs-lookup"><span data-stu-id="169e4-105">Your program may be calling a routine in a DLL that is being passed the wrong type or number of arguments.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="169e4-106">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="169e4-106">To correct this error</span></span>  
  
1. <span data-ttu-id="169e4-107">Verificare che tutti i tipi di argomento condividano quelli specificati nella dichiarazione della routine che si sta chiamando.</span><span class="sxs-lookup"><span data-stu-id="169e4-107">Make sure all argument types agree with those specified in the declaration of the routine that you are calling.</span></span>  
  
2. <span data-ttu-id="169e4-108">Assicurarsi di passare lo stesso numero di argomenti indicato nella dichiarazione della routine che si sta chiamando.</span><span class="sxs-lookup"><span data-stu-id="169e4-108">Make sure you are passing the same number of arguments indicated in the declaration of the routine that you are calling.</span></span>  
  
3. <span data-ttu-id="169e4-109">Se la routine DLL prevede gli argomenti per valore, assicurarsi che `ByVal` sia specificato per gli argomenti nella dichiarazione per la routine.</span><span class="sxs-lookup"><span data-stu-id="169e4-109">If the DLL routine expects arguments by value, make sure `ByVal` is specified for those arguments in the declaration for the routine.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="169e4-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="169e4-110">See also</span></span>

- [<span data-ttu-id="169e4-111">Tipi di errore</span><span class="sxs-lookup"><span data-stu-id="169e4-111">Error Types</span></span>](../../programming-guide/language-features/error-types.md)
- [<span data-ttu-id="169e4-112">Istruzione Call</span><span class="sxs-lookup"><span data-stu-id="169e4-112">Call Statement</span></span>](../statements/call-statement.md)
- [<span data-ttu-id="169e4-113">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="169e4-113">Declare Statement</span></span>](../statements/declare-statement.md)
