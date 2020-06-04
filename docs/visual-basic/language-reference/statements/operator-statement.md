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
ms.openlocfilehash: f9e6ffe5a49715592399321ab471d73826e05d8e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404395"
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
Facoltativa. Vedere [elenco attributi](attribute-list.md).

`Public`  
Obbligatorio. Indica che questa routine dell'operatore dispone di accesso [pubblico](../modifiers/public.md) .

`Overloads`  
Facoltativa. Vedere [Overload](../modifiers/overloads.md).

`Shared`  
Obbligatorio. Indica che questa routine dell'operatore è una procedura [condivisa](../modifiers/shared.md) .

`Shadows`  
Facoltativa. Vedere [Shadows](../modifiers/shadows.md).

`Widening`  
Obbligatorio per un operatore di conversione, a meno che non si specifichi `Narrowing` . Indica che questa routine dell'operatore definisce una conversione verso un tipo di contenuto più [ampio](../modifiers/widening.md) . Vedere "conversioni verso un tipo di ampliamento e riduzione" in questa pagina della guida.

`Narrowing`  
Obbligatorio per un operatore di conversione, a meno che non si specifichi `Widening` . Indica che questa routine dell'operatore definisce una conversione verso un tipo di caratteri più [piccolo](../modifiers/narrowing.md) . Vedere "conversioni verso un tipo di ampliamento e riduzione" in questa pagina della guida.

`operatorsymbol`  
Obbligatorio. Simbolo o identificatore dell'operatore definito da questa routine di operatore.

`operand1`  
Obbligatorio. Il nome e il tipo del singolo operando di un operatore unario (incluso un operatore di conversione) o l'operando sinistro di un operatore binario.

`operand2`  
Obbligatorio per gli operatori binari. Nome e tipo dell'operando di destra di un operatore binario.

`operand1`e `operand2` presentano la sintassi e le parti seguenti:

`[ ByVal ] operandname [ As operandtype ]`

|Parte|Descrizione|
|----------|-----------------|
|`ByVal`|Facoltativo, ma il meccanismo di passaggio deve essere [ByVal](../modifiers/byval.md).|
|`operandname`|Obbligatorio. Nome della variabile che rappresenta questo operando. Vedere [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).|
|`operandtype`|Facoltativo a meno che non `Option Strict` sia `On` . Tipo di dati dell'operando.|

`type`  
Facoltativo a meno che non `Option Strict` sia `On` . Tipo di dati del valore restituito dalla routine dell'operatore.

`statements`  
Facoltativa. Blocco di istruzioni eseguite dalla stored procedure.

`returnvalue`  
Obbligatorio. Valore restituito dalla routine Operator al codice chiamante.

`End` `Operator`  
Obbligatorio. Termina la definizione di questa routine di operatore.

## <a name="remarks"></a>Commenti

È possibile utilizzare `Operator` solo in una classe o una struttura. Ciò significa che il *contesto di dichiarazione* per un operatore non può essere un file di origine, uno spazio dei nomi, un modulo, un'interfaccia, una routine o un blocco. Per altre informazioni, vedere [Contesti delle dichiarazioni e livelli di accesso predefiniti](declaration-contexts-and-default-access-levels.md).

Tutti gli operatori devono essere `Public Shared` . Non è possibile specificare `ByRef` , `Optional` o `ParamArray` per uno degli operandi.

Non è possibile usare il simbolo dell'operatore o l'identificatore per mantenere un valore restituito. È necessario utilizzare l' `Return` istruzione ed è necessario specificare un valore. Qualsiasi numero di `Return` istruzioni può comparire in qualsiasi punto della procedura.

La definizione di un operatore in questo modo viene chiamata *Overload degli operatori*, indipendentemente dal fatto che si usi la `Overloads` parola chiave. La tabella seguente elenca gli operatori che è possibile definire.

|Type|Operatori|
|----------|---------------|
|Unaria|`+`, `-`, `IsFalse`, `IsTrue`, `Not`|
|Binario|`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`|
|Conversione (unario)|`CType`|

