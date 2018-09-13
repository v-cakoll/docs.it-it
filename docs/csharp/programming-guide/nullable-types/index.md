---
title: Tipi nullable (Guida per programmatori C#)
description: Informazioni sui tipi nullable C# e su come usarli
ms.date: 07/30/2018
helpviewer_keywords:
- nullable types [C#]
- C# language, nullable types
- types [C#], nullable
ms.assetid: e473cb01-28ca-42be-9cea-f717055d72c6
ms.openlocfilehash: 2af0704abcad00c75a5d40bfe2d0523d07ee6a3f
ms.sourcegitcommit: ba5c189bf44d44204a3e8838e59ec378a62d82f3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/12/2018
ms.locfileid: "44700807"
---
# <a name="nullable-types-c-programming-guide"></a>Tipi nullable (Guida per programmatori C#)

I tipi nullable sono istanze dello struct <xref:System.Nullable%601?displayProperty=nameWithType>. I tipi nullable possono rappresentare tutti i valori di un tipo sottostante `T` e un valore [null](../../language-reference/keywords/null.md) aggiuntivo. Il tipo sottostante `T` può essere qualsiasi [tipo valore](../../language-reference/keywords/value-types.md) non nullable. `T` non può essere un tipo riferimento.

È ad esempio possibile assegnare `null` o qualsiasi valore integer compreso tra <xref:System.Int32.MinValue?displayProperty=nameWithType> e <xref:System.Int32.MaxValue?displayProperty=nameWithType> a `Nullable<int>` e [true](../../language-reference/keywords/true-literal.md), [false](../../language-reference/keywords/false-literal.md) o `null` a `Nullable<bool>`.

Un tipo nullable viene usato quando è necessario rappresentare il valore non definito di un tipo sottostante. Una variabile booleana può avere solo due valori: true e false. Non è previsto alcun valore "non definito". In molte applicazioni di programmazione, in particolare nelle interazioni tra database, un valore di variabile può essere non definito o mancante. Ad esempio un campo di un database può contenere i valori true o false oppure è possibile che non contenga alcun valore. In tale caso si usa un tipo `Nullable<bool>`.

I tipi nullable hanno le caratteristiche seguenti:
  
- I tipi nullable rappresentano variabili di tipo valore a cui può essere assegnato il valore `null`. Non è possibile creare un tipi nullable sulla base di un tipo riferimento. I tipi riferimento supportano già il valore `null`.  
  
- La sintassi `T?` è un'abbreviazione per `Nullable<T>`. Le due forme sono intercambiabili.  
  
- Per assegnare un valore a un tipo nullable è possibile seguire la stessa procedura adottata per un tipo valore sottostante: `int? x = 10;` o `double? d = 4.108;`. È anche possibile assegnare il valore `null`: `int? x = null;`.  
  
- Usare le proprietà di sola lettura <xref:System.Nullable%601.HasValue%2A?displayProperty=nameWithType> e <xref:System.Nullable%601.Value%2A?displayProperty=nameWithType> per verificare la presenza di valori null e recuperare il valore, come illustrato nell'esempio seguente: `if (x.HasValue) y = x.Value;`  
  
  - La proprietà <xref:System.Nullable%601.HasValue%2A> restituisce `true` se la variabile contiene un valore o `false` se è `null`.
  
  - La proprietà <xref:System.Nullable%601.Value%2A> restituisce un valore se <xref:System.Nullable%601.HasValue%2A> restituisce `true`. In caso contrario, verrà generata un'eccezione <xref:System.InvalidOperationException>.  
  
- Con un tipo nullable è anche possibile usare gli operatori `==` e `!=`, come mostrato nell'esempio seguente: `if (x != null) y = x.Value;`. Se `a` e `b` sono Null, `a == b` restituisce `true`.  

- A partire da C# 7.0, è possibile usare i [criteri di ricerca](../../pattern-matching.md#the-is-type-pattern-expression) per esaminare e ottenere un valore di un tipo nullable: `if (x is int valueOfX) y = valueOfX;`.
  
- Il valore predefinito di `T?` è un'istanza la cui proprietà <xref:System.Nullable%601.HasValue%2A> restituisce `false`.  

- Usare il metodo <xref:System.Nullable%601.GetValueOrDefault> per restituire il valore assegnato oppure il valore [predefinito](../../language-reference/keywords/default-values-table.md) del tipo valore sottostante se il valore del tipo nullable è `null`.  

- Usare il metodo <xref:System.Nullable%601.GetValueOrDefault(%600)> per restituire il valore assegnato oppure il valore predefinito specificato se il valore del tipo nullable è `null`.
  
- Usare l'[operatore di unione Null](../../language-reference/operators/null-coalescing-operator.md), `??`, per assegnare un valore al tipo sottostante in base al valore del tipo nullable: `int? x = null; int y = x ?? -1;`. Poiché `x` è Null, nell'esempio il valore restituito di `y` è `-1`.

- Se viene impostata una conversione definita dall'utente tra due tipi di dati, la stessa conversione può essere usata anche con le versioni nullable di questi tipi di dati.
  
- I tipi nullable nidificati non sono consentiti. La riga seguente non verrà compilata: `Nullable<Nullable<int>> n;`  

Per altre informazioni, vedere gli argomenti [Utilizzo dei tipi nullable](using-nullable-types.md) e [Procedura: Identificare un tipo nullable](how-to-identify-a-nullable-type.md).
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Nullable%601?displayProperty=nameWithType>  
- <xref:System.Nullable?displayProperty=nameWithType>  
- [?? (operatore)](../../language-reference/operators/null-coalescing-operator.md)  
- [Guida per programmatori C#](../index.md)  
- [Guida a C#](../../index.md)  
- [Riferimenti per C#](../../language-reference/index.md)  
- [Tipi di valori nullable (Visual Basic)](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)  
