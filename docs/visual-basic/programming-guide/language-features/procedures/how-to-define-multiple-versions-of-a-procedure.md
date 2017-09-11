---
title: "Procedura: definire più versioni di una routine (Visual Basic) | Documenti di Microsoft"
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
- procedures, defining
- Visual Basic code, procedures
- procedures, overloading
- procedures, multiple versions
- procedure overloading, multiple versions
ms.assetid: 71ccdd66-1b00-4b66-bee4-6926c0d696f4
caps.latest.revision: 14
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
ms.openlocfilehash: f4296ba3a78316b70011bcca18f7071716f3c90d
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-define-multiple-versions-of-a-procedure-visual-basic"></a><span data-ttu-id="dac6d-102">Procedura: definire più versioni di una routine (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dac6d-102">How to: Define Multiple Versions of a Procedure (Visual Basic)</span></span>
<span data-ttu-id="dac6d-103">È possibile definire una routine in più versioni da *overload* quest'ultima, usando lo stesso nome ma un elenco di parametri diversi per ogni versione.</span><span class="sxs-lookup"><span data-stu-id="dac6d-103">You can define a procedure in multiple versions by *overloading* it, using the same name but a different parameter list for each version.</span></span> <span data-ttu-id="dac6d-104">Lo scopo dell'overload è definire più versioni strettamente correlate di una procedura senza la necessità di distinguere per nome.</span><span class="sxs-lookup"><span data-stu-id="dac6d-104">The purpose of overloading is to define several closely related versions of a procedure without having to differentiate them by name.</span></span>  
  
 <span data-ttu-id="dac6d-105">Per ulteriori informazioni, vedere [overload di routine](./procedure-overloading.md).</span><span class="sxs-lookup"><span data-stu-id="dac6d-105">For more information, see [Procedure Overloading](./procedure-overloading.md).</span></span>  
  
### <a name="to-define-multiple-versions-of-a-procedure"></a><span data-ttu-id="dac6d-106">Per definire più versioni di una routine</span><span class="sxs-lookup"><span data-stu-id="dac6d-106">To define multiple versions of a procedure</span></span>  
  
1.  <span data-ttu-id="dac6d-107">Scrivere un `Sub` o `Function` istruzione di dichiarazione per ogni versione della procedura di cui si desidera definire.</span><span class="sxs-lookup"><span data-stu-id="dac6d-107">Write a `Sub` or `Function` declaration statement for each version of the procedure you want to define.</span></span> <span data-ttu-id="dac6d-108">Utilizzare lo stesso nome di procedura in ogni dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="dac6d-108">Use the same procedure name in every declaration.</span></span>  
  
