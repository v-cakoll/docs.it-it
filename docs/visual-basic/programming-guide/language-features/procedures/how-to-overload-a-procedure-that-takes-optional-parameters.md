---
title: "Procedura: eseguire l'overload di una routine che accetta parametri facoltativi"
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
ms.openlocfilehash: 4d31980e4b968cff274091ba4f307dffddab1100
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350859"
---
# <a name="how-to-overload-a-procedure-that-takes-optional-parameters-visual-basic"></a>Procedura: eseguire l'overload di una routine che accetta parametri facoltativi (Visual Basic)
Se una stored procedure ha uno o più parametri [facoltativi](../../../../visual-basic/language-reference/modifiers/optional.md) , non è possibile definire una versione di overload corrispondente a uno qualsiasi degli overload impliciti. Per ulteriori informazioni, vedere "Overload impliciti per i parametri facoltativi" in [considerazioni sull'overload delle procedure](./considerations-in-overloading-procedures.md).  
  
## <a name="one-optional-parameter"></a>Un parametro facoltativo  
  
#### <a name="to-overload-a-procedure-that-takes-one-optional-parameter"></a>Per eseguire l'overload di una routine che accetta un parametro facoltativo  
  
1. Scrivere un'istruzione di dichiarazione `Sub` o `Function` che includa il parametro facoltativo nell'elenco di parametri. Non utilizzare la parola chiave `Optional` in questa versione di overload.  
  
2. Precede la `Sub` o la parola chiave `Function` con la parola chiave [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) .  
  
3. Scrivere il codice della procedura da eseguire quando il codice chiamante fornisce l'argomento facoltativo.  
  
4. Terminare la procedura con l'istruzione `End Sub` o `End Function` in base alle esigenze.  
  
5. Scrivere una seconda istruzione di dichiarazione identica alla prima dichiarazione, ad eccezione del fatto che non include il parametro facoltativo nell'elenco di parametri.  
  
6. Scrivere il codice della procedura da eseguire quando il codice chiamante non fornisce l'argomento facoltativo. Terminare la procedura con l'istruzione `End Sub` o `End Function` in base alle esigenze.  
  
     Nell'esempio seguente viene illustrata una procedura definita con un parametro facoltativo, un set equivalente di due procedure di overload e infine esempi di versioni di overload valide e non valide.  
  
     [!code-vb[VbVbcnProcedures#59](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#59)]  
  
     [!code-vb[VbVbcnProcedures#60](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#60)]  
  
     [!code-vb[VbVbcnProcedures#61](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#61)]  
  
## <a name="multiple-optional-parameters"></a>Più parametri facoltativi  
 Per una procedura con più di un parametro facoltativo, in genere sono necessarie più di due versioni di overload. Se, ad esempio, sono presenti due parametri facoltativi e il codice chiamante può fornire o omettere ognuno di essi indipendentemente dall'altro, sono necessarie quattro versioni di overload, una per ogni possibile combinazione di argomenti forniti.  
  
 Con l'aumentare del numero di parametri facoltativi, aumenta la complessità dell'overload. A meno che non siano accettate alcune combinazioni di argomenti forniti, per N parametri facoltativi sono necessarie 2 ^ N versioni di overload. A seconda della natura della procedura, è possibile che la chiarezza della logica giustifichi il lavoro aggiuntivo di definizione di tutte le versioni di overload.  
  
#### <a name="to-overload-a-procedure-that-takes-more-than-one-optional-parameter"></a>Per eseguire l'overload di una routine che accetta più di un parametro facoltativo  
  
1. Determinare quali combinazioni di argomenti facoltativi forniti sono accettabili per la logica della routine. Una combinazione inaccettabile potrebbe verificarsi se un parametro facoltativo dipende da un altro. Se, ad esempio, un parametro accetta il nome di una persona e un altro accetta l'età della persona, una combinazione di argomenti che forniscono la validità, ma omettendo il nome non è accettabile.  
  
2. Per ogni combinazione accettabile di argomenti facoltativi specificati, scrivere un'istruzione `Sub` o `Function` dichiarazione che definisce l'elenco di parametri corrispondente. Non usare la parola chiave `Optional`.  
  
3. In ogni dichiarazione precedere la parola chiave `Sub` o `Function` con la parola chiave [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) .  
  
4. Dopo ogni dichiarazione, scrivere il codice della procedura da eseguire quando il codice chiamante fornisce un elenco di argomenti corrispondente all'elenco di parametri della dichiarazione.  
  
5. Terminare ogni procedura con l'istruzione `End Sub` o `End Function` in base alle esigenze.  
  
## <a name="see-also"></a>Vedere anche

- [Routine](./index.md)
- [Parametri e argomenti delle routine](./procedure-parameters-and-arguments.md)
- [Parametri facoltativi](./optional-parameters.md)
- [Matrici di parametri](./parameter-arrays.md)
- [Overload della routine](./procedure-overloading.md)
- [Risoluzione dei problemi relativi alle routine](./troubleshooting-procedures.md)
- [Procedura: Definire più versioni di una routine](./how-to-define-multiple-versions-of-a-procedure.md)
- [Procedura: Chiamare una routine di overload](./how-to-call-an-overloaded-procedure.md)
- [Procedura: Eseguire l'overload di una routine che accetta un numero indefinito di parametri](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [Risoluzione dell'overload](./overload-resolution.md)
