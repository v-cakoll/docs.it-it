---
title: '- Operatore (Visual Basic)'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Negate
- vb.-
helpviewer_keywords:
- operator [Visual Basic]
- operators [Visual Basic], subtraction
- operators [Visual Basic], difference
- negation operator [Visual Basic]
- operators [Visual Basic], arithmetic
- subtraction operator [Visual Basic], syntax
- arithmetic operators [Visual Basic], subtraction
- difference operator [Visual Basic]
- math operators [Visual Basic]
- operators [Visual Basic], negation
- minus operator [Visual Basic]
ms.assetid: bff2c368-662d-4c92-ac87-1d9bdfd3426a
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4ffb7c96fe95e73dc857a15608df94ed8468f9df
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="--operator-visual-basic"></a>Operatore - (Visual Basic)
Restituisce la differenza tra due espressioni numeriche o il valore negativo di un'espressione numerica.  
  
## <a name="syntax"></a>Sintassi  
  
```  
      expression1 – expression2  
- or -  
– expression1  
```  
  
## <a name="parts"></a>Parti  
 `expression1`  
 Obbligatorio. Qualsiasi espressione numerica.  
  
 `expression2`  
 Obbligatorio a meno che il `–` operatore viene calcolato un valore negativo. Qualsiasi espressione numerica.  
  
## <a name="result"></a>Risultato  
 Il risultato è la differenza tra `expression1` e `expression2`, o il valore negato di `expression1`.  
  
 Il tipo di dati del risultato è un tipo numerico appropriato per i tipi di dati di `expression1` e `expression2`. Vedere le tabelle "Calcoli di interi" in [tipi di dati di risultati di operatore](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).  
  
## <a name="supported-types"></a>Tipi supportati  
 Tutti i tipi numerici. Sono inclusi i tipi senza segno a virgola mobile e `Decimal`.  
  
## <a name="remarks"></a>Note  
 Nel primo utilizzo illustrato nella sintassi precedente, il `–` operatore è il *binario* operatore di sottrazione aritmetica per la differenza tra due espressioni numeriche.  
  
 Nel secondo utilizzo illustrato nella sintassi precedente, il `–` operatore è il *unario* operatore di negazione per il valore negativo di un'espressione. In questo senso, la negazione consiste inversione del segno di `expression1` in modo che il risultato è positivo se `expression1` è negativo.  
  
 Se un'espressione restituisce [nulla](../../../visual-basic/language-reference/nothing.md), `–` operatore lo considera come zero.  
  
> [!NOTE]
>  Il `–` operatore può essere *overload*, il che significa che una classe o struttura ridefinire il comportamento quando un operando ha il tipo di quella classe o struttura. Se il codice utilizza l'operatore su una classe o una struttura, assicurarsi di aver compreso il comportamento ridefinito. Per ulteriori informazioni, vedere [routine di operatore](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa il `–` operatore per calcolare e restituire la differenza tra due numeri interi, quindi per negare un numero.  
  
 [!code-vb[VbVbalrOperators#10](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/subtraction-operator_1.vb)]  
  
 Dopo l'esecuzione di queste istruzioni, `binaryResult` contiene il valore 124,45 e `unaryResult` 334,90.  
  
## <a name="see-also"></a>Vedere anche  
 [-= Operatore (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-assignment-operator.md) [operatori aritmetici](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [Precedenza tra gli operatori in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Elenco degli operatori per funzionalità](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Operatori aritmetici in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
