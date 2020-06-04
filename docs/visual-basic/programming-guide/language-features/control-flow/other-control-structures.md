---
title: Altre strutture di controllo
ms.date: 07/20/2015
helpviewer_keywords:
- statements [Visual Basic], control flow
- control structures [Visual Basic]
ms.assetid: 24b811f7-98ba-40ec-8dd3-4d528cfa4574
ms.openlocfilehash: c6d80b237c7c3512c2904547842fdeb3c69bef68
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84402018"
---
# <a name="other-control-structures-visual-basic"></a><span data-ttu-id="b3d67-102">Altre strutture di controllo (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b3d67-102">Other Control Structures (Visual Basic)</span></span>
<span data-ttu-id="b3d67-103">Visual Basic fornisce strutture di controllo che consentono di eliminare una risorsa o ridurre il numero di volte in cui è necessario ripetere un riferimento a un oggetto.</span><span class="sxs-lookup"><span data-stu-id="b3d67-103">Visual Basic provides control structures that help you dispose of a resource or reduce the number of times you have to repeat an object reference.</span></span>  
  
## <a name="usingend-using-construction"></a><span data-ttu-id="b3d67-104">Uso di... Termina usando la costruzione</span><span class="sxs-lookup"><span data-stu-id="b3d67-104">Using...End Using Construction</span></span>  
 <span data-ttu-id="b3d67-105">La `Using...End Using` costruzione stabilisce un blocco di istruzioni all'interno del quale si utilizza una risorsa, ad esempio una connessione SQL.</span><span class="sxs-lookup"><span data-stu-id="b3d67-105">The `Using...End Using` construction establishes a statement block within which you make use of a resource such as a SQL connection.</span></span> <span data-ttu-id="b3d67-106">Facoltativamente, è possibile acquisire la risorsa con l' `Using` istruzione.</span><span class="sxs-lookup"><span data-stu-id="b3d67-106">You can optionally acquire the resource with the `Using` statement.</span></span> <span data-ttu-id="b3d67-107">Quando si esce dal `Using` blocco, Visual Basic Elimina automaticamente la risorsa in modo che sia disponibile per l'uso da parte di altro codice.</span><span class="sxs-lookup"><span data-stu-id="b3d67-107">When you exit the `Using` block, Visual Basic automatically disposes of the resource so that it is available for other code to use.</span></span> <span data-ttu-id="b3d67-108">La risorsa deve essere locale e eliminabile.</span><span class="sxs-lookup"><span data-stu-id="b3d67-108">The resource must be local and disposable.</span></span> <span data-ttu-id="b3d67-109">Per ulteriori informazioni, vedere [istruzione using](../../../language-reference/statements/using-statement.md).</span><span class="sxs-lookup"><span data-stu-id="b3d67-109">For more information, see [Using Statement](../../../language-reference/statements/using-statement.md).</span></span>  
  
## <a name="withend-with-construction"></a><span data-ttu-id="b3d67-110">Con... Termina con costruzione</span><span class="sxs-lookup"><span data-stu-id="b3d67-110">With...End With Construction</span></span>  
 <span data-ttu-id="b3d67-111">La `With...End With` costruzione consente di specificare un riferimento a un oggetto una volta, quindi di eseguire una serie di istruzioni che accedono ai relativi membri.</span><span class="sxs-lookup"><span data-stu-id="b3d67-111">The `With...End With` construction lets you specify an object reference once and then run a series of statements that access its members.</span></span> <span data-ttu-id="b3d67-112">In questo modo è possibile semplificare il codice e migliorare le prestazioni in quanto Visual Basic non è necessario ristabilire il riferimento per ogni istruzione che vi accede.</span><span class="sxs-lookup"><span data-stu-id="b3d67-112">This can simplify your code and improve performance because Visual Basic does not have to re-establish the reference for each statement that accesses it.</span></span> <span data-ttu-id="b3d67-113">Per ulteriori informazioni, vedere [con... Termina con l'istruzione](../../../language-reference/statements/with-end-with-statement.md).</span><span class="sxs-lookup"><span data-stu-id="b3d67-113">For more information, see [With...End With Statement](../../../language-reference/statements/with-end-with-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3d67-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b3d67-114">See also</span></span>

- [<span data-ttu-id="b3d67-115">Flusso di controllo</span><span class="sxs-lookup"><span data-stu-id="b3d67-115">Control Flow</span></span>](index.md)
- [<span data-ttu-id="b3d67-116">Strutture decisionali</span><span class="sxs-lookup"><span data-stu-id="b3d67-116">Decision Structures</span></span>](decision-structures.md)
- [<span data-ttu-id="b3d67-117">Strutture di ciclo</span><span class="sxs-lookup"><span data-stu-id="b3d67-117">Loop Structures</span></span>](loop-structures.md)
- [<span data-ttu-id="b3d67-118">Strutture di controllo annidate</span><span class="sxs-lookup"><span data-stu-id="b3d67-118">Nested Control Structures</span></span>](nested-control-structures.md)
- [<span data-ttu-id="b3d67-119">Istruzione using</span><span class="sxs-lookup"><span data-stu-id="b3d67-119">Using Statement</span></span>](../../../language-reference/statements/using-statement.md)
- [<span data-ttu-id="b3d67-120">Istruzione With...End With</span><span class="sxs-lookup"><span data-stu-id="b3d67-120">With...End With Statement</span></span>](../../../language-reference/statements/with-end-with-statement.md)
