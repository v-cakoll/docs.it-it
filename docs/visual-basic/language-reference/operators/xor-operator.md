---
title: Operatore Xor
ms.date: 07/20/2015
f1_keywords:
- vb.Xor
helpviewer_keywords:
- exclusive OR operator [Visual Basic]
- logical exclusion
- operators [Visual Basic], exclusive or
- exclusion operator [Visual Basic]
- operators [Visual Basic], bitwise
- bitwise operators [Visual Basic], XOR operator
- Xor operator [Visual Basic]
- Xor keyword [Visual Basic]
- bitwise comparison [Visual Basic]
ms.assetid: 036000a9-3934-4e7f-a9d0-a816de3d84a6
ms.openlocfilehash: c5c7ec87bc173f724f8c670395bc3b0458444df6
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74335417"
---
# <a name="xor-operator-visual-basic"></a>Operatore Xor (Visual Basic)
Esegue un'esclusione logica di due espressioni `Boolean` o un'esclusione bit per bit su due espressioni numeriche.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
result = expression1 Xor expression2  
```  
  
## <a name="parts"></a>Parti  
 `result`  
 Obbligatoria. Qualsiasi `Boolean` o variabile numerica. Per il confronto booleano, `result` è l'esclusione logica (disgiunzione logica esclusiva) di due valori `Boolean`. Per le operazioni bit per bit, `result` è un valore numerico che rappresenta l'esclusione bit per bit (disgiunzione bit per bit esclusiva) di due modelli di bit numerici.  
  
 `expression1`  
 Obbligatoria. Qualsiasi `Boolean` o espressione numerica.  
  
 `expression2`  
 Obbligatoria. Qualsiasi `Boolean` o espressione numerica.  
  
## <a name="remarks"></a>Note  
 Per il confronto booleano, `result` viene `True` se e solo se esattamente uno dei `expression1` e `expression2` restituisce `True`. Ovvero, se e solo se `expression1` e `expression2` restituiscono valori opposti `Boolean`. Nella tabella seguente viene illustrato il modo in cui viene determinato `result`.  
  
|Se `expression1` è|E `expression2` è|Il valore di `result` è|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`False`|  
|`True`|`False`|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
> In un confronto booleano, l'operatore `Xor` valuta sempre entrambe le espressioni, che possono includere la chiamata di routine. Non esiste alcuna controparte di corto circuito da `Xor`, perché il risultato dipende sempre da entrambi gli operandi. Per gli operatori logici di *corto circuito* , vedere [operatore AndAlso](../../../visual-basic/language-reference/operators/andalso-operator.md) e [operatore OrElse](../../../visual-basic/language-reference/operators/orelse-operator.md).  
  
 Per le operazioni bit per bit, l'operatore `Xor` esegue un confronto bit per bit dei bit posizionati in modo identico in due espressioni numeriche e imposta il bit corrispondente in `result` in base alla tabella seguente.  
  
|Se bit in `expression1` è|E bit in `expression2` è|Il bit in `result` è|  
|--------------------------------|---------------------------------|----------------------------|  
|1|1|0|  
|1|0|1|  
|0|1|1|  
|0|0|0|  
  
> [!NOTE]
> Poiché gli operatori logici e bit per bit hanno una precedenza inferiore rispetto ad altri operatori aritmetici e relazionali, qualsiasi operazione bit per bit deve essere racchiusa tra parentesi per garantire un'esecuzione accurata.  
  
 Ad esempio, 5 `Xor` 3 è 6. Per verificarne il motivo, convertire 5 e 3 nelle rispettive rappresentazioni binarie, 101 e 011. Usare quindi la tabella precedente per determinare che 101 Xor 011 è 110, ovvero la rappresentazione binaria del numero decimale 6.  
  
## <a name="data-types"></a>Tipi di dati  
 Se gli operandi sono costituiti da un'espressione `Boolean` e un'espressione numerica, Visual Basic converte l'espressione `Boolean` in un valore numerico (-1 per `True` e 0 per `False`) ed esegue un'operazione bit per bit.  
  
 Per un confronto di `Boolean`, il tipo di dati del risultato è `Boolean`. Per un confronto bit per bit, il tipo di dati result è un tipo numerico appropriato per i tipi di dati di `expression1` e `expression2`. Vedere la tabella "confronto relazionale e bit per bit" in [tipi di dati dei risultati dell'operatore](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).  
  
## <a name="overloading"></a>Overload  
 L'operatore `Xor` può essere sottoposto a *Overload*, il che significa che una classe o una struttura può ridefinire il comportamento quando un operando ha il tipo della classe o della struttura. Se il codice usa questo operatore su una classe o una struttura di questo tipo, verificare di aver compreso il comportamento ridefinito. Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene usato l'operatore `Xor` per eseguire l'esclusione logica (disgiunzione logica esclusiva) su due espressioni. Il risultato è un valore `Boolean` che indica se è `True`esattamente una delle espressioni.  
  
 [!code-vb[VbVbalrOperators#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#40)]  
  
 Nell'esempio precedente vengono prodotti rispettivamente i risultati di `False`, `True`e `False`.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene usato l'operatore `Xor` per eseguire l'esclusione logica (disgiunzione logica esclusiva) sui singoli bit di due espressioni numeriche. Il bit nel modello di risultato viene impostato se esattamente uno dei bit corrispondenti negli operandi è impostato su 1.  
  
 [!code-vb[VbVbalrOperators#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#41)]  
  
 Nell'esempio precedente vengono prodotti rispettivamente i risultati 2, 12 e 14.  
  
## <a name="see-also"></a>Vedere anche

- [Operatori logici/bit per bit (Visual Basic)](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [Precedenza tra gli operatori in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Elenco degli operatori per funzionalità](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Operatori logici e bit per bit in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
