---
title: Operatore Mod (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
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
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5464b57c993e5703c09529b527a7bc714e045870
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
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
 Tutti i tipi numerici. Sono inclusi i tipi senza segno a virgola mobile e `Decimal`.  
  
## <a name="result"></a>Risultato  
 Il risultato è il resto dopo `number1` viene diviso per `number2`. Ad esempio, l'espressione `14 Mod 4` restituisce 2.  
  
## <a name="remarks"></a>Note  
 Se il valore `number1` o `number2` è un valore a virgola mobile, viene restituito il resto della divisione a virgola mobile. Il tipo di dati del risultato è il tipo di dati più piccolo che può contenere tutti i possibili valori risultanti dalla divisione con i tipi di dati di `number1` e `number2`.  
  
 Se `number1` o `number2` restituisce [nulla](../../../visual-basic/language-reference/nothing.md), viene considerato pari a zero.  
  
 Gli operatori correlati includono quanto segue:  
  
-   Il [\ (operatore) (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md) restituisce il quoziente di una divisione. Ad esempio, l'espressione `14 \ 4` restituisce 3.  
  
-   Il [/ (operatore) (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) restituisce il quoziente completo, incluso il resto, come numero a virgola mobile. Ad esempio, l'espressione `14 / 4` restituisce 3.5.  
  
## <a name="attempted-division-by-zero"></a>Tentativo di divisione per Zero  
 Se `number2` restituisce zero, il comportamento del `Mod` operatore dipende dal tipo di dati degli operandi. Una divisione integrale genera un <xref:System.DivideByZeroException> eccezione. Restituisce una divisione a virgola mobile <xref:System.Double.NaN>.  
  
## <a name="equivalent-formula"></a>Formula equivalente  
 L'espressione `a Mod b` è equivalente a una delle seguenti formule:  
  
 `a - (b * (a \ b))`  
  
 `a - (b * Fix(a / b))`  
  
## <a name="floating-point-imprecision"></a>A virgola mobile imprecisione  
 Quando si utilizzano numeri a virgola mobile, tenere presente che non sempre contengono una precisa rappresentazione in memoria. Ciò potrebbe provocare risultati imprevisti da alcune operazioni, ad esempio il confronto di valori e `Mod` operatore. Per ulteriori informazioni, vedere [risoluzione dei problemi dei tipi di dati](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).  
  
## <a name="overloading"></a>Overload  
 Il `Mod` operatore può essere *overload*, il che significa che una classe o struttura ridefinire il relativo comportamento. Se il codice applica `Mod` a un'istanza di una classe o struttura che include un overload di questo tipo, assicurarsi di comprendere il comportamento ridefinito. Per ulteriori informazioni, vedere [routine di operatore](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa il `Mod` operatore di divisione tra due numeri e restituire solo il resto. Se il numero è un numero a virgola mobile, il risultato è un numero a virgola mobile che rappresenta il resto.  
  
 [!code-vb[VbVbalrOperators#31](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/mod-operator_1.vb)]  
  
## <a name="example"></a>Esempio  
 L'esempio seguente illustra la potenziale imprecisione degli operandi a virgola mobile. Nella prima istruzione, gli operandi sono `Double`, e una frazione binaria ripetuta all'infinito con un valore archiviato di 0,20000000000000001 0,2. Nella seconda istruzione, il valore letterale carattere tipo `D` impone entrambi gli operandi siano `Decimal`, e 0,2 la rappresentazione è precisa.  
  
 [!code-vb[VbVbalrOperators#32](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/mod-operator_2.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:Microsoft.VisualBasic.Conversion.Int%2A>  
 <xref:Microsoft.VisualBasic.Conversion.Fix%2A>  
 [Operatori aritmetici](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [Precedenza tra gli operatori in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Elenco degli operatori per funzionalità](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Risoluzione dei problemi relativi ai tipi di dati](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [Operatori aritmetici in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)  
 [\ Operatore (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md)
