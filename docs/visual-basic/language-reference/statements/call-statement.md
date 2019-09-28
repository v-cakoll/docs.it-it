---
title: Istruzione Call (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Call
helpviewer_keywords:
- procedures [Visual Basic], Call statement
- Call statement [Visual Basic]
- procedures [Visual Basic], calling
ms.assetid: e5b31571-6867-406f-b8e7-a3f9aae4723a
ms.openlocfilehash: af0b62d6cfacbcf94f527e049e07e51bf496a6cf
ms.sourcegitcommit: da2dd2772fcf32b44eb18b1cbe8affd17b1753c9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2019
ms.locfileid: "71392755"
---
# <a name="call-statement-visual-basic"></a>Istruzione Call (Visual Basic)

Trasferisce il controllo a una procedura di libreria a collegamento dinamico (DLL) `Function`, `Sub` o.

## <a name="syntax"></a>Sintassi

```vb
[ Call ] procedureName [ (argumentList) ]
```

## <a name="parts"></a>Parti

|||
|---|---|
|`procedureName`|Obbligatorio. Nome della procedura da chiamare.|
|`argumentList`|facoltativo. Elenco di variabili o espressioni che rappresentano gli argomenti passati alla routine quando viene chiamato. Più argomenti sono separati da virgole. Se si include `argumentList`, è necessario racchiuderlo tra parentesi.|
|||
  
## <a name="remarks"></a>Note

 È possibile utilizzare la parola chiave `Call` quando si chiama una routine. Per la maggior parte delle chiamate di procedura, non è necessario usare questa parola chiave.

 In genere si usa la parola chiave `Call` quando l'espressione chiamata non inizia con un identificatore. Non è consigliabile usare la parola chiave `Call` per altri usi.

 Se la procedura restituisce un valore, l'istruzione `Call` lo ignora.

## <a name="example"></a>Esempio

 Nel codice seguente vengono illustrati due esempi in cui la parola chiave `Call` è necessaria per chiamare una routine. In entrambi gli esempi, l'espressione chiamata non inizia con un identificatore.

 [!code-vb[VbVbalrStatements#97](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#97)]  
  
## <a name="see-also"></a>Vedere anche

- [Istruzione Function](function-statement.md)
- [Istruzione Sub](sub-statement.md)
- [Istruzione Declare](declare-statement.md)
- [Espressioni lambda](../../programming-guide/language-features/procedures/lambda-expressions.md)
