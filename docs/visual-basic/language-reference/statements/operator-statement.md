---
title: Operator Statement
ms.date: 07/20/2015
f1_keywords:
- vb.operator
helpviewer_keywords:
- operators [Visual Basic]
- procedures [Visual Basic], operator
- Narrowing keyword [Visual Basic], conversion operators
- Visual Basic code, operators
- Widening keyword [Visual Basic], conversion operators
- syntax [Visual Basic], Operator procedures
- operators [Visual Basic], overloading
- overloaded operators [Visual Basic]
- operator overloading
- operator procedures
- Operator statement [Visual Basic]
- CType function [Visual Basic], Operator statement
ms.assetid: b12ec4af-1ad7-4a17-865b-c5ee96320ae5
ms.openlocfilehash: aa6ae3977977ded05e47d12dabe72f09251f262d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353803"
---
# <a name="operator-statement"></a>Operator Statement

Dichiara il simbolo dell'operatore, gli operandi e il codice che definiscono una routine di operatore in una classe o una struttura.

## <a name="syntax"></a>Sintassi

```vb
[ <attrlist> ] Public [ Overloads ] Shared [ Shadows ] [ Widening | Narrowing ]
Operator operatorsymbol ( operand1 [, operand2 ]) [ As [ <attrlist> ] type ]
    [ statements ]
    [ statements ]
    Return returnvalue
    [ statements ]
End Operator
```

## <a name="parts"></a>Parti

`attrlist`  
Parametro facoltativo. Vedere [elenco attributi](../../../visual-basic/language-reference/statements/attribute-list.md).

`Public`  
Obbligatorio. Indica che questa routine dell'operatore dispone di accesso [pubblico](../../../visual-basic/language-reference/modifiers/public.md) .

`Overloads`  
Parametro facoltativo. Vedere [Overload](../../../visual-basic/language-reference/modifiers/overloads.md).

`Shared`  
Obbligatorio. Indica che questa routine dell'operatore è una procedura [condivisa](../../../visual-basic/language-reference/modifiers/shared.md) .

`Shadows`  
Parametro facoltativo. Vedere [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).

`Widening`  
Obbligatorio per un operatore di conversione, a meno che non si specifichi `Narrowing`. Indica che questa routine dell'operatore definisce una conversione verso un tipo di contenuto più [ampio](../../../visual-basic/language-reference/modifiers/widening.md) . Vedere "conversioni verso un tipo di ampliamento e riduzione" in questa pagina della guida.

`Narrowing`  
Obbligatorio per un operatore di conversione, a meno che non si specifichi `Widening`. Indica che questa routine dell'operatore definisce una conversione verso un tipo di caratteri più [piccolo](../../../visual-basic/language-reference/modifiers/narrowing.md) . Vedere "conversioni verso un tipo di ampliamento e riduzione" in questa pagina della guida.

`operatorsymbol`  
Obbligatorio. Simbolo o identificatore dell'operatore definito da questa routine di operatore.

`operand1`  
Obbligatorio. Il nome e il tipo del singolo operando di un operatore unario (incluso un operatore di conversione) o l'operando sinistro di un operatore binario.

`operand2`  
Obbligatorio per gli operatori binari. Nome e tipo dell'operando di destra di un operatore binario.

`operand1` e `operand2` hanno la sintassi e le parti seguenti:

`[ ByVal ] operandname [ As operandtype ]`

