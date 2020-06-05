---
title: 'Procedura: chiamare una routine di overload'
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], overloading
- procedures [Visual Basic], calling
- procedures [Visual Basic], multiple versions
- procedure calls [Visual Basic], overloaded
ms.assetid: 3bb331fb-f6bc-406f-9ca0-9609b497014c
ms.openlocfilehash: de101309fa1edaaddc3defc5759d9293fbef684c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84388543"
---
# <a name="how-to-call-an-overloaded-procedure-visual-basic"></a><span data-ttu-id="cc2ff-102">Procedura: chiamare una routine di overload (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cc2ff-102">How to: Call an Overloaded Procedure (Visual Basic)</span></span>
<span data-ttu-id="cc2ff-103">Il vantaggio dell'overload di una stored procedure è la flessibilità della chiamata.</span><span class="sxs-lookup"><span data-stu-id="cc2ff-103">The advantage of overloading a procedure is in the flexibility of the call.</span></span> <span data-ttu-id="cc2ff-104">Il codice chiamante può ottenere le informazioni necessarie per passare alla routine e quindi chiamare un solo nome di routine, indipendentemente dagli argomenti che passano.</span><span class="sxs-lookup"><span data-stu-id="cc2ff-104">The calling code can obtain the information it needs to pass to the procedure and then call a single procedure name, no matter what arguments it is passing.</span></span>  
  
### <a name="to-call-a-procedure-that-has-more-than-one-version-defined"></a><span data-ttu-id="cc2ff-105">Per chiamare una routine con più di una versione definita</span><span class="sxs-lookup"><span data-stu-id="cc2ff-105">To call a procedure that has more than one version defined</span></span>  
  
1. <span data-ttu-id="cc2ff-106">Nel codice chiamante determinare i dati da passare alla routine.</span><span class="sxs-lookup"><span data-stu-id="cc2ff-106">In the calling code, determine which data to pass to the procedure.</span></span>  
  
2. <span data-ttu-id="cc2ff-107">Scrivere la chiamata di procedura in modo normale, presentando i dati nell'elenco di argomenti.</span><span class="sxs-lookup"><span data-stu-id="cc2ff-107">Write the procedure call in the normal way, presenting the data in the argument list.</span></span> <span data-ttu-id="cc2ff-108">Assicurarsi che gli argomenti corrispondano all'elenco di parametri in una delle versioni definite per la stored procedure.</span><span class="sxs-lookup"><span data-stu-id="cc2ff-108">Be sure the arguments match the parameter list in one of the versions defined for the procedure.</span></span>  
  
3. <span data-ttu-id="cc2ff-109">Non è necessario determinare la versione della procedura da chiamare.</span><span class="sxs-lookup"><span data-stu-id="cc2ff-109">You do not have to determine which version of the procedure to call.</span></span> <span data-ttu-id="cc2ff-110">Visual Basic passa il controllo alla versione corrispondente all'elenco di argomenti.</span><span class="sxs-lookup"><span data-stu-id="cc2ff-110">Visual Basic passes control to the version matching your argument list.</span></span>  
  
     <span data-ttu-id="cc2ff-111">Nell'esempio seguente viene chiamata la `post` procedura dichiarata in [procedura: definire più versioni di una routine](./how-to-define-multiple-versions-of-a-procedure.md).</span><span class="sxs-lookup"><span data-stu-id="cc2ff-111">The following example calls the `post` procedure declared in [How to: Define Multiple Versions of a Procedure](./how-to-define-multiple-versions-of-a-procedure.md).</span></span> <span data-ttu-id="cc2ff-112">Ottiene l'identificazione del cliente, determina se è un `String` oggetto o `Integer` , quindi in entrambi i casi chiama la stessa procedura.</span><span class="sxs-lookup"><span data-stu-id="cc2ff-112">It obtains the customer identification, determines whether it is a `String` or an `Integer`, and then in either case calls the same procedure.</span></span>  
  
     [!code-vb[VbVbcnProcedures#56](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#56)]  
  
     [!code-vb[VbVbcnProcedures#57](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#57)]  
  
## <a name="see-also"></a><span data-ttu-id="cc2ff-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cc2ff-113">See also</span></span>

- [<span data-ttu-id="cc2ff-114">Procedure</span><span class="sxs-lookup"><span data-stu-id="cc2ff-114">Procedures</span></span>](./index.md)
- [<span data-ttu-id="cc2ff-115">Parametri e argomenti delle routine</span><span class="sxs-lookup"><span data-stu-id="cc2ff-115">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="cc2ff-116">Overload della routine</span><span class="sxs-lookup"><span data-stu-id="cc2ff-116">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="cc2ff-117">Risoluzione dei problemi relativi alle routine</span><span class="sxs-lookup"><span data-stu-id="cc2ff-117">Troubleshooting Procedures</span></span>](./troubleshooting-procedures.md)
- [<span data-ttu-id="cc2ff-118">Procedura: definire più versioni di una routine</span><span class="sxs-lookup"><span data-stu-id="cc2ff-118">How to: Define Multiple Versions of a Procedure</span></span>](./how-to-define-multiple-versions-of-a-procedure.md)
- [<span data-ttu-id="cc2ff-119">Procedura: eseguire l'overload di una routine che accetta parametri facoltativi</span><span class="sxs-lookup"><span data-stu-id="cc2ff-119">How to: Overload a Procedure that Takes Optional Parameters</span></span>](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [<span data-ttu-id="cc2ff-120">Procedura: eseguire l'overload di una routine che accetta un numero indefinito di parametri</span><span class="sxs-lookup"><span data-stu-id="cc2ff-120">How to: Overload a Procedure that Takes an Indefinite Number of Parameters</span></span>](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [<span data-ttu-id="cc2ff-121">Considerazioni sull'overload di routine</span><span class="sxs-lookup"><span data-stu-id="cc2ff-121">Considerations in Overloading Procedures</span></span>](./considerations-in-overloading-procedures.md)
- [<span data-ttu-id="cc2ff-122">Risoluzione dell'overload</span><span class="sxs-lookup"><span data-stu-id="cc2ff-122">Overload Resolution</span></span>](./overload-resolution.md)
- [<span data-ttu-id="cc2ff-123">Overload</span><span class="sxs-lookup"><span data-stu-id="cc2ff-123">Overloads</span></span>](../../../language-reference/modifiers/overloads.md)
