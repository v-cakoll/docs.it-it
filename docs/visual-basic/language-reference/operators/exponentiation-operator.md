---
title: Operatore ^ (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.^
helpviewer_keywords:
- raising numbers to powers
- ^ operator [Visual Basic], exponention
- square operator [Visual Basic]
- ^ operator [Visual Basic]
- exponentiation operator [Visual Basic]
- exponent
- numbers [Visual Basic], rasing
- powers
- arithmetic operators [Visual Basic], exponentiation
ms.assetid: d89a1ca8-83da-4784-a87b-a9d7dceb3f62
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9e7159f289b687055c7d75cc8da58d6f76607a83
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-visual-basic"></a>Operatore ^ (Visual Basic)
Eleva un numero alla potenza di un altro numero.  
  
## <a name="syntax"></a>Sintassi  
  
```  
number ^ exponent  
```  
  
## <a name="parts"></a>Parti  
 `number`  
 Obbligatorio. Qualsiasi espressione numerica.  
  
 `exponent`  
 Obbligatorio. Qualsiasi espressione numerica.  
  
## <a name="result"></a>Risultato  
 Il risultato è `number` elevato alla potenza di `exponent`, sempre come un `Double` valore.  
  
## <a name="supported-types"></a>Tipi supportati  
 `Double`. Gli operandi di tipo diverso vengono convertiti in `Double`.  
  
## <a name="remarks"></a>Note  
 Visual Basic esegue sempre elevamento a potenza nel [tipo di dati Double](../../../visual-basic/language-reference/data-types/double-data-type.md).  
  
 Il valore di `exponent` può essere frazionario, negativo o entrambi.  
  
 Quando più elevamento a potenza viene eseguito in un'unica espressione, il `^` operatore viene valutato come viene rilevata da sinistra a destra.  
  
> [!NOTE]
>  Il `^` operatore può essere *overload*, il che significa che una classe o struttura ridefinire il comportamento quando un operando ha il tipo di quella classe o struttura. Se il codice Usa l'operatore in una classe o una struttura, assicurarsi di comprendere il comportamento ridefinito. Per ulteriori informazioni, vedere [routine di operatore](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa il `^` operatore per generare un numero alla potenza di un esponente. Il risultato è il primo operando elevato alla potenza del secondo.  
  
 [!code-vb[VbVbalrOperators#20](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/exponentiation-operator_1.vb)]  
  
 Nell'esempio precedente produce i risultati seguenti:  
  
 `exp1`è impostato su 4 (2 al quadrato).  
  
 `exp2`è impostato su 19683 (3 al cubo, quindi tale valore al cubo).  
  
 `exp3`è impostato su -125 (-5 al cubo).  
  
 `exp4`è impostato su 625 (-5 alla quarta potenza).  
  
 `exp5`è impostato su 2 (radice cubica di 8).  
  
 `exp6`è impostato su 0,5 (1.0 diviso la radice cubica di 8).  
  
 Si noti l'importanza delle parentesi nelle espressioni nell'esempio precedente. Causa del *precedenza degli operatori*, Visual Basic esegue in genere il `^` operatore prima degli altri, anche l'operatore unario `–` operatore. Se `exp4` e `exp6` è stata calcolata senza parentesi, prodotti sarebbero stati i seguenti risultati:  
  
 `exp4 = -5 ^ 4`viene calcolato come: (5 alla quarta potenza), che comporta la-625.  
  
 `exp6 = 8 ^ -1.0 / 3.0`viene calcolato come (8 per la potenza di-1 o 0,125) diviso 3.0, risultato uguale a 0,041666666666666666666666666666667.  
  
## <a name="see-also"></a>Vedere anche  
 [Operatore ^=](../../../visual-basic/language-reference/operators/exponentiation-assignment-operator.md)  
 [Operatori aritmetici](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [Precedenza tra gli operatori in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Elenco degli operatori per funzionalità](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Operatori aritmetici in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
