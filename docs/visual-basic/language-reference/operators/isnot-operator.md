---
title: Operatore IsNot (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.isnot
helpviewer_keywords:
- IsNot operator [Visual Basic]
ms.assetid: 8dd2bcdb-0166-48a2-9094-60dfb448f36c
ms.openlocfilehash: 32e8f9532244679d2994b0e3d98279d75f7e77b4
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701042"
---
# <a name="isnot-operator-visual-basic"></a>Operatore IsNot (Visual Basic)

Confronta due variabili di riferimento a oggetti.

## <a name="syntax"></a>Sintassi

```vb
result = object1 IsNot object2
```

## <a name="parts"></a>Parti
 `result` Obbligatorio. Valore `Boolean`.

 `object1` Obbligatorio. Qualsiasi variabile o espressione `Object`.

 `object2` Obbligatorio. Qualsiasi variabile o espressione `Object`.

## <a name="remarks"></a>Note
 L'operatore `IsNot` determina se due riferimenti a oggetti si riferiscono a oggetti diversi. Tuttavia, non esegue confronti di valori. Se `object1` e `object2` fanno entrambi riferimento alla stessa istanza dell'oggetto, `result` è `False`. in caso contrario, `result` è `True`.

 `IsNot` è il contrario dell'operatore `Is`. Il vantaggio di `IsNot` è che è possibile evitare la sintassi scomoda con `Not` e `Is`, che può essere difficile da leggere.

 È possibile utilizzare gli operatori `Is` e `IsNot` per testare gli oggetti ad associazione anticipata e ad associazione tardiva.

## <a name="example"></a>Esempio
 Nell'esempio di codice seguente vengono usati sia l'operatore `Is` che l'operatore `IsNot` per eseguire lo stesso confronto.

 [!code-vb[VbVbalrOperators#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#29)]

## <a name="see-also"></a>Vedere anche

- [Operatore Is](is-operator.md)
- [Operatore TypeOf](typeof-operator.md)
- [Precedenza tra gli operatori in Visual Basic](operator-precedence.md)
- [Procedura: Verificare se due oggetti sono uguali @ no__t-0
