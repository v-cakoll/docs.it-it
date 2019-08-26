---
title: Operatori - Guida per programmatori C#
ms.custom: seodec18
ms.date: 04/30/2019
helpviewer_keywords:
- operators [C#]
- C# language, operators
- operators [C#], about operators
ms.assetid: 214e7b83-1a41-4f7c-9867-64e9c0bab39f
ms.openlocfilehash: 4870c744383205c2b7e3832c01fb838a545f085f
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/19/2019
ms.locfileid: "69588616"
---
# <a name="operators-c-programming-guide"></a>Operatori (Guida per programmatori C#)

Nel linguaggio C# un *operatore* è un elemento del programma che si applica a uno o più *operandi* in un'espressione o in un'istruzione. Gli operatori che accettano un unico operando, ad esempio l'operatore di incremento (`++`) o `new`, sono denominati operatori *unari* . Quelli che accettano due operandi, ad esempio gli operatori aritmetici (`+`,`-`,`*`,`/`), sono denominati operatori *binari* . L'operatore condizionale (`?:`) accetta tre operandi ed è l'unico operatore ternario disponibile in C#.  
  
 L'istruzione C# riportata di seguito contiene un unico operatore unario e un unico operando. L'operatore di incremento `++`modifica il valore dell'operando `y`.  
  
 [!code-csharp[csProgGuideStatements#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#5)]  
  
 L'istruzione C# riportata di seguito contiene due operatori binari, ciascuno con due operandi. L'operatore di assegnazione `=`ha come operandi la variabile integer `y` e l'espressione `2 + 3` . L'espressione `2 + 3` è costituita dall'operatore di addizione e due operandi, `2` e `3`.  
  
 [!code-csharp[csProgGuideStatements#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#6)]  
  
Un operando può essere un'espressione valida composta da codice di qualsiasi lunghezza e può includere un numero qualsiasi di sottoespressioni. In un'espressione che contiene più operatori, l'ordine in cui vengono applicati gli operatori è determinata dalla *precedenza tra operatori*, l' *associatività*e le parentesi.  

## <a name="operator-precedence"></a>Precedenza tra gli operatori
  
Ogni operatore ha una precedenza definita. In un'espressione che contiene più operatori che dispongono di diversi livelli di precedenza, la precedenza degli operatori determina l'ordine in cui gli operatori verranno valutati. L'istruzione che segue, ad esempio, assegna il valore 3 a `n1`:

```csharp
n1 = 11 - 2 * 4;
```

La moltiplicazione viene eseguita per prima perché ha la precedenza sulla sottrazione.

Per l'elenco completo degli operatori C# ordinati in base al livello di precedenza, vedere [Operatori C#](../../language-reference/operators/index.md).
  
## <a name="associativity"></a>Associazione

 Quando in un'espressione sono presenti due o più operatori con la stessa precedenza, verranno valutati in base all'associazione. Gli operatori che prevedono l'associazione all'operando sinistro vengono valutati nell'ordine da sinistra a destra. L'espressione `x * y / z` viene ad esempio valutata come `(x * y) / z`. Gli operatori che prevedono l'associazione all'operando destro vengono valutati nell'ordine da destra a sinistra. Ad esempio, l'operatore di assegnazione prevede l'associazione all'operando destro. Se non fosse così, il codice seguente restituirà un errore.  
  
```csharp  
int a, b, c;  
c = 1;  
// The following two lines are equivalent.  
a = b = c;  
a = (b = c);  
  
// The following line, which forces left associativity, causes an error.  
//(a = b) = c;  
```  
  
 Facendo un altro esempio, l'operatore ternario ([?:](../../language-reference/operators/conditional-operator.md)) prevede l'associazione all'operando destro. La maggior parte degli operatori binari prevede l'associazione all'operando sinistro.  
  
 Se gli operatori in un'espressione sono impostati su associativo o associativo da destra, gli operandi di ogni espressione vengono valutati per primi, da sinistra a destra. Negli esempi seguenti viene illustrato l'ordine di valutazione degli operatori e degli operandi.  
  
|Istruzione|Ordine di valutazione|  
|---------------|-------------------------|  
|`a = b`|a, b, =|  
|`a = b + c`|a, b, c, +, =|  
|`a = b + c * d`|a, b, c, d, *, +, =|  
|`a = b * c + d`|a, b, c, *, d, +, =|  
|`a = b - c + d`|a, b, c, -, d, +, =|  
|`a += b -= c`|a, b, c, -=, +=|  
  
## <a name="adding-parentheses"></a>Aggiunta di parentesi

 È possibile modificare l'ordine imposto dalla precedenza degli operatori e dall'associatività usando le parentesi. Ad esempio, il risultato dell'espressione `2 + 3 * 2` restituisce normalmente 8, in quanto gli operatori di moltiplicazione hanno la precedenza su quelli di addizione. Tuttavia, se si scrive l'espressione in questo modo `(2 + 3) * 2`, l'addizione è presa in considerazione prima della moltiplicazione e il risultato sarà 10. Negli esempi seguenti viene illustrato l'ordine di valutazione delle espressioni tra parentesi. Come negli esempi precedenti, gli operandi vengono valutati prima di applicare l'operatore.  
  
|Istruzione|Ordine di valutazione|  
|---------------|-------------------------|  
|`a = (b + c) * d`|a, b, c, +, d, *, =|  
|`a = b - (c + d)`|a, b, c, d, +, -, =|  
|`a = (b + c) * (d - e)`|a, b, c, +, d, e, -, *, =|  
  
## <a name="operator-overloading"></a>Overload degli operatori

È possibile definire il comportamento di determinati operatori per classi e struct personalizzati. Questo processo è denominato *overload degli operatori*. Per altre informazioni, vedere [Overload degli operatori](../../language-reference/operators/operator-overloading.md).
  
## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../index.md)
- [Istruzioni, espressioni e operatori](index.md)
- [Operatori C#](../../language-reference/operators/index.md)
