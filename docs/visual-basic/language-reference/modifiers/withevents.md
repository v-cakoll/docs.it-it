---
title: WithEvents (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.WithEvents
- WithEvents
helpviewer_keywords:
- WithEvents keyword [Visual Basic]
ms.assetid: 19d461f5-d72f-4de9-8c1d-0a6650316990
ms.openlocfilehash: 50d5a768393e90d28d150b451405e35e6f4c7953
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2019
ms.locfileid: "72583033"
---
# <a name="withevents-visual-basic"></a>WithEvents (Visual Basic)
Specifica che una o più variabili membro dichiarate fanno riferimento a un'istanza di una classe che può generare eventi.

## <a name="remarks"></a>Note

Quando una variabile viene definita utilizzando `WithEvents`, è possibile specificare in modo dichiarativo che un metodo gestisce gli eventi della variabile utilizzando la parola chiave `Handles`.

È possibile usare `WithEvents` solo a livello di classe o di modulo. Ciò significa che il contesto di dichiarazione per una variabile di `WithEvents` deve essere una classe o un modulo e non può essere un file di origine, uno spazio dei nomi, una struttura o una procedura.

Non è possibile usare `WithEvents` per un membro di struttura.

È possibile dichiarare solo singole variabili, non matrici, con `WithEvents`.

## <a name="rules"></a>Regole

**Tipi di elemento.** È necessario dichiarare le variabili di `WithEvents` come variabili oggetto in modo che possano accettare istanze di classe. Non è tuttavia possibile dichiararli come `Object`. È necessario dichiararli come la classe specifica che può generare gli eventi.

Il modificatore `WithEvents` può essere usato in questo contesto: [istruzione Dim](../../../visual-basic/language-reference/statements/dim-statement.md)

## <a name="example"></a>Esempio

```vb
Dim WithEvents app As Application
```

## <a name="see-also"></a>Vedere anche

- [Handles](../../../visual-basic/language-reference/statements/handles-clause.md)
- [Parole chiave](../../../visual-basic/language-reference/keywords/index.md)
- [Eventi](../../../visual-basic/programming-guide/language-features/events/index.md)
