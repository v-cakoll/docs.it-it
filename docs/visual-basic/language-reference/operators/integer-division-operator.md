---
title: Operatore \ (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.\
- '\'
helpviewer_keywords:
- division operator [Visual Basic], integer
- integer division operator [Visual Basic]
- zero, division by zero
- arithmetic operators [Visual Basic], division
- division [Visual Basic], by zero
- backslash (\) [Visual Basic]
- '\ operator [Visual Basic]'
- integer quotient
- math operators [Visual Basic]
- quotients, integer
- truncation [Visual Basic], integer division
ms.assetid: 4b0ee347-950c-45c9-8e23-54bc85df208e
ms.openlocfilehash: d1a46f99c21be007d33361ba095a3f0c52fe906c
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701139"
---
# <a name="-operator-visual-basic"></a>Operatore \ (Visual Basic)
Divide due numeri e restituisce un risultato intero.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
expression1 \ expression2  
```  
  
## <a name="parts"></a>Parti  
 `expression1`  
 Obbligatorio. Qualsiasi espressione numerica.  
  
 `expression2`  
 Obbligatorio. Qualsiasi espressione numerica.  
  
## <a name="supported-types"></a>Tipi supportati  
 Tutti i tipi numerici, inclusi i tipi senza segno e a virgola mobile e `Decimal`.  
  
## <a name="result"></a>Risultato  
 Il risultato è il quoziente intero di `expression1` diviso per `expression2`, che elimina qualsiasi resto e mantiene solo la parte intera. Questa operazione è nota come *troncamento*.  
  
 Il tipo di dati del risultato è un tipo numerico appropriato per i tipi di dati di `expression1` e `expression2`. Vedere le tabelle "aritmetiche di interi" nei [tipi di dati dei risultati dell'operatore](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).  
  
 L' [operatore/(Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) restituisce il quoziente completo, che mantiene il resto della parte frazionaria.  
  
## <a name="remarks"></a>Note  
 Prima di eseguire la divisione, Visual Basic tenta di convertire qualsiasi espressione numerica a virgola mobile in `Long`. Se `Option Strict` è `On`, si verifica un errore del compilatore. Se `Option Strict` è `Off`, è possibile <xref:System.OverflowException> Se il valore non è compreso nell'intervallo del [tipo di dati Long](../../../visual-basic/language-reference/data-types/long-data-type.md). Anche la conversione a `Long` è soggetta all' *arrotondamento del banco*. Per ulteriori informazioni, vedere "parti frazionarie" nelle [funzioni di conversione dei tipi](../../../visual-basic/language-reference/functions/type-conversion-functions.md).  
  
 Se `expression1` o`expression2` restituisce [Nothing](../../../visual-basic/language-reference/nothing.md), viene considerato come zero.  
  
## <a name="attempted-division-by-zero"></a>Tentativo di divisione per zero  
 Se `expression2` restituisce zero, l'operatore `\` genera un'eccezione <xref:System.DivideByZeroException>. Questo vale per tutti i tipi di dati numerici degli operandi.  
  
> [!NOTE]
> L'operatore `\` può essere sottoposto a *Overload*, il che significa che una classe o una struttura può ridefinire il comportamento quando un operando ha il tipo della classe o della struttura. Se il codice usa questo operatore su una classe o una struttura di questo tipo, assicurarsi di comprendere il comportamento ridefinito. Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene usato l'operatore `\` per eseguire la divisione di interi. Il risultato è un numero intero che rappresenta il quoziente integer dei due operandi, con il resto ignorato.  
  
 [!code-vb[VbVbalrOperators#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#18)]  
  
 Le espressioni nell'esempio precedente restituiscono rispettivamente i valori 2, 3, 33 e-22.  
  
## <a name="see-also"></a>Vedere anche

- [Operatore \\ =](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md)
- [Operatore/(Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md)
- [Istruzione Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [Operatori aritmetici](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Precedenza tra gli operatori in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Elenco degli operatori per funzionalità](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Operatori aritmetici in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
