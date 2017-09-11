---
title: 'Procedura: chiamare una routine di overload (Visual Basic) | Documenti di Microsoft'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Visual Basic code, procedures
- procedures, overloading
- procedures, calling
- procedures, multiple versions
- procedure calls, overloaded
ms.assetid: 3bb331fb-f6bc-406f-9ca0-9609b497014c
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 777df0cc81a4e0518773a0e8cc98d590d1c0cf0d
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-call-an-overloaded-procedure-visual-basic"></a><span data-ttu-id="44b5c-102">Procedura: chiamare una routine di overload (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="44b5c-102">How to: Call an Overloaded Procedure (Visual Basic)</span></span>
<span data-ttu-id="44b5c-103">Il vantaggio di overload di una routine è la flessibilità della chiamata.</span><span class="sxs-lookup"><span data-stu-id="44b5c-103">The advantage of overloading a procedure is in the flexibility of the call.</span></span> <span data-ttu-id="44b5c-104">Il codice chiamante può ottenere le informazioni che necessarie per passare alla procedura e quindi chiamare un singolo nome di routine indipendentemente dagli argomenti passaggio.</span><span class="sxs-lookup"><span data-stu-id="44b5c-104">The calling code can obtain the information it needs to pass to the procedure and then call a single procedure name, no matter what arguments it is passing.</span></span>  
  
### <a name="to-call-a-procedure-that-has-more-than-one-version-defined"></a><span data-ttu-id="44b5c-105">Per chiamare una routine che ha definita più di una versione</span><span class="sxs-lookup"><span data-stu-id="44b5c-105">To call a procedure that has more than one version defined</span></span>  
  
1.  <span data-ttu-id="44b5c-106">Nel codice chiamante, determinare i dati da passare alla procedura.</span><span class="sxs-lookup"><span data-stu-id="44b5c-106">In the calling code, determine which data to pass to the procedure.</span></span>  
  
2.  <span data-ttu-id="44b5c-107">Scrivere la chiamata di procedura in modo normale, presentazione dei dati nell'elenco di argomenti.</span><span class="sxs-lookup"><span data-stu-id="44b5c-107">Write the procedure call in the normal way, presenting the data in the argument list.</span></span> <span data-ttu-id="44b5c-108">Assicurarsi che gli argomenti corrispondano all'elenco di parametri in una delle versioni definite per la procedura.</span><span class="sxs-lookup"><span data-stu-id="44b5c-108">Be sure the arguments match the parameter list in one of the versions defined for the procedure.</span></span>  
  
3.  <span data-ttu-id="44b5c-109">Non è necessario determinare la versione della routine da chiamare.</span><span class="sxs-lookup"><span data-stu-id="44b5c-109">You do not have to determine which version of the procedure to call.</span></span> [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="44b5c-110">passa il controllo alla versione corrispondente all'elenco di argomenti.</span><span class="sxs-lookup"><span data-stu-id="44b5c-110"> passes control to the version matching your argument list.</span></span>  
  
     <span data-ttu-id="44b5c-111">Nell'esempio seguente viene chiamato il `post` routine dichiarata in [procedura: definire più versioni di una routine](./how-to-define-multiple-versions-of-a-procedure.md).</span><span class="sxs-lookup"><span data-stu-id="44b5c-111">The following example calls the `post` procedure declared in [How to: Define Multiple Versions of a Procedure](./how-to-define-multiple-versions-of-a-procedure.md).</span></span> <span data-ttu-id="44b5c-112">Ottiene l'identificazione del cliente, determina se è un `String` o `Integer`, quindi chiama la stessa procedura in entrambi i casi.</span><span class="sxs-lookup"><span data-stu-id="44b5c-112">It obtains the customer identification, determines whether it is a `String` or an `Integer`, and then in either case calls the same procedure.</span></span>  
  
     <span data-ttu-id="44b5c-113">[!code-vb[&#56; VbVbcnProcedures](./codesnippet/VisualBasic/how-to-call-an-overloaded-procedure_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="44b5c-113">[!code-vb[VbVbcnProcedures#56](./codesnippet/VisualBasic/how-to-call-an-overloaded-procedure_1.vb)]</span></span>  
  
     <span data-ttu-id="44b5c-114">[!code-vb[VbVbcnProcedures&#57;](./codesnippet/VisualBasic/how-to-call-an-overloaded-procedure_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="44b5c-114">[!code-vb[VbVbcnProcedures#57](./codesnippet/VisualBasic/how-to-call-an-overloaded-procedure_2.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44b5c-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="44b5c-115">See Also</span></span>  
 <span data-ttu-id="44b5c-116">[Procedure](./index.md) </span><span class="sxs-lookup"><span data-stu-id="44b5c-116">[Procedures](./index.md) </span></span>  
<span data-ttu-id="44b5c-117"> [Gli argomenti e parametri di routine](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="44b5c-117"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="44b5c-118"> [Overload di routine](./procedure-overloading.md) </span><span class="sxs-lookup"><span data-stu-id="44b5c-118"> [Procedure Overloading](./procedure-overloading.md) </span></span>  
<span data-ttu-id="44b5c-119"> [Le procedure di risoluzione](./troubleshooting-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="44b5c-119"> [Troubleshooting Procedures](./troubleshooting-procedures.md) </span></span>  
<span data-ttu-id="44b5c-120"> [Procedura: definire più versioni di una routine](./how-to-define-multiple-versions-of-a-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="44b5c-120"> [How to: Define Multiple Versions of a Procedure](./how-to-define-multiple-versions-of-a-procedure.md) </span></span>  
<span data-ttu-id="44b5c-121"> [Procedura: eseguire l'Overload di una routine che accetta parametri facoltativi](./how-to-overload-a-procedure-that-takes-optional-parameters.md) </span><span class="sxs-lookup"><span data-stu-id="44b5c-121"> [How to: Overload a Procedure that Takes Optional Parameters](./how-to-overload-a-procedure-that-takes-optional-parameters.md) </span></span>  
<span data-ttu-id="44b5c-122"> [Procedura: eseguire l'Overload di una routine che accetta un numero indefinito di parametri](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md) </span><span class="sxs-lookup"><span data-stu-id="44b5c-122"> [How to: Overload a Procedure that Takes an Indefinite Number of Parameters](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md) </span></span>  
<span data-ttu-id="44b5c-123"> [Considerazioni sull'overload di routine](./considerations-in-overloading-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="44b5c-123"> [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md) </span></span>  
<span data-ttu-id="44b5c-124"> [Risoluzione dell'overload](./overload-resolution.md) </span><span class="sxs-lookup"><span data-stu-id="44b5c-124"> [Overload Resolution](./overload-resolution.md) </span></span>  
<span data-ttu-id="44b5c-125"> [Overload](../../../../visual-basic/language-reference/modifiers/overloads.md)</span><span class="sxs-lookup"><span data-stu-id="44b5c-125"> [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md)</span></span>
