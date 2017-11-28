---
title: "Procedura: definire più versioni di una routine (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedures [Visual Basic], overloading
- procedures [Visual Basic], multiple versions
- procedure overloading [Visual Basic], multiple versions
ms.assetid: 71ccdd66-1b00-4b66-bee4-6926c0d696f4
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 1abeaa6806252005dd3abfab3ff60bafa0c0cef1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-define-multiple-versions-of-a-procedure-visual-basic"></a><span data-ttu-id="b48bf-102">Procedura: definire più versioni di una routine (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b48bf-102">How to: Define Multiple Versions of a Procedure (Visual Basic)</span></span>
<span data-ttu-id="b48bf-103">È possibile definire una routine in più versioni da *overload* utilizzando lo stesso nome ma un elenco di parametri diversi per ogni versione.</span><span class="sxs-lookup"><span data-stu-id="b48bf-103">You can define a procedure in multiple versions by *overloading* it, using the same name but a different parameter list for each version.</span></span> <span data-ttu-id="b48bf-104">Lo scopo dell'overload consiste nel definire più versioni strettamente correlate di una stored procedure senza la necessità di distinguere per nome.</span><span class="sxs-lookup"><span data-stu-id="b48bf-104">The purpose of overloading is to define several closely related versions of a procedure without having to differentiate them by name.</span></span>  
  
 <span data-ttu-id="b48bf-105">Per ulteriori informazioni, vedere [overload di routine](./procedure-overloading.md).</span><span class="sxs-lookup"><span data-stu-id="b48bf-105">For more information, see [Procedure Overloading](./procedure-overloading.md).</span></span>  
  
### <a name="to-define-multiple-versions-of-a-procedure"></a><span data-ttu-id="b48bf-106">Per definire più versioni di una stored procedure</span><span class="sxs-lookup"><span data-stu-id="b48bf-106">To define multiple versions of a procedure</span></span>  
  
1.  <span data-ttu-id="b48bf-107">Scrivere un `Sub` o `Function` istruzione di dichiarazione per ogni versione della procedura di cui si desidera definire.</span><span class="sxs-lookup"><span data-stu-id="b48bf-107">Write a `Sub` or `Function` declaration statement for each version of the procedure you want to define.</span></span> <span data-ttu-id="b48bf-108">Usare lo stesso nome di stored procedure in ogni dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="b48bf-108">Use the same procedure name in every declaration.</span></span>  
  
