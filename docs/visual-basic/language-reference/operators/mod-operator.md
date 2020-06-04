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
ms.openlocfilehash: 32065567799b023556a018ae2f5ba338796e0b49
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401511"
---
# <a name="mod-operator-visual-basic"></a>Operatore Mod (Visual Basic)

Divide due numeri e restituisce solo il resto.

## <a name="syntax"></a>Sintassi

```vb
result = number1 Mod number2
```

## <a name="parts"></a>Parti

`result` \
Obbligatorio. Qualsiasi variabile o proprietà numerica.

`number1` \
Obbligatorio. Qualsiasi espressione numerica.

`number2` \
Obbligatorio. Qualsiasi espressione numerica.

## <a name="supported-types"></a>Tipi supportati

tutti i tipi numerici. Sono inclusi i tipi a virgola mobile e non firmati e `Decimal` .

## <a name="result"></a>Risultato

Il risultato è il resto dopo che `number1` è diviso per `number2` . Ad esempio, l'espressione `14 Mod 4` restituisce 2.

> [!NOTE]
> Esiste una differenza tra *resto* e *modulo* in matematica, con risultati diversi per i numeri negativi. L' `Mod` operatore in Visual Basic, l' `op_Modulus` operatore .NET Framework e l'istruzione [REM](<xref:System.Reflection.Emit.OpCodes.Rem>) il sottostante eseguono un'operazione resto.

Il risultato di un' `Mod` operazione mantiene il segno del dividendo, `number1` , quindi può essere positivo o negativo. Il risultato è sempre compreso nell'intervallo (- `number2` , `number2` ), Exclusive. Ad esempio:

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

## <a name="remarks"></a>Osservazioni

Se `number1` o `number2` è un valore a virgola mobile, viene restituito il resto a virgola mobile della divisione. Il tipo di dati del risultato è il tipo di dati più piccolo che può conservare tutti i valori possibili risultanti dalla divisione con i tipi di dati di `number1` e `number2` .

Se `number1` o `number2` restituisce [Nothing](../nothing.md), viene considerato come zero.

Gli operatori correlati includono quanto segue:

- L' [operatore \ (Visual Basic)](integer-division-operator.md) restituisce il quoziente integer di una divisione. Ad esempio, l'espressione `14 \ 4` restituisce 3.

- L' [operatore/(Visual Basic)](floating-point-division-operator.md) restituisce il quoziente completo, incluso il resto, come numero a virgola mobile. Ad esempio, l'espressione `14 / 4` restituisce 3,5.

## <a name="attempted-division-by-zero"></a>Tentativo di divisione per zero

Se `number2` restituisce zero, il comportamento dell' `Mod` operatore dipende dal tipo di dati degli operandi:

- Una divisione integrale genera un' <xref:System.DivideByZeroException> eccezione se `number2` non può essere determinata in fase di compilazione e genera un errore in fase di compilazione `BC30542 Division by zero occurred while evaluating this expression` se `number2` viene valutato a zero in fase di compilazione.
- Viene restituita una divisione a virgola mobile <xref:System.Double.NaN?displayProperty=nameWithType> .

## <a name="equivalent-formula"></a>Formula equivalente

L'espressione `a Mod b` è equivalente a una delle formule seguenti:

`a - (b * (a \ b))`

`a - (b * Fix(a / b))`

## <a name="floating-point-imprecision"></a>Imprecisione a virgola mobile

Quando si utilizzano numeri a virgola mobile, tenere presente che in memoria non è sempre presente una rappresentazione decimale precisa. Questo può causare risultati imprevisti di determinate operazioni, ad esempio il confronto dei valori e l' `Mod` operatore. Per ulteriori informazioni, vedere [risoluzione dei problemi](../../programming-guide/language-features/data-types/troubleshooting-data-types.md)relativi ai tipi di dati.

## <a name="overloading"></a>Overload

È `Mod` possibile eseguire l' *Overload*dell'operatore, il che significa che una classe o una struttura può ridefinire il comportamento. Se il codice si applica `Mod` a un'istanza di una classe o una struttura che include tale overload, assicurarsi di comprendere il comportamento ridefinito. Per altre informazioni, vedere [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).

## <a name="example"></a>Esempio

Nell'esempio seguente viene usato l' `Mod` operatore per dividere due numeri e restituire solo il resto. Se uno dei due numeri è un numero a virgola mobile, il risultato è un numero a virgola mobile che rappresenta il resto.

[!code-vb[VbVbalrOperators#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#31)]

## <a name="example"></a>Esempio

Nell'esempio seguente viene illustrata la potenziale imprecisione degli operandi a virgola mobile. Nella prima istruzione gli operandi sono `Double` e 0,2 è una frazione binaria ripetuta in modo infinito con un valore archiviato di 0.20000000000000001. Nella seconda istruzione, il carattere di tipo letterale `D` impone entrambi gli operandi a `Decimal` e 0,2 presenta una rappresentazione precisa.

[!code-vb[VbVbalrOperators#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#32)]

## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.Conversion.Int%2A>
- <xref:Microsoft.VisualBasic.Conversion.Fix%2A>
- [Operatori aritmetici](arithmetic-operators.md)
- [Precedenza tra gli operatori in Visual Basic](operator-precedence.md)
- [Elenco degli operatori per funzionalità](operators-listed-by-functionality.md)
- [Risoluzione dei problemi relativi ai tipi di dati](../../programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [Operatori aritmetici in Visual Basic](../../programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [Operatore \ (Visual Basic)](integer-division-operator.md)
