---
title: 'Procedura: Definire più versioni di una routine (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedures [Visual Basic], overloading
- procedures [Visual Basic], multiple versions
- procedure overloading [Visual Basic], multiple versions
ms.assetid: 71ccdd66-1b00-4b66-bee4-6926c0d696f4
ms.openlocfilehash: c31c9ad05af04aec5dc41790aea530c62611f500
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58841173"
---
# <a name="how-to-define-multiple-versions-of-a-procedure-visual-basic"></a><span data-ttu-id="31469-102">Procedura: Definire più versioni di una routine (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="31469-102">How to: Define Multiple Versions of a Procedure (Visual Basic)</span></span>
<span data-ttu-id="31469-103">È possibile definire una procedura in più versioni da *overload* utilizzando lo stesso nome ma un elenco di parametri diversi per ogni versione.</span><span class="sxs-lookup"><span data-stu-id="31469-103">You can define a procedure in multiple versions by *overloading* it, using the same name but a different parameter list for each version.</span></span> <span data-ttu-id="31469-104">Lo scopo dell'overload consiste nel definire più versioni strettamente correlate di una stored procedure senza la necessità di distinguerli in base al nome.</span><span class="sxs-lookup"><span data-stu-id="31469-104">The purpose of overloading is to define several closely related versions of a procedure without having to differentiate them by name.</span></span>  
  
 <span data-ttu-id="31469-105">Per altre informazioni, vedere [Procedure Overloading](./procedure-overloading.md).</span><span class="sxs-lookup"><span data-stu-id="31469-105">For more information, see [Procedure Overloading](./procedure-overloading.md).</span></span>  
  
### <a name="to-define-multiple-versions-of-a-procedure"></a><span data-ttu-id="31469-106">Per definire più versioni di una stored procedure</span><span class="sxs-lookup"><span data-stu-id="31469-106">To define multiple versions of a procedure</span></span>  
  
1.  <span data-ttu-id="31469-107">Scrivere un `Sub` o `Function` istruzione di dichiarazione per ciascuna versione della procedura di cui si vuole definire.</span><span class="sxs-lookup"><span data-stu-id="31469-107">Write a `Sub` or `Function` declaration statement for each version of the procedure you want to define.</span></span> <span data-ttu-id="31469-108">Usare il nome della routine stessa in ogni dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="31469-108">Use the same procedure name in every declaration.</span></span>  
  
2.  <span data-ttu-id="31469-109">Far precedere il `Sub` o `Function` parola chiave in ogni dichiarazione con la [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="31469-109">Precede the `Sub` or `Function` keyword in each declaration with the [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) keyword.</span></span> <span data-ttu-id="31469-110">Facoltativamente, è possibile omettere `Overloads` nelle dichiarazioni, ma se si include in una qualsiasi delle dichiarazioni, è necessario includerlo in ogni dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="31469-110">You can optionally omit `Overloads` in the declarations, but if you include it in any of the declarations, you must include it in every declaration.</span></span>  
  
3.  <span data-ttu-id="31469-111">Dopo ogni istruzione di dichiarazione, scrivere il codice delle procedure per gestire il caso specifico in cui il codice chiamante fornisca gli argomenti corrispondenti elenco di parametri di tale versione.</span><span class="sxs-lookup"><span data-stu-id="31469-111">Following each declaration statement, write procedure code to handle the specific case where the calling code supplies arguments matching that version's parameter list.</span></span> <span data-ttu-id="31469-112">Non è necessario testare per i parametri che ha fornito il codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="31469-112">You do not have to test for which parameters the calling code has supplied.</span></span> <span data-ttu-id="31469-113">Visual Basic passa il controllo per la versione corrispondente di routine.</span><span class="sxs-lookup"><span data-stu-id="31469-113">Visual Basic passes control to the matching version of your procedure.</span></span>  
  
4.  <span data-ttu-id="31469-114">Terminare ogni versione della routine con la `End Sub` o `End Function` istruzione nel modo appropriato.</span><span class="sxs-lookup"><span data-stu-id="31469-114">Terminate each version of the procedure with the `End Sub` or `End Function` statement as appropriate.</span></span>  
  
## <a name="example"></a><span data-ttu-id="31469-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="31469-115">Example</span></span>  
 <span data-ttu-id="31469-116">L'esempio seguente definisce un `Sub` procedure per inserire una transazione al saldo di un cliente.</span><span class="sxs-lookup"><span data-stu-id="31469-116">The following example defines a `Sub` procedure to post a transaction against a customer's balance.</span></span> <span data-ttu-id="31469-117">Usa il `Overloads` parola chiave per definire due versioni della routine, uno che accetta il cliente per nome e l'altro per numero di account.</span><span class="sxs-lookup"><span data-stu-id="31469-117">It uses the `Overloads` keyword to define two versions of the procedure, one that accepts the customer by name and the other by account number.</span></span>  
  
 [!code-vb[VbVbcnProcedures#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#72)]  
  
 <span data-ttu-id="31469-118">Il codice chiamante può ottenere l'identificazione del cliente come un `String` o un `Integer`e quindi usare la stessa istruzione di chiamata in entrambi i casi.</span><span class="sxs-lookup"><span data-stu-id="31469-118">The calling code can obtain the customer identification as either a `String` or an `Integer`, and then use the same calling statement in either case.</span></span>  
  
 <span data-ttu-id="31469-119">Per informazioni su come chiamare queste versioni del `post` procedure, vedere [come: Chiamare una routine di overload](./how-to-call-an-overloaded-procedure.md).</span><span class="sxs-lookup"><span data-stu-id="31469-119">For information on how to call these versions of the `post` procedure, see [How to: Call an Overloaded Procedure](./how-to-call-an-overloaded-procedure.md).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="31469-120">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="31469-120">Compiling the Code</span></span>  
 <span data-ttu-id="31469-121">Assicurarsi che ognuna delle versioni di overload con lo stesso nome di procedura ma un elenco di parametri diverso.</span><span class="sxs-lookup"><span data-stu-id="31469-121">Make sure each of your overloaded versions has the same procedure name but a different parameter list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31469-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="31469-122">See also</span></span>

- [<span data-ttu-id="31469-123">Routine</span><span class="sxs-lookup"><span data-stu-id="31469-123">Procedures</span></span>](./index.md)
- [<span data-ttu-id="31469-124">Parametri e argomenti delle routine</span><span class="sxs-lookup"><span data-stu-id="31469-124">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="31469-125">Risoluzione dei problemi relativi alle routine</span><span class="sxs-lookup"><span data-stu-id="31469-125">Troubleshooting Procedures</span></span>](./troubleshooting-procedures.md)
- [<span data-ttu-id="31469-126">Procedura: Overload di una routine che accetta parametri facoltativi</span><span class="sxs-lookup"><span data-stu-id="31469-126">How to: Overload a Procedure that Takes Optional Parameters</span></span>](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [<span data-ttu-id="31469-127">Procedura: Eseguire l'overload di una routine che accetta un numero indefinito di parametri</span><span class="sxs-lookup"><span data-stu-id="31469-127">How to: Overload a Procedure that Takes an Indefinite Number of Parameters</span></span>](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [<span data-ttu-id="31469-128">Considerazioni sull'overload di routine</span><span class="sxs-lookup"><span data-stu-id="31469-128">Considerations in Overloading Procedures</span></span>](./considerations-in-overloading-procedures.md)
- [<span data-ttu-id="31469-129">Risoluzione dell'overload</span><span class="sxs-lookup"><span data-stu-id="31469-129">Overload Resolution</span></span>](./overload-resolution.md)
