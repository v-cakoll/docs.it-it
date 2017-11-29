---
title: Operatore \ (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 38718b109b4b3865238267039908ea1d51d06229
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
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
 Tutti i tipi numerici, inclusi i tipi senza segno a virgola mobile e `Decimal`.  
  
## <a name="result"></a>Risultato  
 Il risultato è il quoziente di `expression1` diviso `expression2`, che le parti restanti e viene mantenuta solo la parte intera. Questo è noto come *troncamento*.  
  
 Il tipo di dati del risultato è un tipo numerico appropriato per i tipi di dati di `expression1` e `expression2`. Vedere le tabelle "Calcoli di interi" in [tipi di dati di risultati di operatore](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).  
  
 Il [/ (operatore) (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) restituisce il quoziente completo, incluso il resto nella parte frazionaria.  
  
## <a name="remarks"></a>Note  
 Prima di eseguire la divisione, Visual Basic tenta di convertire qualsiasi espressione numerica a virgola mobile a `Long`. Se `Option Strict` è `On`, si verifica un errore del compilatore. Se `Option Strict` è `Off`, un <xref:System.OverflowException> è possibile se il valore è compreso nell'intervallo del [tipo di dati Long](../../../visual-basic/language-reference/data-types/long-data-type.md). La conversione a `Long` è anche soggetto a *arrotondamento*. Per ulteriori informazioni, vedere "Parti frazionarie" in [funzioni di conversione del tipo](../../../visual-basic/language-reference/functions/type-conversion-functions.md).  
  
 Se `expression1` o `expression2` restituisce [nulla](../../../visual-basic/language-reference/nothing.md), viene considerato pari a zero.  
  
## <a name="attempted-division-by-zero"></a>Tentativo di divisione per Zero  
 Se `expression2` restituisce zero, il `\` operatore genera un <xref:System.DivideByZeroException> eccezione. Questo vale per tutti i tipi di dati numerici degli operandi.  
  
> [!NOTE]
>  Il `\` operatore può essere *overload*, il che significa che una classe o struttura ridefinire il comportamento quando un operando ha il tipo di quella classe o struttura. Se il codice Usa l'operatore in una classe o una struttura, assicurarsi di comprendere il comportamento ridefinito. Per ulteriori informazioni, vedere [routine di operatore](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa il `\` operatore per eseguire la divisione di integer. Il risultato è un numero intero che rappresenta il quoziente di due operandi, con il resto.  
  
 [!code-vb[VbVbalrOperators#18](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/integer-division-operator_1.vb)]  
  
 Nell'esempio precedente le espressioni restituiscono rispettivamente i valori 2, 3, 33 e -22.  
  
## <a name="see-also"></a>Vedere anche  
 [\\= (Operatore)](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md)  
 [/ Operatore (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md)  
 [Istruzione Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [Operatori aritmetici](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [Precedenza tra gli operatori in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Elenco degli operatori per funzionalità](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Operatori aritmetici in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
