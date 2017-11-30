---
title: Precedenza tra gli operatori in Visual Basic
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 6c0fb466b404cafdd4b91d061971fd683375c715
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="operator-precedence-in-visual-basic"></a>Precedenza tra gli operatori in Visual Basic
Quando vengono eseguite operazioni diverse in un'espressione, ogni parte viene valutata e risolta in un ordine predeterminato definito *precedenza degli operatori*.  
  
## <a name="precedence-rules"></a>Regole di precedenza  
 Se un'espressione contiene operatori da più di una categoria, vengono valutati in base alle regole seguenti:  
  
-   Gli operatori aritmetici e di concatenazione hanno l'ordine di precedenza descritta nella sezione seguente, e hanno maggiore precedenza rispetto a confronto, logici e bit per bit.  
  
-   Tutti gli operatori di confronto hanno la stessa precedenza e precedenza maggiore rispetto agli operatori logici e bit per bit, ma con precedenza inferiore rispetto agli operatori aritmetici e di concatenazione.  
  
-   Gli operatori logici e bit per bit di ordine di precedenza descritta nella sezione seguente e tutti gli aritmetica, di concatenazione e gli operatori di confronto.  
  
-   Gli operatori con uguale precedenza vengono valutati da sinistra a destra nell'ordine in cui appaiono nell'espressione.  
  
## <a name="precedence-order"></a>Ordine di precedenza  
 Gli operatori vengono valutati nell'ordine di precedenza seguente:  
  
### <a name="await-operator"></a>Operatore Await  
 Await  
  
### <a name="arithmetic-and-concatenation-operators"></a>Operazioni aritmetiche e concatenazione (operatori)  
 Elevamento a potenza (`^`)  
  
 Unario identità e negazione (`+`, `–`)  
  
 Moltiplicazione e divisione a virgola mobile (`*`, `/`)  
  
 Divisione di interi (`\`)  
  
 Il modulo aritmetico (`Mod`)  
  
 Addizione e sottrazione (`+`, `–`)  
  
 Concatenazione di stringhe (`&`)  
  
 Bit aritmetico (`<<`, `>>`)  
  
### <a name="comparison-operators"></a>Operatori di confronto  
 Tutti gli operatori di confronto (`=`, `<>`, `<`, `<=`, `>`, `>=`, `Is`, `IsNot`, `Like`, `TypeOf`... `Is`)  
  
### <a name="logical-and-bitwise-operators"></a>Operatori logici e bit per bit  
 Negazione (`Not`)  
  
 Insieme (`And`, `AndAlso`)  
  
 Disgiunzione (`Or`, `OrElse`)  
  
 Disgiunzione (`Xor`)  
  
### <a name="comments"></a>Commenti  
 Il `=` operatore è solo l'operatore di confronto uguaglianza, non l'operatore di assegnazione.  
  
 L'operatore di concatenazione di stringhe (`&`) non è un operatore aritmetico, ma in precedenza si è raggruppato con gli operatori aritmetici.  
  
 Il `Is` e `IsNot` gli operatori sono gli operatori di confronto di riferimento di oggetto. Essi non confrontare i valori di due oggetti. si verifica solo per determinare se due variabili di oggetti si riferiscono alla stessa istanza dell'oggetto.  
  
## <a name="associativity"></a>Associazione  
 Quando gli operatori uguale precedenza compaiono insieme in un'espressione, ad esempio una moltiplicazione e divisione, il compilatore valuta ogni operazione che viene rilevato da sinistra a destra. Questa condizione è illustrata nell'esempio seguente.  
  
```  
Dim n1 As Integer = 96 / 8 / 4  
Dim n2 As Integer = (96 / 8) / 4  
Dim n3 As Integer = 96 / (8 / 4)  
```  
  
 La prima espressione valuta la divisione 96 / 8 (che restituisce 12) e quindi la divisione 12 / 4, che restituisce 3. Poiché il compilatore valuta le operazioni per `n1` da sinistra a destra, la valutazione è lo stesso quando tale ordine è indicato in modo esplicito per `n2`. Entrambi `n1` e `n2` producono un risultato di tre. Al contrario, `n3` il risultato di 48, perché le parentesi forzano il compilatore può valutare 8 / 4 prima.  
  
 Questo comportamento, gli operatori sono definiti a *lasciato associativa* in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].  
  
## <a name="overriding-precedence-and-associativity"></a>Si esegue l'override di precedenza e associatività  
 È possibile utilizzare parentesi per forzare alcune parti di un'espressione da valutare prima degli altri. Questo consente di ignorare l'ordine di precedenza sia l'associazione a sinistra. [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]esegue sempre le operazioni che vengono racchiusi tra parentesi prima di quelli all'esterno. Tuttavia, all'interno delle parentesi, viene mantenuta la precedenza e associatività, a meno di utilizzare le parentesi all'interno delle parentesi. Questa condizione è illustrata nell'esempio seguente.  
  
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
 [Operatore =](../../../visual-basic/language-reference/operators/assignment-operator.md)  
 [Operatore Is](../../../visual-basic/language-reference/operators/is-operator.md)  
 [Operatore IsNot](../../../visual-basic/language-reference/operators/isnot-operator.md)  
 [Operatore Like](../../../visual-basic/language-reference/operators/like-operator.md)  
 [Operatore TypeOf](../../../visual-basic/language-reference/operators/typeof-operator.md)  
 [Operatore Await](../../../visual-basic/language-reference/operators/await-operator.md)  
 [Elenco degli operatori per funzionalità](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Operatori ed espressioni](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
