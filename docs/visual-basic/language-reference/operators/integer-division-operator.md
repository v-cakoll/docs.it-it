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
ms.openlocfilehash: ac306038aefba4ca0e0f13fa2945d01c27c0804d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54654685"
---
# <a name="-operator-visual-basic"></a>Operatore \ (Visual Basic)
Divide due numeri e restituisce un risultato intero.  
  
## <a name="syntax"></a>Sintassi  
  
```  
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
 Il risultato è il quoziente dei `expression1` diviso per `expression2`, che elimina qualsiasi parte rimanente e mantiene solo la parte intera. Questo è noto come *troncamento*.  
  
 Il tipo di dati del risultato è un tipo numerico appropriato per i tipi di dati di `expression1` e `expression2`. Vedere le tabelle "Calcoli di interi" nella [Data Types of operatore Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).  
  
 Il [/ operatore (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) restituisce il quoziente completo, incluso il resto in parte frazionaria.  
  
## <a name="remarks"></a>Note  
 Prima di eseguire la divisione, Visual Basic tenta di convertire qualsiasi espressione numerica a virgola mobile a `Long`. Se `Option Strict` è `On`, si verifica un errore del compilatore. Se `Option Strict` viene `Off`, un <xref:System.OverflowException> può verificarsi se il valore è compreso nell'intervallo del [tipo di dati Long](../../../visual-basic/language-reference/data-types/long-data-type.md). La conversione a `Long` è anche soggetto *arrotondamento*. Per altre informazioni, vedere "Parti frazionarie" nella [funzioni di conversione del tipo](../../../visual-basic/language-reference/functions/type-conversion-functions.md).  
  
 Se `expression1` oppure `expression2` restituisca [Nothing](../../../visual-basic/language-reference/nothing.md), viene considerato come zero.  
  
## <a name="attempted-division-by-zero"></a>Tentativo di divisione per Zero  
 Se `expression2` restituisce zero, il `\` operatore genera un <xref:System.DivideByZeroException> eccezione. Questo vale per tutti i tipi di dati numerici degli operandi.  
  
> [!NOTE]
>  Il `\` operatore può essere *sottoposto a overload*, il che significa che una classe o struttura può ridefinire il comportamento quando un operando ha il tipo di quella classe o struttura. Se il codice Usa l'operatore su una classe o struttura, assicurarsi di che comprendere il comportamento ridefinito. Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa il `\` operatore per eseguire la divisione di integer. Il risultato è un intero che rappresenta il quoziente dei due operandi, escluso il resto.  
  
 [!code-vb[VbVbalrOperators#18](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/integer-division-operator_1.vb)]  
  
 Le espressioni nell'esempio precedente restituiscono i valori 2, 3, 33 e -22, rispettivamente.  
  
## <a name="see-also"></a>Vedere anche
- [\\= Operatore](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md)
- [/ Operatore (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md)
- [Istruzione Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [Operatori aritmetici](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Precedenza tra gli operatori in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Elenco degli operatori per funzionalità](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Operatori aritmetici in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