Si noti che l'operatore `=` nell'elenco binario è l'operatore di confronto, non l'operatore di assegnazione.

Quando si definisce `CType` , è necessario specificare `Widening` o `Narrowing` .

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

- Se si definiscono gli `IsTrue` `IsFalse` operatori e, devono entrambi restituire il `Boolean` tipo.

- Se si definiscono gli `<<` `>>` operatori e, devono entrambi specificare il `Integer` tipo per l'oggetto `operandtype` di `operand2` .

Il tipo restituito non deve corrispondere al tipo di uno degli operandi. Un operatore di confronto, ad esempio, `=` `<>` può essere restituito `Boolean` anche se nessuno degli operandi è `Boolean` .

## <a name="logical-and-bitwise-operators"></a>Operatori logici e bit per bit

Gli `And` `Or` operatori,, `Not` e `Xor` possono eseguire operazioni logiche o bit per bit in Visual Basic. Tuttavia, se si definisce uno di questi operatori in una classe o una struttura, è possibile definire solo l'operazione bit per bit.

Non è possibile definire l' `AndAlso` operatore direttamente con un' `Operator` istruzione. Tuttavia, è possibile usare `AndAlso` se sono state soddisfatte le condizioni seguenti:

- È stato definito lo `And` stesso tipo di operando che si desidera utilizzare per `AndAlso` .

- La definizione di `And` restituisce lo stesso tipo della classe o della struttura in cui è stato definito.

- È stato definito l' `IsFalse` operatore sulla classe o sulla struttura in cui è stato definito `And` .

Analogamente, è possibile usare `OrElse` se è stato definito `Or` negli stessi operandi, con il tipo restituito della classe o della struttura, ed è stato definito `IsTrue` sulla classe o sulla struttura.

## <a name="widening-and-narrowing-conversions"></a>Widening and Narrowing Conversions

Una *conversione* verso un tipo di caratteri più ampio viene sempre eseguita in fase di esecuzione, mentre una conversione verso un tipo di caratteri più *piccolo* può avere esito negativo Per altre informazioni, vedere [Widening and Narrowing Conversions](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).

Se si dichiara una procedura di conversione `Widening` , il codice della procedura non deve generare errori. Ciò comporta quanto segue:

- Deve sempre restituire un valore valido di tipo `type` .

- Deve gestire tutte le possibili eccezioni e altre condizioni di errore.

- Deve gestire eventuali ritorni degli errori da qualsiasi routine chiamata.

Se è possibile che una procedura di conversione potrebbe non riuscire o che potrebbe causare un'eccezione non gestita, è necessario dichiararla come `Narrowing` .

## <a name="example"></a>Esempio

Nell'esempio di codice seguente viene utilizzata l' `Operator` istruzione per definire il contorno di una struttura che include routine di operatore per gli `And` operatori, `Or` , `IsFalse` e `IsTrue` . `And`e `Or` accettano due operandi di tipo `abc` e tipo restituito `abc` . `IsFalse`e `IsTrue` accettano un solo operando di tipo `abc` e restituiscono `Boolean` . Queste definizioni consentono al codice chiamante di usare `And` , `AndAlso` , `Or` e `OrElse` con operandi di tipo `abc` .

[!code-vb[VbVbalrStatements#44](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#44)]

## <a name="see-also"></a>Vedere anche

- [Operatore IsFalse](../operators/isfalse-operator.md)
- [Operatore IsTrue](../operators/istrue-operator.md)
- [Widening](../modifiers/widening.md)
- [Narrowing](../modifiers/narrowing.md)
- [Widening and Narrowing Conversions](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [Routine di operatore](../../programming-guide/language-features/procedures/operator-procedures.md)
- [Procedura: definire un operatore](../../programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [Procedura: Definire un operatore di conversione](../../programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
- [Procedura: chiamare una routine di operatore](../../programming-guide/language-features/procedures/how-to-call-an-operator-procedure.md)
- [Procedura: utilizzare una classe che definisce gli operatori](../../programming-guide/language-features/procedures/how-to-use-a-class-that-defines-operators.md)
