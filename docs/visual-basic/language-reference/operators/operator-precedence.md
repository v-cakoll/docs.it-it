---
title: Precedenza tra gli operatori
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
ms.openlocfilehash: 318fcc3f35276ba0b2061ba9677c5fde29429f6f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348270"
---
# <a name="operator-precedence-in-visual-basic"></a>Precedenza tra gli operatori in Visual Basic
Quando più operazioni si verificano in un'espressione, ogni parte viene valutata e risolta in base a un ordine predeterminato denominato *precedenza degli operatori*.

## <a name="precedence-rules"></a>Regole di precedenza
 Quando le espressioni contengono operatori di più di una categoria, vengono valutate in base alle regole seguenti:

- Gli operatori aritmetici e di concatenazione hanno l'ordine di precedenza descritto nella sezione seguente e hanno tutti una maggiore precedenza rispetto agli operatori di confronto, logici e bit per bit.

- Tutti gli operatori di confronto hanno uguale precedenza e hanno una precedenza maggiore rispetto agli operatori logici e bit per bit, ma con precedenza più bassa rispetto agli operatori aritmetici e di concatenazione.

- Gli operatori logici e bit per bit hanno l'ordine di precedenza descritto nella sezione seguente e hanno una precedenza più bassa rispetto agli operatori aritmetici, di concatenazione e di confronto.

- Gli operatori con uguale precedenza vengono valutati da sinistra a destra nell'ordine in cui sono visualizzati nell'espressione.

## <a name="precedence-order"></a>Ordine di precedenza
 Gli operatori vengono valutati nel seguente ordine di precedenza:

### <a name="await-operator"></a>Operatore Await
 Attendono

### <a name="arithmetic-and-concatenation-operators"></a>Operatori aritmetici e di concatenazione
 Elevamento a potenza (`^`)

 Identità e negazione unari (`+`, `–`)

 Divisione a virgola mobile e moltiplicazione (`*`, `/`)

 Divisione di interi (`\`)

 Aritmetica modulare (`Mod`)

 Addizione e sottrazione (`+`, `–`)

 Concatenazione di stringhe (`&`)

 Spostamento di bit aritmetico (`<<`, `>>`)

### <a name="comparison-operators"></a>Operatori di confronto
 Tutti gli operatori di confronto (`=`, `<>`, `<`, `<=`, `>`, `>=`, `Is`, `IsNot`, `Like`, `TypeOf`...`Is`)

### <a name="logical-and-bitwise-operators"></a>Operatori logici e bit per bit
 Negazione (`Not`)

 Congiunzione (`And`, `AndAlso`)

 Disgiunzione inclusiva (`Or`, `OrElse`)

 Disgiunzione esclusiva (`Xor`)

### <a name="comments"></a>Comments
 L'operatore `=` è solo l'operatore di confronto di uguaglianza, non l'operatore di assegnazione.

 L'operatore di concatenazione delle stringhe (`&`) non è un operatore aritmetico, ma in precedenza è raggruppato con gli operatori aritmetici.

 Gli operatori `Is` e `IsNot` sono operatori di confronto dei riferimenti agli oggetti. Non confrontano i valori di due oggetti; controllano solo per determinare se due variabili oggetto fanno riferimento alla stessa istanza dell'oggetto.

## <a name="associativity"></a>associatività
 Quando gli operatori con la stessa precedenza vengono visualizzati insieme in un'espressione, ad esempio moltiplicazione e divisione, il compilatore valuta ogni operazione quando viene rilevata da sinistra verso destra. Ciò è illustrato nell'esempio seguente.

```vb
Dim n1 As Integer = 96 / 8 / 4
Dim n2 As Integer = (96 / 8) / 4
Dim n3 As Integer = 96 / (8 / 4)
```

 La prima espressione valuta la divisione 96/8 (che restituisce 12), quindi la divisione 12/4, che produce tre. Poiché il compilatore valuta le operazioni per `n1` da sinistra a destra, la valutazione è la stessa quando tale ordine è indicato in modo esplicito per `n2`. Sia `n1` che `n2` hanno un risultato di tre. Al contrario, `n3` ha un risultato di 48, perché le parentesi forzano il compilatore a valutare prima di tutto 8/4.

 A causa di questo comportamento, gli operatori vengono definiti *associativi a sinistra* in Visual Basic.

## <a name="overriding-precedence-and-associativity"></a>Override della precedenza e dell'associatività
 È possibile utilizzare le parentesi per forzare la valutazione di alcune parti di un'espressione prima di altre. Questo può sostituire l'ordine di precedenza e l'associatività a sinistra. Visual Basic esegue sempre le operazioni racchiuse tra parentesi prima di quelle esterne a. Tuttavia, tra parentesi, gestisce la precedenza e l'associatività ordinarie, a meno che non si utilizzino le parentesi all'interno delle parentesi. Ciò è illustrato nell'esempio seguente.

```vb
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