2.  <span data-ttu-id="dac6d-109">Far precedere il `Sub` o `Function` (parola chiave) in ogni dichiarazione con la [overload](../../../../visual-basic/language-reference/modifiers/overloads.md) (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="dac6d-109">Precede the `Sub` or `Function` keyword in each declaration with the [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) keyword.</span></span> <span data-ttu-id="dac6d-110">È possibile omettere `Overloads` nelle dichiarazioni, ma se si include in una di queste dichiarazioni, è necessario includerlo in ogni dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="dac6d-110">You can optionally omit `Overloads` in the declarations, but if you include it in any of the declarations, you must include it in every declaration.</span></span>  
  
3.  <span data-ttu-id="dac6d-111">Dopo ogni istruzione di dichiarazione, scrivere codice procedure per gestire il caso specifico in cui il codice chiamante fornisce argomenti corrispondenti elenco di parametri di quella versione.</span><span class="sxs-lookup"><span data-stu-id="dac6d-111">Following each declaration statement, write procedure code to handle the specific case where the calling code supplies arguments matching that version's parameter list.</span></span> <span data-ttu-id="dac6d-112">Non è necessario testare per i parametri che ha fornito il codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="dac6d-112">You do not have to test for which parameters the calling code has supplied.</span></span> [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="dac6d-113">passa il controllo alla versione corrispondente della routine.</span><span class="sxs-lookup"><span data-stu-id="dac6d-113"> passes control to the matching version of your procedure.</span></span>  
  
4.  <span data-ttu-id="dac6d-114">Terminare ogni versione della routine con il `End Sub` o `End Function` istruzione nel modo appropriato.</span><span class="sxs-lookup"><span data-stu-id="dac6d-114">Terminate each version of the procedure with the `End Sub` or `End Function` statement as appropriate.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dac6d-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="dac6d-115">Example</span></span>  
 <span data-ttu-id="dac6d-116">L'esempio seguente definisce una `Sub` procedura per registrare una transazione al saldo del cliente.</span><span class="sxs-lookup"><span data-stu-id="dac6d-116">The following example defines a `Sub` procedure to post a transaction against a customer's balance.</span></span> <span data-ttu-id="dac6d-117">Usa il `Overloads` (parola chiave) per definire due versioni della routine, una che accetta il cliente per nome e l'altra per numero di conto.</span><span class="sxs-lookup"><span data-stu-id="dac6d-117">It uses the `Overloads` keyword to define two versions of the procedure, one that accepts the customer by name and the other by account number.</span></span>  
  
 <span data-ttu-id="dac6d-118">[!code-vb[VbVbcnProcedures&#72;](./codesnippet/VisualBasic/how-to-define-multiple-versions-of-a-procedure_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="dac6d-118">[!code-vb[VbVbcnProcedures#72](./codesnippet/VisualBasic/how-to-define-multiple-versions-of-a-procedure_1.vb)]</span></span>  
  
 <span data-ttu-id="dac6d-119">Il codice chiamante può ottenere l'identificazione del cliente come un `String` o `Integer`, quindi utilizzare la stessa istruzione di chiamata in entrambi i casi.</span><span class="sxs-lookup"><span data-stu-id="dac6d-119">The calling code can obtain the customer identification as either a `String` or an `Integer`, and then use the same calling statement in either case.</span></span>  
  
 <span data-ttu-id="dac6d-120">Per informazioni sulla chiamata di queste versioni di `post` procedura, vedere [procedura: chiamare una routine di overload](./how-to-call-an-overloaded-procedure.md).</span><span class="sxs-lookup"><span data-stu-id="dac6d-120">For information on how to call these versions of the `post` procedure, see [How to: Call an Overloaded Procedure](./how-to-call-an-overloaded-procedure.md).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="dac6d-121">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="dac6d-121">Compiling the Code</span></span>  
 <span data-ttu-id="dac6d-122">Assicurarsi che le versioni di overload con lo stesso nome di procedura ma un elenco di parametri diverso.</span><span class="sxs-lookup"><span data-stu-id="dac6d-122">Make sure each of your overloaded versions has the same procedure name but a different parameter list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dac6d-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dac6d-123">See Also</span></span>  
 <span data-ttu-id="dac6d-124">[Procedure](./index.md) </span><span class="sxs-lookup"><span data-stu-id="dac6d-124">[Procedures](./index.md) </span></span>  
<span data-ttu-id="dac6d-125"> [Gli argomenti e parametri di routine](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="dac6d-125"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="dac6d-126"> [Le procedure di risoluzione](./troubleshooting-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="dac6d-126"> [Troubleshooting Procedures](./troubleshooting-procedures.md) </span></span>  
<span data-ttu-id="dac6d-127"> [Procedura: eseguire l'Overload di una routine che accetta parametri facoltativi](./how-to-overload-a-procedure-that-takes-optional-parameters.md) </span><span class="sxs-lookup"><span data-stu-id="dac6d-127"> [How to: Overload a Procedure that Takes Optional Parameters](./how-to-overload-a-procedure-that-takes-optional-parameters.md) </span></span>  
<span data-ttu-id="dac6d-128"> [Procedura: eseguire l'Overload di una routine che accetta un numero indefinito di parametri](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md) </span><span class="sxs-lookup"><span data-stu-id="dac6d-128"> [How to: Overload a Procedure that Takes an Indefinite Number of Parameters](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md) </span></span>  
<span data-ttu-id="dac6d-129"> [Considerazioni sull'overload di routine](./considerations-in-overloading-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="dac6d-129"> [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md) </span></span>  
<span data-ttu-id="dac6d-130"> [Risoluzione dell'overload](./overload-resolution.md)</span><span class="sxs-lookup"><span data-stu-id="dac6d-130"> [Overload Resolution](./overload-resolution.md)</span></span>
