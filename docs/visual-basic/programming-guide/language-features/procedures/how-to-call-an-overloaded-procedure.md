---
title: 'Procedura: chiamare una routine di overload (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], overloading
- procedures [Visual Basic], calling
- procedures [Visual Basic], multiple versions
- procedure calls [Visual Basic], overloaded
ms.assetid: 3bb331fb-f6bc-406f-9ca0-9609b497014c
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ff5967c1b09ad59f249297b1cf0a4ed900faf4a1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-call-an-overloaded-procedure-visual-basic"></a><span data-ttu-id="a62cf-102">Procedura: chiamare una routine di overload (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a62cf-102">How to: Call an Overloaded Procedure (Visual Basic)</span></span>
<span data-ttu-id="a62cf-103">Il vantaggio di overload di una routine è la flessibilità della chiamata.</span><span class="sxs-lookup"><span data-stu-id="a62cf-103">The advantage of overloading a procedure is in the flexibility of the call.</span></span> <span data-ttu-id="a62cf-104">Il codice chiamante può ottenere le informazioni che necessarie per passare alla procedura e quindi chiamare un singolo nome di routine indipendentemente dagli argomenti passaggio.</span><span class="sxs-lookup"><span data-stu-id="a62cf-104">The calling code can obtain the information it needs to pass to the procedure and then call a single procedure name, no matter what arguments it is passing.</span></span>  
  
### <a name="to-call-a-procedure-that-has-more-than-one-version-defined"></a><span data-ttu-id="a62cf-105">Per chiamare una routine con più di una versione definita</span><span class="sxs-lookup"><span data-stu-id="a62cf-105">To call a procedure that has more than one version defined</span></span>  
  
1.  <span data-ttu-id="a62cf-106">Nel codice chiamante, determinano i dati da passare alla procedura.</span><span class="sxs-lookup"><span data-stu-id="a62cf-106">In the calling code, determine which data to pass to the procedure.</span></span>  
  
2.  <span data-ttu-id="a62cf-107">Chiamata di routine di scrittura in modo normale, presentazione dei dati nell'elenco di argomenti.</span><span class="sxs-lookup"><span data-stu-id="a62cf-107">Write the procedure call in the normal way, presenting the data in the argument list.</span></span> <span data-ttu-id="a62cf-108">Assicurarsi che gli argomenti corrispondere l'elenco di parametri in una delle versioni definite per la routine.</span><span class="sxs-lookup"><span data-stu-id="a62cf-108">Be sure the arguments match the parameter list in one of the versions defined for the procedure.</span></span>  
  
3.  <span data-ttu-id="a62cf-109">Non è necessario determinare la versione della routine da chiamare.</span><span class="sxs-lookup"><span data-stu-id="a62cf-109">You do not have to determine which version of the procedure to call.</span></span> [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="a62cf-110">passa il controllo di versione che corrisponde all'elenco di argomenti.</span><span class="sxs-lookup"><span data-stu-id="a62cf-110"> passes control to the version matching your argument list.</span></span>  
  
     <span data-ttu-id="a62cf-111">L'esempio seguente chiama il `post` routine è dichiarata [procedura: definire più versioni di una stored Procedure](./how-to-define-multiple-versions-of-a-procedure.md).</span><span class="sxs-lookup"><span data-stu-id="a62cf-111">The following example calls the `post` procedure declared in [How to: Define Multiple Versions of a Procedure](./how-to-define-multiple-versions-of-a-procedure.md).</span></span> <span data-ttu-id="a62cf-112">Viene ottenuto l'identificazione del cliente, che determina se è un `String` o `Integer`e quindi chiama la stessa procedura in entrambi i casi.</span><span class="sxs-lookup"><span data-stu-id="a62cf-112">It obtains the customer identification, determines whether it is a `String` or an `Integer`, and then in either case calls the same procedure.</span></span>  
  
     [!code-vb[VbVbcnProcedures#56](./codesnippet/VisualBasic/how-to-call-an-overloaded-procedure_1.vb)]  
  
     [!code-vb[VbVbcnProcedures#57](./codesnippet/VisualBasic/how-to-call-an-overloaded-procedure_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="a62cf-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a62cf-113">See Also</span></span>  
 [<span data-ttu-id="a62cf-114">Routine</span><span class="sxs-lookup"><span data-stu-id="a62cf-114">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="a62cf-115">Parametri e argomenti delle routine</span><span class="sxs-lookup"><span data-stu-id="a62cf-115">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="a62cf-116">Overload della routine</span><span class="sxs-lookup"><span data-stu-id="a62cf-116">Procedure Overloading</span></span>](./procedure-overloading.md)  
 [<span data-ttu-id="a62cf-117">Risoluzione dei problemi relativi alle routine</span><span class="sxs-lookup"><span data-stu-id="a62cf-117">Troubleshooting Procedures</span></span>](./troubleshooting-procedures.md)  
 [<span data-ttu-id="a62cf-118">Procedura: Definire più versioni di una routine</span><span class="sxs-lookup"><span data-stu-id="a62cf-118">How to: Define Multiple Versions of a Procedure</span></span>](./how-to-define-multiple-versions-of-a-procedure.md)  
 [<span data-ttu-id="a62cf-119">Procedura: Eseguire l'overload di una routine che accetta parametri facoltativi</span><span class="sxs-lookup"><span data-stu-id="a62cf-119">How to: Overload a Procedure that Takes Optional Parameters</span></span>](./how-to-overload-a-procedure-that-takes-optional-parameters.md)  
 [<span data-ttu-id="a62cf-120">Procedura: Eseguire l'overload di una routine che accetta un numero indefinito di parametri</span><span class="sxs-lookup"><span data-stu-id="a62cf-120">How to: Overload a Procedure that Takes an Indefinite Number of Parameters</span></span>](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)  
 [<span data-ttu-id="a62cf-121">Considerazioni sull'overload di routine</span><span class="sxs-lookup"><span data-stu-id="a62cf-121">Considerations in Overloading Procedures</span></span>](./considerations-in-overloading-procedures.md)  
 [<span data-ttu-id="a62cf-122">Risoluzione dell'overload</span><span class="sxs-lookup"><span data-stu-id="a62cf-122">Overload Resolution</span></span>](./overload-resolution.md)  
 [<span data-ttu-id="a62cf-123">Overload</span><span class="sxs-lookup"><span data-stu-id="a62cf-123">Overloads</span></span>](../../../../visual-basic/language-reference/modifiers/overloads.md)