2.  <span data-ttu-id="b48bf-109">Anteporre il `Sub` o `Function` (parola chiave) in ogni dichiarazione con il [overload](../../../../visual-basic/language-reference/modifiers/overloads.md) (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="b48bf-109">Precede the `Sub` or `Function` keyword in each declaration with the [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) keyword.</span></span> <span data-ttu-id="b48bf-110">È possibile omettere `Overloads` nelle dichiarazioni, ma se si include in una qualsiasi delle dichiarazioni, è necessario includerlo in ogni dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="b48bf-110">You can optionally omit `Overloads` in the declarations, but if you include it in any of the declarations, you must include it in every declaration.</span></span>  
  
3.  <span data-ttu-id="b48bf-111">Dopo ogni istruzione di dichiarazione, scrivere il codice di procedure per gestire il caso specifico in cui il codice chiamante fornisce argomenti corrispondenti elenco di parametri di quella versione.</span><span class="sxs-lookup"><span data-stu-id="b48bf-111">Following each declaration statement, write procedure code to handle the specific case where the calling code supplies arguments matching that version's parameter list.</span></span> <span data-ttu-id="b48bf-112">Non si dispone di test per i parametri che è stato fornito il codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="b48bf-112">You do not have to test for which parameters the calling code has supplied.</span></span> [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="b48bf-113">passa il controllo per la versione corrispondente della routine.</span><span class="sxs-lookup"><span data-stu-id="b48bf-113"> passes control to the matching version of your procedure.</span></span>  
  
4.  <span data-ttu-id="b48bf-114">Terminare ogni versione della routine con il `End Sub` o `End Function` istruzione nel modo appropriato.</span><span class="sxs-lookup"><span data-stu-id="b48bf-114">Terminate each version of the procedure with the `End Sub` or `End Function` statement as appropriate.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b48bf-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="b48bf-115">Example</span></span>  
 <span data-ttu-id="b48bf-116">L'esempio seguente definisce un `Sub` procedura per registrare una transazione al saldo di un cliente.</span><span class="sxs-lookup"><span data-stu-id="b48bf-116">The following example defines a `Sub` procedure to post a transaction against a customer's balance.</span></span> <span data-ttu-id="b48bf-117">Usa il `Overloads` (parola chiave) per definire due versioni della routine, una che accetta il cliente con nome e l'altra per numero di conto.</span><span class="sxs-lookup"><span data-stu-id="b48bf-117">It uses the `Overloads` keyword to define two versions of the procedure, one that accepts the customer by name and the other by account number.</span></span>  
  
 [!code-vb[VbVbcnProcedures#72](./codesnippet/VisualBasic/how-to-define-multiple-versions-of-a-procedure_1.vb)]  
  
 <span data-ttu-id="b48bf-118">Il codice chiamante può ottenere l'identificazione del cliente come un `String` o `Integer`e quindi utilizzare la stessa istruzione di chiamata in entrambi i casi.</span><span class="sxs-lookup"><span data-stu-id="b48bf-118">The calling code can obtain the customer identification as either a `String` or an `Integer`, and then use the same calling statement in either case.</span></span>  
  
 <span data-ttu-id="b48bf-119">Per informazioni su come chiamare le versioni del `post` procedura, vedere [procedura: chiamare una routine di overload](./how-to-call-an-overloaded-procedure.md).</span><span class="sxs-lookup"><span data-stu-id="b48bf-119">For information on how to call these versions of the `post` procedure, see [How to: Call an Overloaded Procedure](./how-to-call-an-overloaded-procedure.md).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b48bf-120">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="b48bf-120">Compiling the Code</span></span>  
 <span data-ttu-id="b48bf-121">Verificare che le versioni di overload con lo stesso nome di stored procedure ma un elenco di parametri diverso.</span><span class="sxs-lookup"><span data-stu-id="b48bf-121">Make sure each of your overloaded versions has the same procedure name but a different parameter list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b48bf-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b48bf-122">See Also</span></span>  
 [<span data-ttu-id="b48bf-123">Routine</span><span class="sxs-lookup"><span data-stu-id="b48bf-123">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="b48bf-124">Parametri e argomenti delle routine</span><span class="sxs-lookup"><span data-stu-id="b48bf-124">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="b48bf-125">Risoluzione dei problemi relativi alle routine</span><span class="sxs-lookup"><span data-stu-id="b48bf-125">Troubleshooting Procedures</span></span>](./troubleshooting-procedures.md)  
 [<span data-ttu-id="b48bf-126">Procedura: Eseguire l'overload di una routine che accetta parametri facoltativi</span><span class="sxs-lookup"><span data-stu-id="b48bf-126">How to: Overload a Procedure that Takes Optional Parameters</span></span>](./how-to-overload-a-procedure-that-takes-optional-parameters.md)  
 [<span data-ttu-id="b48bf-127">Procedura: Eseguire l'overload di una routine che accetta un numero indefinito di parametri</span><span class="sxs-lookup"><span data-stu-id="b48bf-127">How to: Overload a Procedure that Takes an Indefinite Number of Parameters</span></span>](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)  
 [<span data-ttu-id="b48bf-128">Considerazioni sull'overload di routine</span><span class="sxs-lookup"><span data-stu-id="b48bf-128">Considerations in Overloading Procedures</span></span>](./considerations-in-overloading-procedures.md)  
 [<span data-ttu-id="b48bf-129">Risoluzione dell'overload</span><span class="sxs-lookup"><span data-stu-id="b48bf-129">Overload Resolution</span></span>](./overload-resolution.md)
