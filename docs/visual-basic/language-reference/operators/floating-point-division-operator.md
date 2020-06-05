---
title: Operatore /
ms.date: 07/20/2015
f1_keywords:
- vb./
helpviewer_keywords:
- division operator [Visual Basic], floating point
- floating-point numbers [Visual Basic], division operator
- slash (/) operator
- zero, division by zero
- operators [Visual Basic], arithmetic
- arithmetic operators [Visual Basic], division
- division [Visual Basic], by zero
- operators [Visual Basic], division
- division operator [Visual Basic], syntax
- / operator [Visual Basic]
- math operators [Visual Basic]
ms.assetid: 335e97f2-c434-439e-9064-76973a051101
ms.openlocfilehash: e9400b50a84522f87a9a2ea4cd05b479d7a4538e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84371168"
---
# <a name="-operator-visual-basic"></a>Operatore / (Visual Basic)
Divide due numeri e restituisce un risultato a virgola mobile.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
expression1 / expression2  
```  
  
## <a name="parts"></a>Parti  
 `expression1`  
 Obbligatorio. Qualsiasi espressione numerica.  
  
 `expression2`  
 Obbligatorio. Qualsiasi espressione numerica.  
  
## <a name="supported-types"></a>Tipi supportati  
 Tutti i tipi numerici, inclusi i tipi senza segno e a virgola mobile e `Decimal` .  
  
## <a name="result"></a>Risultato  
 Il risultato è il quoziente completo di `expression1` diviso per `expression2` , incluso qualsiasi resto.  
  
 L' [operatore \ (Visual Basic)](integer-division-operator.md) restituisce il quoziente integer, che elimina il resto.  
  
## <a name="remarks"></a>Commenti  
 Il tipo di dati del risultato dipende dai tipi degli operandi. Nella tabella seguente viene illustrato il modo in cui viene determinato il tipo di dati del risultato.  
  
|Tipi di dati degli operandi|Tipo di dati result|  
|------------------------|----------------------|  
|Entrambe le espressioni sono tipi di dati integrali ([SByte](../data-types/sbyte-data-type.md), [byte](../data-types/byte-data-type.md), [short](../data-types/short-data-type.md), [ushort](../data-types/ushort-data-type.md), [Integer](../data-types/integer-data-type.md), [UInteger](../data-types/uinteger-data-type.md), [Long](../data-types/long-data-type.md), [ULONG](../data-types/ulong-data-type.md))|`Double`|  
|Un'espressione è un tipo di dati [singolo](../data-types/single-data-type.md) e l'altra non è un [valore Double](../data-types/double-data-type.md)|`Single`|  
|Un'espressione è un tipo di dati [Decimal](../data-types/decimal-data-type.md) e l'altra non è una [singola](../data-types/single-data-type.md) o una [doppia](../data-types/double-data-type.md)|`Decimal`|  
|Expression è un tipo di dati [Double](../data-types/double-data-type.md)|`Double`|  
  
 Prima di eseguire la divisione, le espressioni numeriche integrali vengono ampliate a `Double` . Se il risultato viene assegnato a un tipo di dati integrale, Visual Basic tenta di convertire il risultato da `Double` a tale tipo. Questa operazione può generare un'eccezione se il risultato non rientra in tale tipo. In particolare, vedere "tentativo di divisione per zero" in questa pagina della guida.  
  
 Se `expression1` o `expression2` restituisce [Nothing](../nothing.md), viene considerato come zero.  
  
## <a name="attempted-division-by-zero"></a>Tentativo di divisione per zero  
 Se `expression2` restituisce zero, l' `/` operatore si comporta in modo diverso per i diversi tipi di dati degli operandi. La tabella seguente illustra i possibili comportamenti.  
  
|Tipi di dati degli operandi|Comportamento se `expression2` è zero|  
|------------------------|---------------------------------------|  
|Virgola mobile ( `Single` o `Double` )|Restituisce l'infinito ( <xref:System.Double.PositiveInfinity> o <xref:System.Double.NegativeInfinity> ) o <xref:System.Double.NaN> (non un numero) se `expression1` è anche zero|  
|`Decimal`|Genera<xref:System.DivideByZeroException>|  
|Integrale (con segno o senza segno)|Il tentativo di conversione nel tipo integrale genera un'eccezione <xref:System.OverflowException> perché i tipi integrali non accettano <xref:System.Double.PositiveInfinity> , <xref:System.Double.NegativeInfinity> o<xref:System.Double.NaN>|  
  
> [!NOTE]
> L' `/` operatore può essere sottoposto a *Overload*, il che significa che una classe o una struttura può ridefinire il comportamento quando un operando ha il tipo della classe o della struttura. Se il codice usa questo operatore su una classe o una struttura di questo tipo, assicurarsi di comprendere il comportamento ridefinito. Per altre informazioni, vedere [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Esempio  
 Questo esempio usa l' `/` operatore per eseguire la divisione a virgola mobile. Il risultato è il quoziente dei due operandi.  
  
 [!code-vb[VbVbalrOperators#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#16)]  
  
 Le espressioni nell'esempio precedente restituiscono i valori 2,5 e 3,333333. Si noti che il risultato è sempre a virgola mobile ( `Double` ), anche se entrambi gli operandi sono costanti integer.  
  
## <a name="see-also"></a>Vedere anche

- [Operatore /= (Visual Basic)](floating-point-division-assignment-operator.md)
- [Operatore \ (Visual Basic)](integer-division-operator.md)
- [Tipi di dati dei risultati degli operatori](data-types-of-operator-results.md)
- [Operatori aritmetici](arithmetic-operators.md)
- [Precedenza tra gli operatori in Visual Basic](operator-precedence.md)
- [Elenco degli operatori per funzionalità](operators-listed-by-functionality.md)
- [Operatori aritmetici in Visual Basic](../../programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
