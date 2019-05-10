---
title: Precedenza tra gli operatori in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- arithmetic operators [Visual Basic], precedence
- operator precedence
- logical operators [Visual Basic], precedence
- operators [Visual Basic], associativity
- operators [Visual Basic], resolution
- associativity of operators [Visual Basic]
- operators [Visual Basic], precedence
- precedence [Visual Basic], of operators
- comparison operators [Visual Basic], precedence
- math operators [Visual Basic]
- order of precedence
ms.assetid: cbbdb282-f572-458e-a520-008a675f8063
ms.openlocfilehash: 95505fd593881ff27418c69550952d072b4e3949
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64628865"
---
# <a name="operator-precedence-in-visual-basic"></a>Precedenza tra gli operatori in Visual Basic
Quando si verificano diverse operazioni in un'espressione, ogni parte viene valutata e risolti in un ordine predeterminato chiamato *precedenza degli operatori*.  
  
## <a name="precedence-rules"></a>Regole di precedenza  
 Se un'espressione contiene operatori da più di una categoria, vengono valutati in base alle regole seguenti:  
  
- Gli operatori aritmetici e di concatenazione hanno l'ordine di precedenza descritta nella sezione seguente e tutti hanno la precedenza maggiore rispetto a confronto, logici e operatori bit per bit.  
  
- Tutti gli operatori di confronto hanno uguale precedenza e hanno la precedenza maggiore rispetto agli operatori logici e bit per bit, ma la precedenza inferiore rispetto agli operatori aritmetici e di concatenazione.  
  
- Gli operatori logici e bit per bit di ordine di precedenza descritta nella sezione seguente e tutti l'aritmetica, di concatenazione e gli operatori di confronto.  
  
- Gli operatori con uguale precedenza vengono valutati da sinistra a destra nell'ordine in cui vengono visualizzati nell'espressione.  
  
## <a name="precedence-order"></a>Ordine di precedenza  
 Gli operatori vengono valutati nell'ordine di precedenza seguente:  
  
### <a name="await-operator"></a>Operatore Await  
 Await  
  
### <a name="arithmetic-and-concatenation-operators"></a>Operazioni aritmetiche e operatori di concatenazione  
 Elevamento a potenza (`^`)  
  
 Unario identità e la negazione (`+`, `–`)  
  
 Moltiplicazione e divisione a virgola mobile (`*`, `/`)  
  
 Divisione di interi (`\`)  
  
 Modulo aritmetico (`Mod`)  
  
 Addizione e sottrazione (`+`, `–`)  
  
 Concatenazione di stringhe (`&`)  
  
 Bit aritmetico (`<<`, `>>`)  
  
### <a name="comparison-operators"></a>Operatori di confronto  
 Tutti gli operatori di confronto (`=`, `<>`, `<`, `<=`, `>`, `>=`, `Is`, `IsNot`, `Like`, `TypeOf`... `Is`)  
  
### <a name="logical-and-bitwise-operators"></a>Operatori logici e bit per bit  
 Negazione (`Not`)  
  
 Conjunction (`And`, `AndAlso`)  
  
 La disgiunzione (`Or`, `OrElse`)  
  
 Disgiunzione (`Xor`)  
  
### <a name="comments"></a>Commenti  
 Il `=` operatore è solo l'operatore di confronto uguaglianza, non l'operatore di assegnazione.  
  
 L'operatore di concatenazione di stringhe (`&`) non è un operatore aritmetico, ma in precedenza viene raggruppato con gli operatori aritmetici.  
  
 Il `Is` e `IsNot` gli operatori sono gli operatori di confronto di riferimento di oggetto. Essi non confrontare i valori di due oggetti. si verifica solo per determinare se due variabili oggetto fanno riferimento alla stessa istanza dell'oggetto.  
  
## <a name="associativity"></a>Associazione  
 Quando gli operatori uguale precedenza vengono visualizzati insieme in un'espressione, ad esempio la moltiplicazione e divisione, il compilatore valuta ogni operazione che viene rilevato da sinistra a destra. Questa condizione è illustrata nell'esempio seguente.  
  
```  
Dim n1 As Integer = 96 / 8 / 4  
Dim n2 As Integer = (96 / 8) / 4  
Dim n3 As Integer = 96 / (8 / 4)  
```  
  
 La prima espressione restituisce la divisione 96 / 8 (con conseguente 12) e quindi la divisione 12 / 4, che restituisce 3. Poiché il compilatore valuterà le operazioni per `n1` da sinistra a destra, la versione di valutazione è lo stesso quando quest'ordine è indicato in modo esplicito per `n2`. Entrambe `n1` e `n2` dispone di un risultato pari a tre. Al contrario, `n3` dispone di un risultato di 48, perché le parentesi forzano il compilatore può valutare 8 / 4 prima.  
  
 A causa di questo comportamento, gli operatori sono detta *associative all'operando sinistro* in Visual Basic.  
  
## <a name="overriding-precedence-and-associativity"></a>Override della precedenza e associatività degli operatori  
 È possibile utilizzare parentesi per forzare alcune parti di un'espressione da valutare prima degli altri. Questo consente di ignorare l'ordine di precedenza sia di associatività degli operatori a sinistra. Vengono eseguite sempre le operazioni che sono racchiusi tra parentesi prima di quelli di fuori. Tuttavia, all'interno delle parentesi, viene mantenuta la precedenza e associatività degli operatori, a meno che non si usano le parentesi all'interno delle parentesi. Questa condizione è illustrata nell'esempio seguente.  
  
```  
Dim a, b, c, d, e, f, g As Double  
a = 8.0  
b = 3.0  
c = 4.0  
d = 2.0  
e = 1.0  
f = a - b + c / d * e  
' The preceding line sets f to 7.0. Because of natural operator   
' precedence and associativity, it is exactly equivalent to the   
' following line.  
f = (a - b) + ((c / d) * e)  
' The following line overrides the natural operator precedence   
' and left associativity.  
g = (a - (b + c)) / (d * e)  
' The preceding line sets g to 0.5.  
```  
  
## <a name="see-also"></a>Vedere anche

- [Operatore =](../../../visual-basic/language-reference/operators/assignment-operator.md)
- [Operatore Is](../../../visual-basic/language-reference/operators/is-operator.md)
- [Operatore IsNot](../../../visual-basic/language-reference/operators/isnot-operator.md)
- [Operatore Like](../../../visual-basic/language-reference/operators/like-operator.md)
- [Operatore TypeOf](../../../visual-basic/language-reference/operators/typeof-operator.md)
- [Operatore Await](../../../visual-basic/language-reference/operators/await-operator.md)
- [Elenco degli operatori per funzionalità](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Operatori ed espressioni](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
