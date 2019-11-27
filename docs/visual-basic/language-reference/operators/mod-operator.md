---
title: Operatore Mod
ms.date: 04/24/2018
f1_keywords:
- vb.Mod
helpviewer_keywords:
- remainder (Mod operator)
- division operator [Visual Basic], Mod operator
- modulus operator [Visual Basic], Visual Basic
- Mod operator [Visual Basic]
- operators [Visual Basic], division
- arithmetic operators [Visual Basic], Mod
- math operators [Visual Basic]
ms.assetid: 6ff7e40e-cec8-4c77-bff6-8ddd2791c25b
ms.openlocfilehash: b7552550d4b0496d6ad7ee76a7327054d544b874
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350909"
---
# <a name="mod-operator-visual-basic"></a>Operatore Mod (Visual Basic)

Divide due numeri e restituisce solo il resto.

## <a name="syntax"></a>Sintassi

```vb
result = number1 Mod number2
```

## <a name="parts"></a>Parti

`result` \
Obbligatoria. Qualsiasi variabile o proprietà numerica.

`number1` \
Obbligatoria. Qualsiasi espressione numerica.

`number2` \
Obbligatoria. Qualsiasi espressione numerica.

## <a name="supported-types"></a>Tipi supportati

tutti i tipi numerici. Sono inclusi i tipi a virgola mobile e senza segno e `Decimal`.

## <a name="result"></a>Risultato

Il risultato è il resto dopo la divisione di `number1` per `number2`. Ad esempio, l'espressione `14 Mod 4` restituisce 2.

> [!NOTE]
> Esiste una differenza tra *resto* e *modulo* in matematica, con risultati diversi per i numeri negativi. L'operatore `Mod` in Visual Basic, l'operatore .NET Framework `op_Modulus` e l'istruzione [REM](<xref:System.Reflection.Emit.OpCodes.Rem>) il sottostante eseguono un'operazione resto.

Il risultato di un'operazione di `Mod` mantiene il segno del dividendo, `number1`e pertanto può essere positivo o negativo. Il risultato è sempre compreso nell'intervallo (-`number2`, `number2`), Exclusive. Ad esempio:

```vb
Public Module Example
   Public Sub Main()
      Console.WriteLine($" 8 Mod  3 = {8 Mod 3}")
      Console.WriteLine($"-8 Mod  3 = {-8 Mod 3}")
      Console.WriteLine($" 8 Mod -3 = {8 Mod -3}")
      Console.WriteLine($"-8 Mod -3 = {-8 Mod -3}")
   End Sub
End Module
' The example displays the following output:
'       8 Mod  3 = 2
'      -8 Mod  3 = -2
'       8 Mod -3 = 2
'      -8 Mod -3 = -2
```

## <a name="remarks"></a>Note

Se `number1` o `number2` è un valore a virgola mobile, viene restituito il resto a virgola mobile della divisione. Il tipo di dati del risultato è il tipo di dati più piccolo che può conservare tutti i valori possibili risultanti dalla divisione con i tipi di dati di `number1` e `number2`.

Se `number1` o `number2` restituisce [Nothing](../../../visual-basic/language-reference/nothing.md), viene considerato come zero.

Gli operatori correlati includono quanto segue:

- L' [operatore \ (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md) restituisce il quoziente integer di una divisione. Ad esempio, l'espressione `14 \ 4` restituisce 3.

- L' [operatore/(Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) restituisce il quoziente completo, incluso il resto, come numero a virgola mobile. Ad esempio, l'espressione `14 / 4` restituisce 3,5.

## <a name="attempted-division-by-zero"></a>Tentativo di divisione per zero

Se `number2` restituisce zero, il comportamento dell'operatore `Mod` dipende dal tipo di dati degli operandi:

- Una divisione integrale genera un'eccezione <xref:System.DivideByZeroException> se non è possibile determinare `number2` in fase di compilazione e genera un errore in fase di compilazione `BC30542 Division by zero occurred while evaluating this expression` se `number2` viene valutato a zero in fase di compilazione.
- Una divisione a virgola mobile restituisce <xref:System.Double.NaN?displayProperty=nameWithType>.

## <a name="equivalent-formula"></a>Formula equivalente

L'espressione `a Mod b` è equivalente a una delle formule seguenti:

`a - (b * (a \ b))`

`a - (b * Fix(a / b))`

## <a name="floating-point-imprecision"></a>Imprecisione a virgola mobile

Quando si utilizzano numeri a virgola mobile, tenere presente che in memoria non è sempre presente una rappresentazione decimale precisa. Questo può causare risultati imprevisti di determinate operazioni, ad esempio il confronto dei valori e l'operatore `Mod`. Per ulteriori informazioni, vedere [risoluzione dei problemi](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)relativi ai tipi di dati.

## <a name="overloading"></a>Overload

È possibile eseguire l' *Overload*dell'operatore `Mod`, il che significa che una classe o una struttura può ridefinire il comportamento. Se il codice viene applicato `Mod` a un'istanza di una classe o una struttura che include tale overload, assicurarsi di comprendere il comportamento ridefinito. Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).

## <a name="example"></a>Esempio

Nell'esempio seguente viene usato l'operatore `Mod` per dividere due numeri e restituire solo il resto. Se uno dei due numeri è un numero a virgola mobile, il risultato è un numero a virgola mobile che rappresenta il resto.

[!code-vb[VbVbalrOperators#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#31)]

## <a name="example"></a>Esempio

Nell'esempio seguente viene illustrata la potenziale imprecisione degli operandi a virgola mobile. Nella prima istruzione gli operandi sono `Double`e 0,2 è una frazione binaria ripetuta in modo infinito con un valore archiviato di 0.20000000000000001. Nella seconda istruzione, il carattere di tipo letterale `D` impone a entrambi gli operandi di `Decimal`e 0,2 presenta una rappresentazione precisa.

[!code-vb[VbVbalrOperators#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#32)]

## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.Conversion.Int%2A>
- <xref:Microsoft.VisualBasic.Conversion.Fix%2A>
- [Operatori aritmetici](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Precedenza tra gli operatori in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Elenco degli operatori per funzionalità](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Risoluzione dei problemi relativi ai tipi di dati](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [Operatori aritmetici in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [Operatore \ (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md)
