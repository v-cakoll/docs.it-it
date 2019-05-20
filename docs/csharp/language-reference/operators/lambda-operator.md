---
title: Operatore => - Riferimenti per C#
ms.custom: seodec18
ms.date: 01/22/2019
f1_keywords:
- =>_CSharpKeyword
helpviewer_keywords:
- lambda operator [C#]
- => operator [C#]
- lambda expressions [C#], => operator
ms.openlocfilehash: 6e6ace55e7557e940970675c99ec4db87c124f1d
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65633895"
---
# <a name="-operator-c-reference"></a>Operatore => (Riferimenti per C#)

Il token `=>` è supportato in due forme: come operatore lambda e come separatore tra il nome di un membro e l'implementazione del membro nella definizione del corpo dell'espressione.

## <a name="lambda-operator"></a>Operatore lambda

Nelle [espressioni lambda](../../programming-guide/statements-expressions-operators/lambda-expressions.md), l'operatore lambda `=>` separa le variabili di input sul lato sinistro dal corpo dell'espressione lambda sul lato destro.

L'esempio seguente illustra l'utilizzo delle espressioni lambda tramite la funzionalità [LINQ](../../programming-guide/concepts/linq/index.md) con la sintassi dei metodi:

[!code-csharp-interactive[infer types of input variables](~/samples/snippets/csharp/language-reference/operators/LambdaOperatorExamples.cs#InferredTypes)]

Le variabili di input delle espressioni lambda vengono fortemente tipizzate in fase di compilazione. Se il compilatore è in grado di dedurre i tipi delle variabili di input, come nell'esempio precedente, è possibile omettere le dichiarazioni di tipo. Se il tipo delle variabili di input deve essere specificato, è necessario farlo per ogni variabile, come illustrato nell'esempio seguente:

[!code-csharp-interactive[specify types of input variables](~/samples/snippets/csharp/language-reference/operators/LambdaOperatorExamples.cs#ExplicitTypes)]

L'esempio seguente illustra come definire un'espressione lambda senza variabili di input:

[!code-csharp-interactive[without input variables](~/samples/snippets/csharp/language-reference/operators/LambdaOperatorExamples.cs#WithoutInput)]

Per altre informazioni, vedere [Espressioni lambda](../../programming-guide/statements-expressions-operators/lambda-expressions.md).

## <a name="expression-body-definition"></a>Definizione del corpo dell'espressione

Una definizione di corpo di espressione presenta la seguente sintassi generale:

```csharp
member => expression;
```

dove *expression* è un'espressione valida. Si noti che *expression* può essere un'*espressione di istruzione* solo se il tipo restituito del membro è `void` o se il membro è un costruttore, un finalizzatore o una funzione di accesso `set` di una proprietà.

L'esempio seguente illustra una definizione del corpo dell'espressione per un metodo `Person.ToString`:

```csharp
public override string ToString() => $"{fname} {lname}".Trim();
```

Si tratta di una versione abbreviata della definizione di metodo seguente:

```csharp
public override string ToString()
{
   return $"{fname} {lname}".Trim();
}
```

Le definizioni del corpo dell'espressione per i metodi e le proprietà di sola lettura sono supportate a partire da C# 6. Le definizioni del corpo dell'espressione per costruttori, finalizzatori, funzioni di accesso di proprietà e indicizzatori sono supportate a partire da C# 7.0.

Per altre informazioni, vedere [Membri con corpo di espressione](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).

## <a name="operator-overloadability"></a>Overload degli operatori

Non è possibile sottoporre l'operatore `=>` a overload.

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere la sezione [Espressioni di funzioni anonime](~/_csharplang/spec/expressions.md#anonymous-function-expressions) della [specifica del linguaggio C#](../language-specification/index.md).

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Operatori C#](index.md)
- [Espressioni lambda](../../programming-guide/statements-expressions-operators/lambda-expressions.md)
- [Membri con corpo di espressione](../../programming-guide/statements-expressions-operators/expression-bodied-members.md)
