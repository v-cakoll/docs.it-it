---
title: 'Procedura: Chiamare una routine di overload (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], overloading
- procedures [Visual Basic], calling
- procedures [Visual Basic], multiple versions
- procedure calls [Visual Basic], overloaded
ms.assetid: 3bb331fb-f6bc-406f-9ca0-9609b497014c
ms.openlocfilehash: 9dda0fbc0cffe8904ab97c46cea40d5cf00c91e9
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58843786"
---
# <a name="how-to-call-an-overloaded-procedure-visual-basic"></a><span data-ttu-id="81175-102">Procedura: Chiamare una routine di overload (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="81175-102">How to: Call an Overloaded Procedure (Visual Basic)</span></span>
<span data-ttu-id="81175-103">Il vantaggio di overload di una routine è la flessibilità della chiamata.</span><span class="sxs-lookup"><span data-stu-id="81175-103">The advantage of overloading a procedure is in the flexibility of the call.</span></span> <span data-ttu-id="81175-104">Il codice chiamante può ottenere le informazioni che necessarie per passare alla procedura e quindi chiamare un nome di procedura singolo, indipendentemente dagli argomenti è stato superato.</span><span class="sxs-lookup"><span data-stu-id="81175-104">The calling code can obtain the information it needs to pass to the procedure and then call a single procedure name, no matter what arguments it is passing.</span></span>  
  
### <a name="to-call-a-procedure-that-has-more-than-one-version-defined"></a><span data-ttu-id="81175-105">Per chiamare una routine che ha più di una versione definita</span><span class="sxs-lookup"><span data-stu-id="81175-105">To call a procedure that has more than one version defined</span></span>  
  
1.  <span data-ttu-id="81175-106">Nel codice chiamante, determinare a quali dati da passare alla procedura.</span><span class="sxs-lookup"><span data-stu-id="81175-106">In the calling code, determine which data to pass to the procedure.</span></span>  
  
2.  <span data-ttu-id="81175-107">Scrivere la chiamata di routine in modo normale, presentazione dei dati nell'elenco di argomenti.</span><span class="sxs-lookup"><span data-stu-id="81175-107">Write the procedure call in the normal way, presenting the data in the argument list.</span></span> <span data-ttu-id="81175-108">Assicurarsi che gli argomenti corrispondono all'elenco di parametri in una delle versioni definite per la procedura.</span><span class="sxs-lookup"><span data-stu-id="81175-108">Be sure the arguments match the parameter list in one of the versions defined for the procedure.</span></span>  
  
3.  <span data-ttu-id="81175-109">Non è necessario determinare quale versione della routine da chiamare.</span><span class="sxs-lookup"><span data-stu-id="81175-109">You do not have to determine which version of the procedure to call.</span></span> <span data-ttu-id="81175-110">Visual Basic passa il controllo per la versione corrispondente all'elenco di argomenti.</span><span class="sxs-lookup"><span data-stu-id="81175-110">Visual Basic passes control to the version matching your argument list.</span></span>  
  
     <span data-ttu-id="81175-111">L'esempio seguente chiama il `post` routine dichiarata [come: Definire più versioni di una stored Procedure](./how-to-define-multiple-versions-of-a-procedure.md).</span><span class="sxs-lookup"><span data-stu-id="81175-111">The following example calls the `post` procedure declared in [How to: Define Multiple Versions of a Procedure](./how-to-define-multiple-versions-of-a-procedure.md).</span></span> <span data-ttu-id="81175-112">Ottiene l'identificazione del cliente, determina se è un `String` o un `Integer`e quindi chiama la stessa procedura in entrambi i casi.</span><span class="sxs-lookup"><span data-stu-id="81175-112">It obtains the customer identification, determines whether it is a `String` or an `Integer`, and then in either case calls the same procedure.</span></span>  
  
     [!code-vb[VbVbcnProcedures#56](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#56)]  
  
     [!code-vb[VbVbcnProcedures#57](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#57)]  
  
## <a name="see-also"></a><span data-ttu-id="81175-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="81175-113">See also</span></span>

- [<span data-ttu-id="81175-114">Routine</span><span class="sxs-lookup"><span data-stu-id="81175-114">Procedures</span></span>](./index.md)
- [<span data-ttu-id="81175-115">Parametri e argomenti delle routine</span><span class="sxs-lookup"><span data-stu-id="81175-115">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="81175-116">Overload della routine</span><span class="sxs-lookup"><span data-stu-id="81175-116">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="81175-117">Risoluzione dei problemi relativi alle routine</span><span class="sxs-lookup"><span data-stu-id="81175-117">Troubleshooting Procedures</span></span>](./troubleshooting-procedures.md)
- [<span data-ttu-id="81175-118">Procedura: Definire più versioni di una stored Procedure</span><span class="sxs-lookup"><span data-stu-id="81175-118">How to: Define Multiple Versions of a Procedure</span></span>](./how-to-define-multiple-versions-of-a-procedure.md)
- [<span data-ttu-id="81175-119">Procedura: Overload di una routine che accetta parametri facoltativi</span><span class="sxs-lookup"><span data-stu-id="81175-119">How to: Overload a Procedure that Takes Optional Parameters</span></span>](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [<span data-ttu-id="81175-120">Procedura: Eseguire l'overload di una routine che accetta un numero indefinito di parametri</span><span class="sxs-lookup"><span data-stu-id="81175-120">How to: Overload a Procedure that Takes an Indefinite Number of Parameters</span></span>](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [<span data-ttu-id="81175-121">Considerazioni sull'overload di routine</span><span class="sxs-lookup"><span data-stu-id="81175-121">Considerations in Overloading Procedures</span></span>](./considerations-in-overloading-procedures.md)
- [<span data-ttu-id="81175-122">Risoluzione dell'overload</span><span class="sxs-lookup"><span data-stu-id="81175-122">Overload Resolution</span></span>](./overload-resolution.md)
- [<span data-ttu-id="81175-123">Overload</span><span class="sxs-lookup"><span data-stu-id="81175-123">Overloads</span></span>](../../../../visual-basic/language-reference/modifiers/overloads.md)
