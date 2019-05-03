---
title: 'Procedura: Proteggere un argomento di routine modifica del valore (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], arguments
- procedures [Visual Basic], parameters
- procedure arguments
- arguments [Visual Basic], passing by reference
- Visual Basic code, procedures
- arguments [Visual Basic], ByVal
- arguments [Visual Basic], passing by value
- procedure parameters
- procedures [Visual Basic], calling
- arguments [Visual Basic], ByRef
- arguments [Visual Basic], changing value
ms.assetid: d2b7c766-ce16-4d2c-8d79-3fc0e7ba2227
ms.openlocfilehash: 70378b57c6d3af5a98e0ba9c6e3aebc319561b1b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61665741"
---
# <a name="how-to-protect-a-procedure-argument-against-value-changes-visual-basic"></a>Procedura: Proteggere un argomento di routine modifica del valore (Visual Basic)
Se una procedura dichiara un parametro come [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), Visual Basic fornisce il codice della routine un riferimento diretto all'elemento di programmazione sottostante all'argomento nel codice chiamante. In questo modo la procedura per modificare il valore sottostante all'argomento nel codice chiamante. In alcuni casi il codice chiamante può essere per proteggersi da tali modifiche.  
  
 È possibile proteggere sempre un argomento da modifica dichiarando il parametro corrispondente [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) nella procedura. Se si desidera essere in grado di modificare un determinato argomento in alcuni casi, ma non altri, è possibile dichiararla `ByRef` e consentire al codice chiamante di determinare il meccanismo di passaggio in ogni chiamata. Ciò avviene tramite l'argomento corrispondente di inclusione tra parentesi per passarlo come valore, o non racchiudendolo tra parentesi per passarlo per riferimento. Per altre informazioni, vedere [Procedura: Forzare un argomento da passare per valore](./how-to-force-an-argument-to-be-passed-by-value.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente illustra due procedure che accettano una variabile di matrice e operano sui relativi elementi. Il `increase` procedure aggiunge semplicemente uno per ogni elemento. Il `replace` procedure assegna una nuova matrice al parametro `a()` , quindi aggiunge uno per ogni elemento. Tuttavia, la riassegnazione non influenza la variabile di matrice sottostante nel codice chiamante.  
  
 [!code-vb[VbVbcnProcedures#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#35)]  
  
 [!code-vb[VbVbcnProcedures#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#38)]  
  
 [!code-vb[VbVbcnProcedures#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#37)]  
  
 Il primo `MsgBox` chiamata viene visualizzato "dopo aver Increase (n): 11, 21, 31, 41". Perché la matrice `n` è un tipo di riferimento `increase` possono modificare i relativi membri, anche se è il meccanismo di passaggio `ByVal`.  
  
 Il secondo `MsgBox` chiamata viene visualizzato "dopo Replace (n): 11, 21, 31, 41". In quanto `n` viene passato `ByVal`, `replace` non è possibile modificare la variabile `n` nel codice chiamante tramite l'assegnazione di una nuova matrice a esso. Quando `replace` crea la nuova istanza della matrice `k` e la assegna alla variabile locale `a`, perde il riferimento a `n` passato dal codice chiamante. Quando si trasforma i membri del `a`, solo la matrice locale `k` è interessato. Pertanto `replace` incrementa i valori della matrice `n` nel codice chiamante.  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'impostazione predefinita in Visual Basic consiste nel passare argomenti per valore. Tuttavia, è buona norma includere il [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) oppure [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) parola chiave with ogni parametro dichiarato. Questo rende il codice più facile da leggere.  
  
## <a name="see-also"></a>Vedere anche

- [Routine](./index.md)
- [Parametri e argomenti delle routine](./procedure-parameters-and-arguments.md)
- [Procedura: Passare argomenti a una routine](./how-to-pass-arguments-to-a-procedure.md)
- [Passaggio di argomenti per valore e per riferimento](./passing-arguments-by-value-and-by-reference.md)
- [Differenze tra argomenti modificabili e non modificabili](./differences-between-modifiable-and-nonmodifiable-arguments.md)
- [Differenze tra il passaggio di un argomento per valore e per riferimento](./differences-between-passing-an-argument-by-value-and-by-reference.md)
- [Procedura: Modificare il valore di un argomento di routine](./how-to-change-the-value-of-a-procedure-argument.md)
- [Procedura: Forzare un argomento da passare per valore](./how-to-force-an-argument-to-be-passed-by-value.md)
- [Passaggio di argomenti in base alla posizione e al nome](./passing-arguments-by-position-and-by-name.md)
- [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
