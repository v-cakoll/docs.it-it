---
title: Altre strutture di controllo
ms.date: 07/20/2015
helpviewer_keywords:
- statements [Visual Basic], control flow
- control structures [Visual Basic]
ms.assetid: 24b811f7-98ba-40ec-8dd3-4d528cfa4574
ms.openlocfilehash: 758df361f421684655147ae288af3f350e53c4d7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348139"
---
# <a name="other-control-structures-visual-basic"></a><span data-ttu-id="ecc34-102">Altre strutture di controllo (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ecc34-102">Other Control Structures (Visual Basic)</span></span>
<span data-ttu-id="ecc34-103">Visual Basic fornisce strutture di controllo che consentono di eliminare una risorsa o ridurre il numero di volte in cui è necessario ripetere un riferimento a un oggetto.</span><span class="sxs-lookup"><span data-stu-id="ecc34-103">Visual Basic provides control structures that help you dispose of a resource or reduce the number of times you have to repeat an object reference.</span></span>  
  
## <a name="usingend-using-construction"></a><span data-ttu-id="ecc34-104">Uso di... Termina usando la costruzione</span><span class="sxs-lookup"><span data-stu-id="ecc34-104">Using...End Using Construction</span></span>  
 <span data-ttu-id="ecc34-105">La costruzione `Using...End Using` stabilisce un blocco di istruzioni all'interno del quale si utilizza una risorsa, ad esempio una connessione SQL.</span><span class="sxs-lookup"><span data-stu-id="ecc34-105">The `Using...End Using` construction establishes a statement block within which you make use of a resource such as a SQL connection.</span></span> <span data-ttu-id="ecc34-106">Facoltativamente, è possibile acquisire la risorsa con l'istruzione `Using`.</span><span class="sxs-lookup"><span data-stu-id="ecc34-106">You can optionally acquire the resource with the `Using` statement.</span></span> <span data-ttu-id="ecc34-107">Quando si esce dal blocco `Using`, Visual Basic Elimina automaticamente la risorsa in modo che sia disponibile per l'uso da parte di altro codice.</span><span class="sxs-lookup"><span data-stu-id="ecc34-107">When you exit the `Using` block, Visual Basic automatically disposes of the resource so that it is available for other code to use.</span></span> <span data-ttu-id="ecc34-108">La risorsa deve essere locale e eliminabile.</span><span class="sxs-lookup"><span data-stu-id="ecc34-108">The resource must be local and disposable.</span></span> <span data-ttu-id="ecc34-109">Per altre informazioni, vedere [Istruzione using](../../../../visual-basic/language-reference/statements/using-statement.md).</span><span class="sxs-lookup"><span data-stu-id="ecc34-109">For more information, see [Using Statement](../../../../visual-basic/language-reference/statements/using-statement.md).</span></span>  
  
## <a name="withend-with-construction"></a><span data-ttu-id="ecc34-110">Con... Termina con costruzione</span><span class="sxs-lookup"><span data-stu-id="ecc34-110">With...End With Construction</span></span>  
 <span data-ttu-id="ecc34-111">La costruzione di `With...End With` consente di specificare un riferimento a un oggetto una volta, quindi di eseguire una serie di istruzioni che accedono ai relativi membri.</span><span class="sxs-lookup"><span data-stu-id="ecc34-111">The `With...End With` construction lets you specify an object reference once and then run a series of statements that access its members.</span></span> <span data-ttu-id="ecc34-112">In questo modo è possibile semplificare il codice e migliorare le prestazioni in quanto Visual Basic non è necessario ristabilire il riferimento per ogni istruzione che vi accede.</span><span class="sxs-lookup"><span data-stu-id="ecc34-112">This can simplify your code and improve performance because Visual Basic does not have to re-establish the reference for each statement that accesses it.</span></span> <span data-ttu-id="ecc34-113">Per ulteriori informazioni, vedere [con... Termina con l'istruzione](../../../../visual-basic/language-reference/statements/with-end-with-statement.md).</span><span class="sxs-lookup"><span data-stu-id="ecc34-113">For more information, see [With...End With Statement](../../../../visual-basic/language-reference/statements/with-end-with-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ecc34-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ecc34-114">See also</span></span>

- [<span data-ttu-id="ecc34-115">Flusso di controllo</span><span class="sxs-lookup"><span data-stu-id="ecc34-115">Control Flow</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [<span data-ttu-id="ecc34-116">Strutture decisionali</span><span class="sxs-lookup"><span data-stu-id="ecc34-116">Decision Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [<span data-ttu-id="ecc34-117">Strutture di ciclo</span><span class="sxs-lookup"><span data-stu-id="ecc34-117">Loop Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="ecc34-118">Strutture di controllo annidate</span><span class="sxs-lookup"><span data-stu-id="ecc34-118">Nested Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="ecc34-119">Istruzione Using</span><span class="sxs-lookup"><span data-stu-id="ecc34-119">Using Statement</span></span>](../../../../visual-basic/language-reference/statements/using-statement.md)
- [<span data-ttu-id="ecc34-120">Istruzione With...End With</span><span class="sxs-lookup"><span data-stu-id="ecc34-120">With...End With Statement</span></span>](../../../../visual-basic/language-reference/statements/with-end-with-statement.md)
