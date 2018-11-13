---
title: 'Operatore ?: (Riferimenti per C#)'
ms.date: 07/20/2015
f1_keywords:
- ?:_CSharpKeyword
- ?_CSharpKeyword
- :_CSharpKeyword
helpviewer_keywords:
- '?: operator [C#]'
- conditional operator (?:) [C#]
ms.assetid: e83a17f1-7500-48ba-8bee-2fbc4c847af4
ms.openlocfilehash: 3e45ff6eaaefa5829c3ed9415abe1a12b7a1d069
ms.sourcegitcommit: 4bca8f7e172fd019ef437a4803bf5895c6bc4781
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2018
ms.locfileid: "50980622"
---
# <a name="-operator-c-reference"></a>Operatore ?: (Riferimenti per C#)

L'operatore condizionale (`?:`), noto come operatore condizionale ternario, restituisce uno di due valori in base al valore di un'espressione booleana. Di seguito è riportata la sintassi per l'operatore condizionale.  

```csharp
condition ? first_expression : second_expression;  
```

A partire da C# 7.2, `first_expression` e `second_expression` possono essere [espressioni `ref`](https://github.com/dotnet/csharplang/blob/master/proposals/csharp-7.2/conditional-ref.md):

```csharp
ref condition ? ref first_expression : ref second_expression;  
```

Il risultato può essere assegnato a una variabile `ref` o `ref readonly` o a una variabile senza modificatori.

## <a name="remarks"></a>Note

L' oggetto `condition` deve restituire `true` o `false`. Se `condition` è `true`, `first_expression` viene valutato e diventa il risultato. Se `condition` è `false`, `second_expression` viene valutato e diventa il risultato. Viene valutata soltanto una delle due espressioni. Ciò è particolarmente importante per le espressioni in cui il risultato è `ref`, come la seguente espressione valida:

```csharp
ref (storage != null) ? ref storage[3] : ref defaultValue;
```

Il riferimento a `storage` non viene valutato quando `storage` è Null.

Quando il risultato è un valore, il tipo di `first_expression` e `second_expression` deve corrispondere oppure deve essere presente una conversione implicita da un tipo all'altro. Quando il risultato è `ref`, il tipo di `first_expression` e `second_expression` deve corrispondere.

I calcoli che richiedono una costruzione `if-else` possono essere espressi più concisamente mediante l'operatore condizionale. Ad esempio, il codice seguente viene utilizzato prima un'istruzione `if`, quindi un operatore condizionale per classificare un integer come positivo o negativo.

```csharp
int input = Convert.ToInt32(Console.ReadLine());  
string classify;  
  
// if-else construction.  
if (input > 0)  
    classify = "positive";  
else  
    classify = "negative";  
  
// ?: conditional operator.  
classify = (input > 0) ? "positive" : "negative";  
```

L'operatore condizionale si associa all'operando a destra. L'espressione `a ? b : c ? d : e` viene valutata come `a ? b : (c ? d : e)`, non come `(a ? b : c) ? d : e`.  
  
Non è possibile eseguire l'overload dell'operatore condizionale.
  
## <a name="example"></a>Esempio

L'esempio seguente illustra l'operatore condizionale il cui risultato è un valore:

[!code-csharp[csRefOperators?:](~/samples/snippets/csharp/language-reference/operators/ConditionalExamples.cs#ConditionalValue)]

L'alternativa seguente illustra l'operatore condizionale il cui risultato è un riferimento:

[!code-csharp[csRefOperatorsRef?:](~/samples/snippets/csharp/language-reference/operators/ConditionalExamples.cs#ConditionalRef)]

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../../../csharp/language-reference/index.md)  
- [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
- [Operatori C#](../../../csharp/language-reference/operators/index.md)  
- [if-else](../../../csharp/language-reference/keywords/if-else.md)  
- [Operatori ?. e ?[]](../../../csharp/language-reference/operators/null-conditional-operators.md)  
- [?? (operatore)](../../../csharp/language-reference/operators/null-coalescing-operator.md)
