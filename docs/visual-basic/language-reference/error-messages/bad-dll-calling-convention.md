---
title: Convenzione di chiamata DLL non valida
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID49
ms.assetid: 7c7def45-b0ab-450f-ad3f-4383dfd9aed7
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: daa84e82d2fbe1041af56fdd5cc3855efd814ddf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="bad-dll-calling-convention"></a><span data-ttu-id="9ed42-102">Convenzione di chiamata DLL non valida</span><span class="sxs-lookup"><span data-stu-id="9ed42-102">Bad DLL calling convention</span></span>
<span data-ttu-id="9ed42-103">Gli argomenti passati a una libreria di collegamento dinamico (DLL) devono corrispondere esattamente a quelli previsti per la routine.</span><span class="sxs-lookup"><span data-stu-id="9ed42-103">Arguments passed to a dynamic-link library (DLL) must exactly match those expected by the routine.</span></span> <span data-ttu-id="9ed42-104">Convenzioni di chiamata affrontare numero, tipo e ordine degli argomenti.</span><span class="sxs-lookup"><span data-stu-id="9ed42-104">Calling conventions deal with number, type, and order of arguments.</span></span> <span data-ttu-id="9ed42-105">Il programma può chiamare una routine in una DLL che viene passata il tipo non corretto o il numero di argomenti.</span><span class="sxs-lookup"><span data-stu-id="9ed42-105">Your program may be calling a routine in a DLL that is being passed the wrong type or number of arguments.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="9ed42-106">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="9ed42-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="9ed42-107">Assicurarsi che tutti i tipi di argomento corrispondano a quelli specificati nella dichiarazione di routine che si sta chiamando.</span><span class="sxs-lookup"><span data-stu-id="9ed42-107">Make sure all argument types agree with those specified in the declaration of the routine that you are calling.</span></span>  
  
2.  <span data-ttu-id="9ed42-108">Verificare che si sta passando lo stesso numero di argomenti indicati nella dichiarazione della routine che si sta chiamando.</span><span class="sxs-lookup"><span data-stu-id="9ed42-108">Make sure you are passing the same number of arguments indicated in the declaration of the routine that you are calling.</span></span>  
  
3.  <span data-ttu-id="9ed42-109">Se la routine della DLL prevede gli argomenti per valore, assicurarsi che `ByVal` viene specificato per gli argomenti nella dichiarazione della routine.</span><span class="sxs-lookup"><span data-stu-id="9ed42-109">If the DLL routine expects arguments by value, make sure `ByVal` is specified for those arguments in the declaration for the routine.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ed42-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9ed42-110">See Also</span></span>  
 [<span data-ttu-id="9ed42-111">Tipi di errore</span><span class="sxs-lookup"><span data-stu-id="9ed42-111">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)  
 [<span data-ttu-id="9ed42-112">Istruzione Call</span><span class="sxs-lookup"><span data-stu-id="9ed42-112">Call Statement</span></span>](../../../visual-basic/language-reference/statements/call-statement.md)  
 [<span data-ttu-id="9ed42-113">Istruzione Declare</span><span class="sxs-lookup"><span data-stu-id="9ed42-113">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)
