---
title: WithEvents
ms.date: 07/20/2015
f1_keywords:
- vb.WithEvents
- WithEvents
helpviewer_keywords:
- WithEvents keyword [Visual Basic]
ms.assetid: 19d461f5-d72f-4de9-8c1d-0a6650316990
ms.openlocfilehash: 48261e27de302c1809c9725e6e2fc0705a803930
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84386776"
---
# <a name="withevents-visual-basic"></a>WithEvents (Visual Basic)
Specifica che una o più variabili membro dichiarate fanno riferimento a un'istanza di una classe che può generare eventi.

## <a name="remarks"></a>Commenti

Quando una variabile viene definita tramite `WithEvents` , è possibile specificare in modo dichiarativo che un metodo gestisce gli eventi della variabile utilizzando la `Handles` parola chiave.

È possibile usare `WithEvents` solo a livello di classe o di modulo. Ciò significa che il contesto di dichiarazione per una `WithEvents` variabile deve essere una classe o un modulo e non può essere un file di origine, uno spazio dei nomi, una struttura o una procedura.

Non è possibile usare `WithEvents` in un membro di struttura.

È possibile dichiarare solo singole variabili, non matrici, con `WithEvents` .

## <a name="rules"></a>Regole

**Tipi di elemento.** È necessario dichiarare le `WithEvents` variabili come variabili oggetto in modo che possano accettare istanze di classe. Tuttavia, non è possibile dichiararli come `Object` . È necessario dichiararli come la classe specifica che può generare gli eventi.

Il `WithEvents` modificatore può essere usato in questo contesto: [istruzione Dim](../statements/dim-statement.md)

## <a name="example"></a>Esempio

```vb
Dim WithEvents app As Application
```

## <a name="see-also"></a>Vedere anche

- [Selettori](../statements/handles-clause.md)
- [Parole chiave](../keywords/index.md)
- [Events](../../programming-guide/language-features/events/index.md)
