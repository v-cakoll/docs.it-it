---
title: 'Procedura: definire più versioni di una routine'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedures [Visual Basic], overloading
- procedures [Visual Basic], multiple versions
- procedure overloading [Visual Basic], multiple versions
ms.assetid: 71ccdd66-1b00-4b66-bee4-6926c0d696f4
ms.openlocfilehash: e8ed9a6356b7177b2c029a9280d0790a93676653
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347588"
---
# <a name="how-to-define-multiple-versions-of-a-procedure-visual-basic"></a><span data-ttu-id="66f38-102">Procedura: definire più versioni di una routine (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="66f38-102">How to: Define Multiple Versions of a Procedure (Visual Basic)</span></span>
<span data-ttu-id="66f38-103">È possibile definire una stored procedure in più versioni eseguendo l' *Overload* , usando lo stesso nome ma un elenco di parametri diverso per ogni versione.</span><span class="sxs-lookup"><span data-stu-id="66f38-103">You can define a procedure in multiple versions by *overloading* it, using the same name but a different parameter list for each version.</span></span> <span data-ttu-id="66f38-104">Lo scopo dell'overload è definire diverse versioni strettamente correlate di una stored procedure senza doverle differenziare per nome.</span><span class="sxs-lookup"><span data-stu-id="66f38-104">The purpose of overloading is to define several closely related versions of a procedure without having to differentiate them by name.</span></span>  
  
 <span data-ttu-id="66f38-105">Per altre informazioni, vedere [Procedure Overloading](./procedure-overloading.md).</span><span class="sxs-lookup"><span data-stu-id="66f38-105">For more information, see [Procedure Overloading](./procedure-overloading.md).</span></span>  
  
### <a name="to-define-multiple-versions-of-a-procedure"></a><span data-ttu-id="66f38-106">Per definire più versioni di una routine</span><span class="sxs-lookup"><span data-stu-id="66f38-106">To define multiple versions of a procedure</span></span>  
  
1. <span data-ttu-id="66f38-107">Scrivere un'istruzione di dichiarazione `Sub` o `Function` per ogni versione della procedura che si desidera definire.</span><span class="sxs-lookup"><span data-stu-id="66f38-107">Write a `Sub` or `Function` declaration statement for each version of the procedure you want to define.</span></span> <span data-ttu-id="66f38-108">Utilizzare lo stesso nome di procedura in ogni dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="66f38-108">Use the same procedure name in every declaration.</span></span>  
  
2. <span data-ttu-id="66f38-109">Precede la parola chiave `Sub` o `Function` in ogni dichiarazione con la parola chiave [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) .</span><span class="sxs-lookup"><span data-stu-id="66f38-109">Precede the `Sub` or `Function` keyword in each declaration with the [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) keyword.</span></span> <span data-ttu-id="66f38-110">Facoltativamente, è possibile omettere `Overloads` nelle dichiarazioni, ma se lo si include in una delle dichiarazioni, è necessario includerlo in ogni dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="66f38-110">You can optionally omit `Overloads` in the declarations, but if you include it in any of the declarations, you must include it in every declaration.</span></span>  
  
3. <span data-ttu-id="66f38-111">Dopo ogni istruzione di dichiarazione, scrivere il codice della procedura per gestire il caso specifico in cui il codice chiamante fornisce argomenti corrispondenti all'elenco di parametri della versione.</span><span class="sxs-lookup"><span data-stu-id="66f38-111">Following each declaration statement, write procedure code to handle the specific case where the calling code supplies arguments matching that version's parameter list.</span></span> <span data-ttu-id="66f38-112">Non è necessario testare i parametri forniti dal codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="66f38-112">You do not have to test for which parameters the calling code has supplied.</span></span> <span data-ttu-id="66f38-113">Visual Basic passa il controllo alla versione corrispondente della routine.</span><span class="sxs-lookup"><span data-stu-id="66f38-113">Visual Basic passes control to the matching version of your procedure.</span></span>  
  