|Parte|description|
|----------|-----------------|
|`ByVal`|Facoltativo, ma il meccanismo di passaggio deve essere [ByVal](../../../visual-basic/language-reference/modifiers/byval.md).|
|`operandname`|Obbligatorio. Nome della variabile che rappresenta questo operando. Vedere [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|
|`operandtype`|Facoltativo, a meno che non sia `On``Option Strict`. Tipo di dati dell'operando.|

`type`  
Facoltativo, a meno che non sia `On``Option Strict`. Tipo di dati del valore restituito dalla routine dell'operatore.

`statements`  
Parametro facoltativo. Blocco di istruzioni eseguite dalla stored procedure.

`returnvalue`  
Obbligatorio. Valore restituito dalla routine Operator al codice chiamante.

`End` `Operator`  
Obbligatorio. Termina la definizione di questa routine di operatore.

## <a name="remarks"></a>Osservazioni

È possibile utilizzare `Operator` solo in una classe o una struttura. Ciò significa che il *contesto di dichiarazione* per un operatore non può essere un file di origine, uno spazio dei nomi, un modulo, un'interfaccia, una routine o un blocco. Per altre informazioni, vedere [Contesti delle dichiarazioni e livelli di accesso predefiniti](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).

Tutti gli operatori devono essere `Public Shared`. Non è possibile specificare `ByRef`, `Optional`o `ParamArray` per uno degli operandi.

Non è possibile usare il simbolo dell'operatore o l'identificatore per mantenere un valore restituito. È necessario utilizzare l'istruzione `Return` ed è necessario specificare un valore. Qualsiasi numero di istruzioni `Return` può comparire in qualsiasi punto della procedura.

La definizione di un operatore in questo modo viene chiamata *Overload degli operatori*, indipendentemente dal fatto che si usi la parola chiave `Overloads`. La tabella seguente elenca gli operatori che è possibile definire.

|Digitare|Operatori|
|----------|---------------|
|Unario|`+`, `-`, `IsFalse`, `IsTrue`, `Not`|
|Binario|`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`|
|Conversione (unario)|`CType`|

Si noti che l'operatore `=` nell'elenco binario è l'operatore di confronto, non l'operatore di assegnazione.

Quando si definiscono `CType`, è necessario specificare `Widening` o `Narrowing`.

## <a name="matched-pairs"></a>Coppie corrispondenti

È necessario definire determinati operatori come coppie corrispondenti. Se si definisce uno degli operatori di tale coppia, è necessario definire anche l'altro. Le coppie corrispondenti sono le seguenti:

- `=` e `<>`

- `>` e `<`

- `>=` e `<=`

- `IsTrue` e `IsFalse`

## <a name="data-type-restrictions"></a>Restrizioni relative ai tipi di dati

Ogni operatore definito deve coinvolgere la classe o la struttura in cui viene definita. Ciò significa che la classe o la struttura deve essere visualizzata come tipo di dati degli elementi seguenti:

- Operando di un operatore unario.

- Almeno uno degli operandi di un operatore binario.

- L'operando o il tipo restituito di un operatore di conversione.

 Alcuni operatori hanno restrizioni aggiuntive per i tipi di dati, come indicato di seguito:

- Se si definiscono gli operatori `IsTrue` e `IsFalse`, devono entrambi restituire il tipo di `Boolean`.

- Se si definiscono gli operatori `<<` e `>>`, è necessario specificare il tipo di `Integer` per la `operandtype` di `operand2`.

Il tipo restituito non deve corrispondere al tipo di uno degli operandi. Un operatore di confronto, ad esempio `=` o `<>` può restituire `Boolean` anche se nessuno degli operandi è `Boolean`.

## <a name="logical-and-bitwise-operators"></a>Operatori logici e bit per bit

Gli operatori `And`, `Or`, `Not`e `Xor` possono eseguire operazioni logiche o bit per bit in Visual Basic. Tuttavia, se si definisce uno di questi operatori in una classe o una struttura, è possibile definire solo l'operazione bit per bit.

Non è possibile definire l'operatore `AndAlso` direttamente con un'istruzione `Operator`. Tuttavia, è possibile usare `AndAlso` se sono state soddisfatte le condizioni seguenti:

- È stato definito `And` per gli stessi tipi di operando che si desidera utilizzare per `AndAlso`.

- La definizione di `And` restituisce lo stesso tipo della classe o della struttura in cui è stata definita.

- È stato definito l'operatore `IsFalse` sulla classe o sulla struttura in cui è stato definito `And`.

Analogamente, è possibile utilizzare `OrElse` se è stato definito `Or` sugli stessi operandi, con il tipo restituito della classe o della struttura, ed è stato definito `IsTrue` sulla classe o sulla struttura.

## <a name="widening-and-narrowing-conversions"></a>Widening and Narrowing Conversions

Una *conversione* verso un tipo di caratteri più ampio viene sempre eseguita in fase di esecuzione, mentre una conversione verso un tipo di caratteri più *piccolo* può avere esito negativo Per altre informazioni, vedere [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).

Se si dichiara una procedura di conversione da `Widening`, il codice della procedura non deve generare errori. Ciò significa che:

- Deve restituire sempre un valore valido di tipo `type`.

- Deve gestire tutte le possibili eccezioni e altre condizioni di errore.

- Deve gestire eventuali ritorni degli errori da qualsiasi routine chiamata.

Se è possibile che una procedura di conversione potrebbe non riuscire o che potrebbe causare un'eccezione non gestita, è necessario dichiararla come `Narrowing`.

## <a name="example"></a>Esempio

Nell'esempio di codice seguente viene utilizzata l'istruzione `Operator` per definire il contorno di una struttura che include routine di operatore per gli operatori `And`, `Or`, `IsFalse`e `IsTrue`. `And` e `Or` accettano due operandi di tipo `abc` e il tipo restituito `abc`. `IsFalse` e `IsTrue` accettano un solo operando di tipo `abc` e restituiscono `Boolean`. Queste definizioni consentono al codice chiamante di utilizzare `And`, `AndAlso`, `Or`e `OrElse` con operandi di tipo `abc`.

[!code-vb[VbVbalrStatements#44](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#44)]

## <a name="see-also"></a>Vedere anche

- [Operatore IsFalse](../../../visual-basic/language-reference/operators/isfalse-operator.md)
- [Operatore IsTrue](../../../visual-basic/language-reference/operators/istrue-operator.md)
- [Widening](../../../visual-basic/language-reference/modifiers/widening.md)
- [Narrowing](../../../visual-basic/language-reference/modifiers/narrowing.md)
- [Conversioni di ampliamento e restrizione](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [Routine di operatore](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)
- [Procedura: Definire un operatore](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [Procedura: Definire un operatore di conversione](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
- [Procedura: Chiamare una routine di operatore](../../../visual-basic/programming-guide/language-features/procedures/how-to-call-an-operator-procedure.md)
- [Procedura: Usare una classe che definisce gli operatori](../../../visual-basic/programming-guide/language-features/procedures/how-to-use-a-class-that-defines-operators.md)
