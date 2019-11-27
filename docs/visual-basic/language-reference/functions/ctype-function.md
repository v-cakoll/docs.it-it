---
title: CType Function
ms.date: 07/20/2015
f1_keywords:
- vb.CType
helpviewer_keywords:
- expression conversion results
- explicit data type conversions [Visual Basic]
- CType function
- conversions [Visual Basic], expression
ms.assetid: dd4b29e7-6fa1-428c-877e-69955420bb72
ms.openlocfilehash: 18b2d5a28cd6ef885ba8d237da6764dbbd108b59
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348092"
---
# <a name="ctype-function-visual-basic"></a>Funzione CType (Visual Basic)

Restituisce il risultato della conversione esplicita di un'espressione in un tipo di dati, oggetto, struttura, classe o interfaccia specificati.

## <a name="syntax"></a>Sintassi

```vb
CType(expression, typename)
```

## <a name="parts"></a>Parti

`expression` qualsiasi espressione valida. Se il valore di `expression` non è compreso nell'intervallo consentito da `typename`, Visual Basic genera un'eccezione.

`typename` qualsiasi espressione valida all'interno di una clausola `As` in un'istruzione `Dim`, ovvero il nome di qualsiasi tipo di dati, oggetto, struttura, classe o interfaccia.

## <a name="remarks"></a>Note

> [!TIP]
> Per eseguire una conversione del tipo è inoltre possibile utilizzare le funzioni seguenti:
>
> - Funzioni di conversione dei tipi quali `CByte`, `CDbl`e `CInt` che eseguono una conversione in un tipo di dati specifico. Per altre informazioni, vedere [funzioni di conversione dei tipi](../../../visual-basic/language-reference/functions/type-conversion-functions.md).
> - Operatore [DirectCast](../../../visual-basic/language-reference/operators/directcast-operator.md) o [operatore TryCast](../../../visual-basic/language-reference/operators/trycast-operator.md). Questi operatori richiedono che un tipo erediti da o implementi l'altro tipo. Possono fornire prestazioni leggermente migliori rispetto a `CType` durante la conversione da e verso il tipo di dati `Object`.

`CType` viene compilata inline, il che significa che il codice di conversione fa parte del codice che valuta l'espressione. In alcuni casi, il codice viene eseguito più velocemente perché non viene chiamata alcuna routine per eseguire la conversione.

Se non viene definita alcuna conversione dal `expression` al `typename` (ad esempio, da `Integer` a `Date`), Visual Basic Visualizza un messaggio di errore in fase di compilazione.

Se una conversione non riesce in fase di esecuzione, viene generata l'eccezione appropriata. Se una conversione verso un tipo di ristringimento non riesce, un <xref:System.OverflowException> è il risultato più comune. Se la conversione non è definita, viene generata un'<xref:System.InvalidCastException>. Questo può verificarsi, ad esempio, se `expression` è di tipo `Object` e il tipo in fase di esecuzione non ha alcuna conversione in `typename`.

Se il tipo di dati di `expression` o `typename` è una classe o una struttura definita, è possibile definire `CType` in tale classe o struttura come operatore di conversione. In questo modo `CType` funge da *operatore di overload*. In tal caso, è possibile controllare il comportamento delle conversioni da e verso la classe o la struttura, incluse le eccezioni che possono essere generate.

## <a name="overloading"></a>Overload

È inoltre possibile eseguire l'overload dell'operatore `CType` su una classe o una struttura definita all'esterno del codice. Se il codice viene convertito in o da tale classe o struttura, assicurarsi di comprendere il comportamento dell'operatore `CType`. Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).

## <a name="converting-dynamic-objects"></a>Conversione di oggetti dinamici

Le conversioni di tipi di oggetti dinamici vengono eseguite da conversioni dinamiche definite dall'utente che utilizzano i metodi <xref:System.Dynamic.DynamicObject.TryConvert%2A> o <xref:System.Dynamic.DynamicMetaObject.BindConvert%2A>. Se si utilizzano oggetti dinamici, utilizzare il metodo <xref:Microsoft.VisualBasic.Conversion.CTypeDynamic%2A> per convertire l'oggetto dinamico.

## <a name="example"></a>Esempio

Nell'esempio seguente viene utilizzata la funzione `CType` per convertire un'espressione nel tipo di dati `Single`.

[!code-vb[VbVbalrFunctions#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#24)]

Per altri esempi, vedere [conversioni implicite ed esplicite](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md).

## <a name="see-also"></a>Vedere anche

- <xref:System.OverflowException>
- <xref:System.InvalidCastException>
- [CString](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Funzioni di conversione](../../../visual-basic/language-reference/functions/conversion-functions.md)
- [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md)
- [Procedura: Definire un operatore di conversione](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
- [Conversione di tipi in .NET Framework](../../../standard/base-types/type-conversion.md)
