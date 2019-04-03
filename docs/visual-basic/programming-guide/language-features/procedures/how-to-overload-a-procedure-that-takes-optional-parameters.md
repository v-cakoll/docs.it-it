---
title: 'Procedura: Overload di una routine che accetta parametri facoltativi (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], parameters
- procedure overloading [Visual Basic], optional parameters
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedure parameters
- procedures [Visual Basic], overloading
- procedures [Visual Basic], multiple versions
ms.assetid: 825f9d56-4cde-43fd-993a-b9171717e2eb
ms.openlocfilehash: 070d641d5a8b683ddfe06039117cc4a8507102df
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58827633"
---
# <a name="how-to-overload-a-procedure-that-takes-optional-parameters-visual-basic"></a>Procedura: Overload di una routine che accetta parametri facoltativi (Visual Basic)
Se una routine contiene uno o più [facoltativo](../../../../visual-basic/language-reference/modifiers/optional.md) parametri, non è possibile definire una versione di overload corrisponda a uno dei relativi overload impliciti. Per altre informazioni, vedere "Esegue l'overload implicito per i parametri facoltativi" nella [considerazioni sull'overload di routine](./considerations-in-overloading-procedures.md).  
  
## <a name="one-optional-parameter"></a>Un parametro facoltativo  
  
#### <a name="to-overload-a-procedure-that-takes-one-optional-parameter"></a>Eseguire l'overload di una routine che accetta un parametro facoltativo  
  
1.  Scrivere un `Sub` o `Function` istruzione di dichiarazione che include il parametro facoltativo nell'elenco dei parametri. Non usare il `Optional` parola chiave in questa versione di overload.  
  
2.  Far precedere il `Sub` o `Function` parola chiave with il [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) (parola chiave).  
  
3.  Scrivere il codice della routine che deve essere eseguita quando il codice chiamante fornisce un argomento facoltativo.  
  
4.  Terminare la procedura con il `End Sub` o `End Function` istruzione nel modo appropriato.  
  
5.  Scrivere una seconda istruzione di dichiarazione che è identica alla prima dichiarazione, ma non include il parametro facoltativo nell'elenco dei parametri.  
  
6.  Scrivere il codice della routine che deve essere eseguita quando il codice chiamante non specifica l'argomento facoltativo. Terminare la procedura con il `End Sub` o `End Function` istruzione nel modo appropriato.  
  
     Nell'esempio seguente illustra una procedura definita con un parametro facoltativo, un set equivalente di due routine di overload e, infine, esempi di versioni di overload valide e non è valide.  
  
     [!code-vb[VbVbcnProcedures#59](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#59)]  
  
     [!code-vb[VbVbcnProcedures#60](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#60)]  
  
     [!code-vb[VbVbcnProcedures#61](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#61)]  
  
## <a name="multiple-optional-parameters"></a>Più parametri facoltativi  
 Per una procedura con più di un parametro facoltativo, in genere è necessario più di due versioni di overload. Ad esempio, se sono presenti due parametri facoltativi e il codice chiamante può specificare o omettere ognuno di essi indipendentemente da altra, è necessario quattro versioni di overload, uno per ogni possibile combinazione di argomenti forniti.  
  
 Man mano che aumenta il numero di parametri facoltativi, aumenta la complessità dell'overload. Se non alcune combinazioni di argomenti forniti non sono accettabili, per i parametri facoltativi N deve essere 2 ^ N versioni di overload. A seconda della natura della procedura, si noterà che la chiarezza di logica giustifica lo sforzo aggiuntivo della definizione di tutte le versioni di overload.  
  
#### <a name="to-overload-a-procedure-that-takes-more-than-one-optional-parameter"></a>Eseguire l'overload di una routine che accetta più di un parametro facoltativo  
  
1.  Stabilisce le combinazioni di argomenti facoltativi forniti accettabili per la logica della routine. Una combinazione inaccettabile potrebbe verificarsi se un parametro facoltativo dipende da un'altra. Ad esempio, se un parametro accetta il nome del personale dell'assistenza e un altro accetta l'età, una combinazione di argomenti che specifica l'età, ma omette il nome è accettabile.  
  
2.  Per ogni combinazione accettabili di argomenti facoltativi forniti, scrivere un `Sub` o `Function` istruzione di dichiarazione che definisce l'elenco di parametri corrispondenti. Non usare il `Optional` (parola chiave).  
  
3.  In ogni dichiarazione, anteporre il `Sub` o `Function` parola chiave with il [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) (parola chiave).  
  
4.  Dopo ogni dichiarazione, scrivere il codice che deve essere eseguita quando il codice chiamante fornisce un elenco di argomenti corrispondenti all'elenco dei parametri della dichiarazione della routine.  
  
5.  Terminare ogni procedura con il `End Sub` o `End Function` istruzione nel modo appropriato.  
  
## <a name="see-also"></a>Vedere anche

- [Routine](./index.md)
- [Parametri e argomenti delle routine](./procedure-parameters-and-arguments.md)
- [Parametri facoltativi](./optional-parameters.md)
- [Matrici di parametri](./parameter-arrays.md)
- [Overload della routine](./procedure-overloading.md)
- [Risoluzione dei problemi relativi alle routine](./troubleshooting-procedures.md)
- [Procedura: Definire più versioni di una stored Procedure](./how-to-define-multiple-versions-of-a-procedure.md)
- [Procedura: Chiamare una routine di overload](./how-to-call-an-overloaded-procedure.md)
- [Procedura: Eseguire l'overload di una routine che accetta un numero indefinito di parametri](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [Risoluzione dell'overload](./overload-resolution.md)
