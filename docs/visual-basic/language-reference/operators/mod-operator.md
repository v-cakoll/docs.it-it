---
title: Operatore Mod (Visual Basic)
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
ms.openlocfilehash: 6bb34eb810f6e2d0b0d631f5891e3e65aa0b170f
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56981400"
---
# <a name="mod-operator-visual-basic"></a>Operatore Mod (Visual Basic)
Divide due numeri e restituisce solo il resto.  
  
## <a name="syntax"></a>Sintassi  
  
```  
number1 Mod number2  
```  
  
## <a name="parts"></a>Parti  
 `number1`  
 Obbligatorio. Qualsiasi espressione numerica.  
  
 `number2`  
 Obbligatorio. Qualsiasi espressione numerica.  
  
## <a name="supported-types"></a>Tipi supportati  
 tutti i tipi numerici. Inclusi i tipi senza segno e a virgola mobile e `Decimal`.  
  
## <a name="result"></a>Risultato

Il risultato è il resto dopo aver `number1` diviso per `number2`. Ad esempio, l'espressione `14 Mod 4` restituisce 2.  

> [!NOTE]
> È presente una differenza tra *resto* e *modulus* in matematica, con risultati diversi per i numeri negativi. Il `Mod` operatore in Visual Basic, .NET Framework `op_Modulus` operatore e sottostante [rem](<xref:System.Reflection.Emit.OpCodes.Rem>) istruzione che eseguire un'operazione di resto.

Il risultato di una `Mod` operazione consente di mantenere il segno del dividendo, `number1`, e pertanto può essere positivo o negativo. Il risultato è sempre compreso nell'intervallo (-`number2`, `number2`), esclusivo. Ad esempio:

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
 Se uno dei due `number1` o `number2` è un valore a virgola mobile, viene restituito il resto della divisione a virgola mobile. Il tipo di dati del risultato è il tipo di dati più piccolo che può contenere tutti i possibili valori risultanti dalla divisione con i tipi di dati di `number1` e `number2`.  
  
 Se `number1` oppure `number2` restituisca [Nothing](../../../visual-basic/language-reference/nothing.md), viene considerato come zero.  
  
 Gli operatori correlati includono quanto segue:  
  
-   Il [\ (operatore) (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md) restituisce il quoziente di una divisione. Ad esempio, l'espressione `14 \ 4` restituisce 3.  
  
-   Il [/ operatore (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) restituisce il quoziente completo, incluso il resto, sotto forma di numero a virgola mobile. Ad esempio, l'espressione `14 / 4` 3.5 viene valutata.  
  
## <a name="attempted-division-by-zero"></a>Tentativo di divisione per zero  
 Se `number2` restituisce zero, il comportamento del `Mod` operatore dipende dal tipo dei dati degli operandi. Una divisione integrale genera un <xref:System.DivideByZeroException> eccezione. Restituisce una divisione a virgola mobile <xref:System.Double.NaN>.  
  
## <a name="equivalent-formula"></a>Formula equivalente  
 L'espressione `a Mod b` è equivalente a una delle formule seguenti:  
  
 `a - (b * (a \ b))`  
  
 `a - (b * Fix(a / b))`  
  
## <a name="floating-point-imprecision"></a>A virgola mobile dell'imprecisione  
 Quando si lavora con numeri a virgola mobile, tenere presente che non sempre hanno una rappresentazione decimale precisa in memoria. Questo può causare risultati imprevisti da determinate operazioni, ad esempio il confronto dei valori e `Mod` operatore. Per altre informazioni, vedere [tipi di dati di risoluzione dei problemi](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).  
  
## <a name="overloading"></a>Overload  
 Il `Mod` operatore può essere *sottoposto a overload*, il che significa che una classe o struttura può ridefinire il relativo comportamento. Se il codice applica `Mod` a un'istanza di una classe o struttura che include un overload di questo tipo, assicurarsi di comprendere il comportamento ridefinito. Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa il `Mod` operatore divide due numeri e restituisce solo il resto. Se uno dei due numeri sono un numero a virgola mobile, il risultato è un numero a virgola mobile che rappresenta il resto.  
  
 [!code-vb[VbVbalrOperators#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#31)]  
  
## <a name="example"></a>Esempio  
 L'esempio seguente illustra le potenzialità dell'imprecisione di operandi a virgola mobile. Nella prima istruzione, gli operandi sono `Double`, e una frazione binaria ripetuta all'infinito con un valore memorizzato di 0.20000000000000001 0,2. Nella seconda istruzione, di tipo carattere letterale `D` forza di entrambi gli operandi in `Decimal`, e 0.2 la rappresentazione è precisa.  
  
 [!code-vb[VbVbalrOperators#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#32)]  
  
## <a name="see-also"></a>Vedere anche
- <xref:Microsoft.VisualBasic.Conversion.Int%2A>
- <xref:Microsoft.VisualBasic.Conversion.Fix%2A>
- [Operatori aritmetici](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Precedenza tra gli operatori in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Elenco degli operatori per funzionalità](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Risoluzione dei problemi relativi ai tipi di dati](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [Operatori aritmetici in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [\ Operatore (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md)
