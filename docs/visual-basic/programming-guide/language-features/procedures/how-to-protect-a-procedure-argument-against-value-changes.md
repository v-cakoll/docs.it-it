---
title: 'Procedura: impedire la modifica del valore di un argomento di una routine'
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
ms.openlocfilehash: b0504d9f7a8862274d5d71dc6a9c1570551629a5
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84414363"
---
# <a name="how-to-protect-a-procedure-argument-against-value-changes-visual-basic"></a>Procedura: impedire la modifica del valore di un argomento di una routine (Visual Basic)
Se una routine dichiara un parametro come [ByRef](../../../language-reference/modifiers/byref.md), Visual Basic assegna al codice della procedura un riferimento diretto all'elemento di programmazione sottostante all'argomento nel codice chiamante. Ciò consente alla routine di modificare il valore sottostante all'argomento nel codice chiamante. In alcuni casi il codice chiamante potrebbe voler proteggersi da una modifica di questo tipo.  
  
 È sempre possibile proteggere un argomento dalla modifica dichiarando il parametro [ByVal](../../../language-reference/modifiers/byval.md) corrispondente nella procedura. Se si desidera essere in grado di modificare un argomento specifico in alcuni casi ma non in altri, è possibile dichiararlo `ByRef` e lasciare che il codice chiamante determini il meccanismo di passaggio in ogni chiamata. A tale scopo, racchiudere l'argomento corrispondente tra parentesi per passarlo per valore o non racchiuderlo tra parentesi per passarlo per riferimento. Per altre informazioni, vedere [procedura: forzare il passaggio di un argomento per valore](./how-to-force-an-argument-to-be-passed-by-value.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente vengono illustrate due procedure che accettano una variabile di matrice e operano sui relativi elementi. La `increase` procedura aggiunge semplicemente una a ogni elemento. La `replace` procedura assegna una nuova matrice al parametro `a()` e quindi ne aggiunge una a ogni elemento. Tuttavia, la riassegnazione non influisce sulla variabile di matrice sottostante nel codice chiamante.  
  
 [!code-vb[VbVbcnProcedures#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#35)]  
  
 [!code-vb[VbVbcnProcedures#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#38)]  
  
 [!code-vb[VbVbcnProcedures#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#37)]  
  
 La prima `MsgBox` chiamata Visualizza "After increase (n): 11, 21, 31, 41". Poiché la matrice `n` è un tipo di riferimento, `increase` può modificare i relativi membri, anche se il meccanismo di passaggio è `ByVal` .  
  
 La seconda `MsgBox` chiamata Visualizza "dopo Replace (n): 11, 21, 31, 41". Poiché `n` viene passato `ByVal` , `replace` non può modificare la variabile `n` nel codice chiamante assegnando una nuova matrice. Quando `replace` Crea la nuova istanza della matrice `k` e la assegna alla variabile locale `a` , perde il riferimento a `n` passato dal codice chiamante. Quando modifica i membri di `a` , solo la matrice locale `k` è interessata. Pertanto, `replace` non incrementa i valori della matrice `n` nel codice chiamante.  
  
## <a name="compile-the-code"></a>Compilare il codice  
 Il valore predefinito in Visual Basic consiste nel passare gli argomenti per valore. Tuttavia, è consigliabile includere la parola chiave [ByVal](../../../language-reference/modifiers/byval.md) o [ByRef](../../../language-reference/modifiers/byref.md) con tutti i parametri dichiarati. Questo rende il codice più facile da leggere.  
  
## <a name="see-also"></a>Vedere anche

- [Procedure](./index.md)
- [Parametri e argomenti delle routine](./procedure-parameters-and-arguments.md)
- [Procedura: passare argomenti a una routine](./how-to-pass-arguments-to-a-procedure.md)
- [Passaggio di argomenti per valore e per riferimento](./passing-arguments-by-value-and-by-reference.md)
- [Differenze tra argomenti modificabili e non modificabili](./differences-between-modifiable-and-nonmodifiable-arguments.md)
- [Differenze tra il passaggio di un argomento per valore e per riferimento](./differences-between-passing-an-argument-by-value-and-by-reference.md)
- [Procedura: cambiare il valore di un argomento di routine](./how-to-change-the-value-of-a-procedure-argument.md)
- [Procedura: forzare il passaggio di un argomento per valore](./how-to-force-an-argument-to-be-passed-by-value.md)
- [Passaggio di argomenti in base alla posizione e al nome](./passing-arguments-by-position-and-by-name.md)
- [Value Types and Reference Types](../data-types/value-types-and-reference-types.md)
