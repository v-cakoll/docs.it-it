---
title: Operatore IsNot
ms.date: 07/20/2015
f1_keywords:
- vb.isnot
helpviewer_keywords:
- IsNot operator [Visual Basic]
ms.assetid: 8dd2bcdb-0166-48a2-9094-60dfb448f36c
ms.openlocfilehash: 616506f64d20e1f150b443433f1b69040136a5ba
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74336068"
---
# <a name="isnot-operator-visual-basic"></a>Operatore IsNot (Visual Basic)

Confronta due variabili di riferimento a oggetti.

## <a name="syntax"></a>Sintassi

```vb
result = object1 IsNot object2
```

## <a name="parts"></a>Parti
 `result` Obbligatorio. Valore `Boolean`.

 `object1` Obbligatorio. Qualsiasi `Object` variabile o espressione.

 `object2` Obbligatorio. Qualsiasi `Object` variabile o espressione.

## <a name="remarks"></a>Osservazioni
 L'operatore `IsNot` determina se due riferimenti a oggetti si riferiscono a oggetti diversi. Tuttavia, non esegue confronti di valori. Se `object1` e `object2` entrambi fanno riferimento alla stessa istanza dell'oggetto, `result` è `False`; in caso contrario, `result` viene `True`.

 `IsNot` è l'opposto dell'operatore `Is`. Il vantaggio di `IsNot` è che è possibile evitare la sintassi scomoda con `Not` e `Is`, che può essere difficile da leggere.

 È possibile utilizzare gli operatori `Is` e `IsNot` per testare gli oggetti ad associazione anticipata e ad associazione tardiva.

## <a name="example"></a>Esempio
 Nell'esempio di codice seguente vengono usati sia l'operatore `Is` che l'operatore `IsNot` per eseguire lo stesso confronto.

 [!code-vb[VbVbalrOperators#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#29)]

## <a name="see-also"></a>Vedere anche

- [Operatore Is](is-operator.md)
- [Operatore TypeOf](typeof-operator.md)
- [Precedenza tra gli operatori in Visual Basic](operator-precedence.md)
- [Procedura: Determinare se due oggetti sono uguali](../../programming-guide/language-features/operators-and-expressions/how-to-test-whether-two-objects-are-the-same.md)
