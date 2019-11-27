---
title: '>> Operatore'
ms.date: 07/20/2015
f1_keywords:
- vb.>>
helpviewer_keywords:
- operator>>
- '>> operator [Visual Basic]'
- bit shift operators [Visual Basic]
- operator >>
- right shift operators [Visual Basic]
ms.assetid: 054dc6a6-47d9-47ef-82da-cfa2b59fbf8f
ms.openlocfilehash: cabf8c569435cc0fc98282f5e8f5fd410e6708dc
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347817"
---
# <a name="-operator-visual-basic"></a>Operatore > > (Visual Basic)
Esegue uno spostamento a destra aritmetico in uno schema di bit.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
result = pattern >> amount  
```  
  
## <a name="parts"></a>Parti  
 `result`  
 Obbligatoria. Valore numerico integrale. Risultato dello spostamento dello schema di bit. Il tipo di dati è uguale a quello di `pattern`.  
  
 `pattern`  
 Obbligatoria. Espressione numerica integrale. Modello di bit da spostare. Il tipo di dati deve essere un tipo integrale (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`o `ULong`).  
  
 `amount`  
 Obbligatoria. Espressione numerica. Numero di bit per spostare lo schema di bit. Il tipo di dati deve essere `Integer` o ampliato per `Integer`.  
  
## <a name="remarks"></a>Note  
 I turni aritmetici non sono circolari, il che significa che i bit spostati da un'estremità del risultato non vengono reintrodotti nell'altra estremità. In uno spostamento a destra aritmetico i bit spostati oltre la posizione del bit più a destra vengono eliminati e il bit più a sinistra (segno) viene propagato nelle posizioni dei bit sgomberate a sinistra. Ciò significa che se `pattern` ha un valore negativo, le posizioni sgomberate sono impostate su una; in caso contrario, vengono impostati su zero.  
  
 Si noti che i tipi di dati `Byte`, `UShort`, `UInteger`e `ULong` non sono firmati, pertanto non è presente alcun bit di segno da propagare. Se `pattern` è di un tipo senza segno, le posizioni sgomberate vengono sempre impostate su zero.  
  
 Per impedire lo spostamento di più bit rispetto al risultato, Visual Basic maschera il valore di `amount` con una maschera di dimensioni corrispondente al tipo di dati di `pattern`. Il file binario e di questi valori viene utilizzato per l'importo dello spostamento. Le maschere delle dimensioni sono le seguenti:  
  
|Tipo di dati di `pattern`|Maschera dimensioni (decimale)|Maschera dimensioni (esadecimale)|  
|----------------------------|---------------------------|-------------------------------|  
|`SByte`, `Byte`|7|& H00000007|  
|`Short`, `UShort`|15|& H0000000F|  
|`Integer`, `UInteger`|31|& H0000001F|  
|`Long`, `ULong`|63|& H0000003F|  
  
 Se `amount` è uguale a zero, il valore di `result` è identico al valore di `pattern`. Se `amount` è negativo, viene considerato come un valore senza segno e mascherato con la maschera di dimensioni appropriata.  
  
 I turni aritmetici non generano mai eccezioni di overflow.  
  
## <a name="overloading"></a>Overload  
 L'operatore `>>` può essere sottoposto a *Overload*, il che significa che una classe o una struttura può ridefinire il comportamento quando un operando ha il tipo della classe o della struttura. Se il codice usa questo operatore su una classe o una struttura di questo tipo, assicurarsi di comprendere il comportamento ridefinito. Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene usato l'operatore `>>` per eseguire turni aritmetici a destra su valori integrali. Il risultato ha sempre lo stesso tipo di dati dell'espressione spostata.  
  
 [!code-vb[VbVbalrOperators#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#14)]  
  
 I risultati dell'esempio precedente sono i seguenti:  
  
- `result1` è 2560 (0000 1010 0000 0000).  
  
- `result2` è 160 (0000 0000 1010 0000).  
  
- `result3` è 2 (0000 0000 0000 0010).  
  
- `result4` è 640 (0000 0010 1000 0000).  
  
- `result5` è 0 (spostato di 15 posizioni a destra).  
  
 Il valore di Shift per `result4` viene calcolato come 18 e 15, che è uguale a 2.  
  
 Nell'esempio seguente vengono illustrati i turni aritmetici su un valore negativo.  
  
 [!code-vb[VbVbalrOperators#55](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#55)]  
  
 I risultati dell'esempio precedente sono i seguenti:  
  
- `negresult1` è-512 (1111 1110 0000 0000).  
  
- `negresult2` è-1 (il bit di segno viene propagato).  
  
## <a name="see-also"></a>Vedere anche

- [Operatori di spostamento bit](../../../visual-basic/language-reference/operators/bit-shift-operators.md)
- [Operatori di assegnazione](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [Operatore >>=](../../../visual-basic/language-reference/operators/right-shift-assignment-operator.md)
- [Precedenza tra gli operatori in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Elenco degli operatori per funzionalità](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Operatori aritmetici in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