4. <span data-ttu-id="66f38-114">Terminare ogni versione della routine con l'istruzione `End Sub` o `End Function` in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="66f38-114">Terminate each version of the procedure with the `End Sub` or `End Function` statement as appropriate.</span></span>  
  
## <a name="example"></a><span data-ttu-id="66f38-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="66f38-115">Example</span></span>  
 <span data-ttu-id="66f38-116">Nell'esempio seguente viene definita una procedura `Sub` per pubblicare una transazione in base al saldo del cliente.</span><span class="sxs-lookup"><span data-stu-id="66f38-116">The following example defines a `Sub` procedure to post a transaction against a customer's balance.</span></span> <span data-ttu-id="66f38-117">Usa la parola chiave `Overloads` per definire due versioni della procedura, una che accetta il cliente in base al nome e l'altra per numero di conto.</span><span class="sxs-lookup"><span data-stu-id="66f38-117">It uses the `Overloads` keyword to define two versions of the procedure, one that accepts the customer by name and the other by account number.</span></span>  
  
 [!code-vb[VbVbcnProcedures#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#72)]  
  
 <span data-ttu-id="66f38-118">Il codice chiamante può ottenere l'identificazione del cliente come un `String` o un `Integer`e quindi usare la stessa istruzione chiamante in entrambi i casi.</span><span class="sxs-lookup"><span data-stu-id="66f38-118">The calling code can obtain the customer identification as either a `String` or an `Integer`, and then use the same calling statement in either case.</span></span>  
  
 <span data-ttu-id="66f38-119">Per informazioni su come chiamare queste versioni della procedura `post`, vedere procedura [: chiamare una routine di overload](./how-to-call-an-overloaded-procedure.md).</span><span class="sxs-lookup"><span data-stu-id="66f38-119">For information on how to call these versions of the `post` procedure, see [How to: Call an Overloaded Procedure](./how-to-call-an-overloaded-procedure.md).</span></span>  
  
## <a name="compile-the-code"></a><span data-ttu-id="66f38-120">Compilare il codice</span><span class="sxs-lookup"><span data-stu-id="66f38-120">Compile the code</span></span>  
 <span data-ttu-id="66f38-121">Verificare che ogni versione di overload abbia lo stesso nome di procedura ma un elenco di parametri diverso.</span><span class="sxs-lookup"><span data-stu-id="66f38-121">Make sure each of your overloaded versions has the same procedure name but a different parameter list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66f38-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="66f38-122">See also</span></span>

- [<span data-ttu-id="66f38-123">Routine</span><span class="sxs-lookup"><span data-stu-id="66f38-123">Procedures</span></span>](./index.md)
- [<span data-ttu-id="66f38-124">Parametri e argomenti delle routine</span><span class="sxs-lookup"><span data-stu-id="66f38-124">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="66f38-125">Risoluzione dei problemi relativi alle routine</span><span class="sxs-lookup"><span data-stu-id="66f38-125">Troubleshooting Procedures</span></span>](./troubleshooting-procedures.md)
- [<span data-ttu-id="66f38-126">Procedura: Eseguire l'overload di una routine che accetta parametri facoltativi</span><span class="sxs-lookup"><span data-stu-id="66f38-126">How to: Overload a Procedure that Takes Optional Parameters</span></span>](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [<span data-ttu-id="66f38-127">Procedura: Eseguire l'overload di una routine che accetta un numero indefinito di parametri</span><span class="sxs-lookup"><span data-stu-id="66f38-127">How to: Overload a Procedure that Takes an Indefinite Number of Parameters</span></span>](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [<span data-ttu-id="66f38-128">Considerazioni sull'overload di routine</span><span class="sxs-lookup"><span data-stu-id="66f38-128">Considerations in Overloading Procedures</span></span>](./considerations-in-overloading-procedures.md)
- [<span data-ttu-id="66f38-129">Risoluzione dell'overload</span><span class="sxs-lookup"><span data-stu-id="66f38-129">Overload Resolution</span></span>](./overload-resolution.md)
