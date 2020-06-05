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
ms.openlocfilehash: 10b07da22b8b43d6a966fa7c334ac6a0ef4b430d
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406366"
---
# <a name="-operator-visual-basic"></a>Operatore >> (Visual Basic)
Esegue uno spostamento a destra aritmetico in uno schema di bit.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
result = pattern >> amount  
```  
  
## <a name="parts"></a>Parti  
 `result`  
 Obbligatorio. Valore numerico integrale. Risultato dello spostamento dello schema di bit. Il tipo di dati corrisponde a quello di `pattern`.  
  
 `pattern`  
 Obbligatorio. Espressione numerica integrale. Schema di bit da spostare. Il tipo di dati deve essere integrale (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long` o `ULong`).  
  
 `amount`  
 Obbligatorio. Espressione numerica. Numero di bit per spostare lo schema di bit. Il tipo di dati deve essere `Integer` o ampliato a `Integer`.  
  
## <a name="remarks"></a>Commenti  
 I turni aritmetici non sono circolari, il che significa che i bit spostati da un'estremità del risultato non vengono reintrodotti nell'altra estremità. In uno spostamento a destra aritmetico i bit spostati oltre la posizione del bit più a destra vengono eliminati e il bit più a sinistra (segno) viene propagato nelle posizioni dei bit sgomberate a sinistra. Ciò significa che se `pattern` ha un valore negativo, le posizioni sgomberate sono impostate su una. in caso contrario, vengono impostate su zero.  
  
 Si noti che i tipi `Byte` di dati,, `UShort` `UInteger` e `ULong` sono senza segno, quindi non esiste alcun bit di segno da propagare. Se `pattern` è di un tipo senza segno, le posizioni sgomberate vengono sempre impostate su zero.  
  
 Per impedire lo spostamento di più bit rispetto al risultato, Visual Basic maschera il valore di `amount` con una maschera di dimensioni corrispondente al tipo di dati di `pattern` . Il file binario e di questi valori viene utilizzato per l'importo dello spostamento. Le maschere delle dimensioni sono le seguenti:  
  
|Tipo di dati di`pattern`|Maschera dimensioni (decimale)|Maschera dimensioni (esadecimale)|  
|----------------------------|---------------------------|-------------------------------|  
|`SByte`, `Byte`|7|&H00000007|  
|`Short`, `UShort`|15|&H0000000F|  
|`Integer`, `UInteger`|31|&H0000001F|  
|`Long`, `ULong`|63|&H0000003F|  
  
 Se `amount` è zero, il valore di `result` è identico al valore di `pattern` . Se `amount` è negativo, viene considerato come un valore senza segno e mascherato con la maschera di dimensioni appropriata.  
  
 I turni aritmetici non generano mai eccezioni di overflow.  
  
## <a name="overloading"></a>Overload  
 L' `>>` operatore può essere sottoposto a *Overload*, il che significa che una classe o una struttura può ridefinire il comportamento quando un operando ha il tipo della classe o della struttura. Se il codice usa questo operatore su una classe o una struttura di questo tipo, assicurarsi di comprendere il comportamento ridefinito. Per altre informazioni, vedere [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene usato l' `>>` operatore per eseguire turni aritmetici a destra su valori integrali. Il risultato ha sempre lo stesso tipo di dati dell'espressione spostata.  
  
 [!code-vb[VbVbalrOperators#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#14)]  
  
 I risultati dell'esempio precedente sono i seguenti:  
  
- `result1`è 2560 (0000 1010 0000 0000).  
  
- `result2`è 160 (0000 0000 1010 0000).  
  
- `result3`è 2 (0000 0000 0000 0010).  
  
- `result4`è 640 (0000 0010 1000 0000).  
  
- `result5`è 0 (spostato di 15 posizioni a destra).  
  
 Il valore Shift per `result4` viene calcolato come 18 e 15, che è uguale a 2.  
  
 Nell'esempio seguente vengono illustrati i turni aritmetici su un valore negativo.  
  
 [!code-vb[VbVbalrOperators#55](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#55)]  
  
 I risultati dell'esempio precedente sono i seguenti:  
  
- `negresult1`is-512 (1111 1110 0000 0000).  
  
- `negresult2`è-1 (il bit di segno viene propagato).  
  
## <a name="see-also"></a>Vedere anche

- [Operatori di spostamento bit](bit-shift-operators.md)
- [Operatori di assegnazione](assignment-operators.md)
- [Operatore>>=](right-shift-assignment-operator.md)
- [Precedenza tra gli operatori in Visual Basic](operator-precedence.md)
- [Elenco degli operatori per funzionalità](operators-listed-by-functionality.md)
- [Operatori aritmetici in Visual Basic](../../programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
