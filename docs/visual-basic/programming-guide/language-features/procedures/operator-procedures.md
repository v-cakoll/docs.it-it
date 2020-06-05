---
title: Routine di operatore
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], operator
- Visual Basic code, operators
- syntax [Visual Basic], Operator procedures
- operators [Visual Basic], overloading
- overloaded operators [Visual Basic]
- operator overloading
- operator procedures
ms.assetid: 8c513d38-246b-4fb7-8b75-29e1364e555b
ms.openlocfilehash: a1dd183570c8aa50efff85bdaebef90bd3b0120f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84364318"
---
# <a name="operator-procedures-visual-basic"></a>Routine di operatore (Visual Basic)

Una routine di operatore è una serie di istruzioni Visual Basic che definiscono il comportamento di un operatore standard, ad esempio `*` , `<>` o, `And` su una classe o una struttura definita. Viene anche chiamato *Overload degli operatori*.

## <a name="when-to-define-operator-procedures"></a>Quando definire le routine degli operatori

Una volta definita una classe o una struttura, è possibile dichiarare le variabili in modo che siano del tipo della classe o della struttura. A volte tale variabile deve partecipare a un'operazione come parte di un'espressione. A tale scopo, deve essere un operando di un operatore.

Visual Basic definisce gli operatori solo sui relativi tipi di dati fondamentali. È possibile definire il comportamento di un operatore quando uno o entrambi gli operandi sono del tipo della classe o della struttura.

Per ulteriori informazioni, vedere [istruzione Operator](../../../language-reference/statements/operator-statement.md).

## <a name="types-of-operator-procedure"></a>Tipi di routine operatore

Una routine di operatore può essere uno dei tipi seguenti:

- Definizione di un operatore unario in cui l'argomento è del tipo della classe o della struttura.

- Definizione di un operatore binario in cui almeno uno degli argomenti è del tipo della classe o della struttura.

- Definizione di un operatore di conversione in cui l'argomento è del tipo della classe o della struttura.

- Definizione di un operatore di conversione che restituisce il tipo della classe o della struttura.

 Gli operatori di conversione sono sempre unari e si utilizza sempre `CType` come operatore che si sta definendo.

## <a name="declaration-syntax"></a>Sintassi di dichiarazione

La sintassi per la dichiarazione di una routine di operatore è la seguente:

```vb
Public Shared [Widening | Narrowing] Operator operatorsymbol ( operand1 [,  operand2 ]) As datatype

' Statements of the operator procedure.

End Operator
```

Usare la `Widening` `Narrowing` parola chiave o solo in un operatore di conversione di tipi. Il simbolo dell'operatore è sempre la [funzione CType](../../../language-reference/functions/ctype-function.md) per un operatore di conversione di tipi.

Si dichiarano due operandi per definire un operatore binario e si dichiara un operando per definire un operatore unario, incluso un operatore di conversione del tipo. Tutti gli operandi devono essere dichiarati `ByVal` .

Dichiarare ogni operando nello stesso modo in cui si dichiarano i parametri per le [sottoprocedure](./sub-procedures.md).

### <a name="data-type"></a>Tipo di dati

Poiché si definisce un operatore in una classe o una struttura definita, almeno uno degli operandi deve essere del tipo di dati della classe o della struttura. Per un operatore di conversione di tipi, l'operando o il tipo restituito deve essere del tipo di dati della classe o della struttura.

Per ulteriori informazioni, vedere [istruzione Operator](../../../language-reference/statements/operator-statement.md).

## <a name="calling-syntax"></a>Sintassi di chiamata

Una routine di operatore viene richiamata in modo implicito tramite il simbolo dell'operatore in un'espressione. Gli operandi vengono forniti esattamente come per gli operatori predefiniti.

La sintassi per una chiamata implicita a una routine di operatore è la seguente:

`Dim testStruct As`  *nomestruttura*

`Dim testNewStruct As`  *strutturaname* `= testStruct` *simbolooperatore*      `10`

### <a name="illustration-of-declaration-and-call"></a>Illustrazione della dichiarazione e della chiamata

Nella struttura seguente viene archiviato un valore intero con segno a 128 bit come parte di ordine superiore e di ordine inferiore costituente. Definisce l' `+` operatore per aggiungere due `veryLong` valori e generare un valore risultante `veryLong` .

[!code-vb[VbVbcnProcedures#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#23)]

Nell'esempio seguente viene illustrata una tipica chiamata all' `+` operatore definito in `veryLong` .

[!code-vb[VbVbcnProcedures#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#24)]

## <a name="see-also"></a>Vedere anche

- [Procedure](./index.md)
- [Routine Sub](./sub-procedures.md)
- [Routine Function](./function-procedures.md)
- [Routine Property](./property-procedures.md)
- [Parametri e argomenti delle routine](./procedure-parameters-and-arguments.md)
- [Operator Statement](../../../language-reference/statements/operator-statement.md)
- [Procedura: definire un operatore](./how-to-define-an-operator.md)
- [Procedura: Definire un operatore di conversione](./how-to-define-a-conversion-operator.md)
- [Procedura: chiamare una routine di operatore](./how-to-call-an-operator-procedure.md)
- [Procedura: utilizzare una classe che definisce gli operatori](./how-to-use-a-class-that-defines-operators.md)
