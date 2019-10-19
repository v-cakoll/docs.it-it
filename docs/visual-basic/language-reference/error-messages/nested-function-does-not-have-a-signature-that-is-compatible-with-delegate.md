---
title: La funzione annidata non dispone di una firma compatibile con il delegato '<delegatename>'
ms.date: 07/20/2015
f1_keywords:
- vbc36532
- bc36532
helpviewer_keywords:
- BC36532
ms.assetid: 493f292c-d81e-40ef-8b47-61f020571829
ms.openlocfilehash: d65c8eab661675c955ff6562098248c04036d6e7
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2019
ms.locfileid: "72580642"
---
# <a name="nested-function-does-not-have-a-signature-that-is-compatible-with-delegate-delegatename"></a>La funzione annidata non dispone di una firma compatibile con il delegato ' \<delegatename >'

Un'espressione lambda è stata assegnata a un delegato con una firma incompatibile. Nel codice seguente, ad esempio, Delegate `Del` dispone di due parametri Integer.

```vb
Delegate Function Del(ByVal p As Integer, ByVal q As Integer) As Integer
```

L'errore viene generato se un'espressione lambda con un argomento viene dichiarata come tipo `Del`:

```vb
' Neither of these is valid.
' Dim lambda1 As Del = Function(n As Integer) n + 1
' Dim lambda2 As Del = Function(n) n + 1
```

**ID errore:** BC36532

## <a name="to-correct-this-error"></a>Per correggere l'errore

Modificare la definizione del delegato o l'espressione lambda assegnata in modo che le firme siano compatibili.

## <a name="see-also"></a>Vedere anche

- [Conversione di tipo relaxed del delegato](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
- [Espressioni lambda](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
