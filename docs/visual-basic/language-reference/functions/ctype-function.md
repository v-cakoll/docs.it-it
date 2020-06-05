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
ms.openlocfilehash: 88d609146648fe1b0c3124b99a65e85293fc0707
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406430"
---
# <a name="ctype-function-visual-basic"></a>Funzione CType (Visual Basic)

Restituisce il risultato della conversione esplicita di un'espressione in un tipo di dati, oggetto, struttura, classe o interfaccia specificati.

## <a name="syntax"></a>Sintassi

```vb
CType(expression, typename)
```

## <a name="parts"></a>Parti

`expression`Qualsiasi espressione valida. Se il valore di non `expression` è compreso nell'intervallo consentito da `typename` , Visual Basic genera un'eccezione.

`typename`Qualsiasi espressione valida all'interno di una `As` clausola in un' `Dim` istruzione, ovvero il nome di qualsiasi tipo di dati, oggetto, struttura, classe o interfaccia.

## <a name="remarks"></a>Commenti

> [!TIP]
> Per eseguire una conversione del tipo è inoltre possibile utilizzare le funzioni seguenti:
>
> - Funzioni di conversione dei tipi `CByte` , ad esempio, `CDbl` e `CInt` che eseguono una conversione in un tipo di dati specifico. Per altre informazioni, vedere [Funzioni di conversione del tipo](type-conversion-functions.md).
> - Operatore [DirectCast](../operators/directcast-operator.md) o [operatore TryCast](../operators/trycast-operator.md). Questi operatori richiedono che un tipo erediti da o implementi l'altro tipo. Possono fornire prestazioni leggermente migliori rispetto `CType` a quando si esegue la conversione da e verso il `Object` tipo di dati.

`CType`viene compilato inline, il che significa che il codice di conversione fa parte del codice che valuta l'espressione. In alcuni casi, il codice viene eseguito più velocemente perché non viene chiamata alcuna routine per eseguire la conversione.

Se non viene definita alcuna conversione da `expression` a `typename` (ad esempio, da `Integer` a `Date` ), Visual Basic Visualizza un messaggio di errore in fase di compilazione.

Se una conversione non riesce in fase di esecuzione, viene generata l'eccezione appropriata. Se una conversione verso un tipo di caratteri più piccolo non riesce, <xref:System.OverflowException> è il risultato più comune. Se la conversione non è definita, viene <xref:System.InvalidCastException> generata un'eccezione. Questo può verificarsi, ad esempio, se `expression` è di tipo `Object` e il tipo in fase di esecuzione non dispone di conversione in `typename` .

Se il tipo di dati di `expression` o `typename` è una classe o una struttura definita, è possibile definire `CType` su tale classe o struttura come operatore di conversione. In questo `CType` modo, funge da *operatore di overload*. In tal caso, è possibile controllare il comportamento delle conversioni da e verso la classe o la struttura, incluse le eccezioni che possono essere generate.

## <a name="overloading"></a>Overload

`CType`È inoltre possibile eseguire l'overload dell'operatore in una classe o in una struttura definita all'esterno del codice. Se il codice viene convertito in o da tale classe o struttura, assicurarsi di comprendere il comportamento dell' `CType` operatore. Per altre informazioni, vedere [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).

## <a name="converting-dynamic-objects"></a>Conversione di oggetti dinamici

Le conversioni di tipi di oggetti dinamici vengono eseguite da conversioni dinamiche definite dall'utente che utilizzano i <xref:System.Dynamic.DynamicObject.TryConvert%2A> <xref:System.Dynamic.DynamicMetaObject.BindConvert%2A> metodi o. Se si utilizzano oggetti dinamici, utilizzare il <xref:Microsoft.VisualBasic.Conversion.CTypeDynamic%2A> metodo per convertire l'oggetto dinamico.

## <a name="example"></a>Esempio

Nell'esempio seguente viene utilizzata la `CType` funzione per convertire un'espressione nel `Single` tipo di dati.

[!code-vb[VbVbalrFunctions#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#24)]

Per altri esempi, vedere [conversioni implicite ed esplicite](../../programming-guide/language-features/data-types/implicit-and-explicit-conversions.md).

## <a name="see-also"></a>Vedere anche

- <xref:System.OverflowException>
- <xref:System.InvalidCastException>
- [CString](type-conversion-functions.md)
- [Funzioni di conversione](conversion-functions.md)
- [Operator Statement](../statements/operator-statement.md)
- [Procedura: Definire un operatore di conversione](../../programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
- [Conversione dei tipi nel .NET Framework](../../../standard/base-types/type-conversion.md)
