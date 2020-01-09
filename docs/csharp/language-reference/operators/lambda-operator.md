---
title: Operatore => Riferimenti per C#
ms.date: 01/22/2019
f1_keywords:
- =>_CSharpKeyword
helpviewer_keywords:
- lambda operator [C#]
- => operator [C#]
- lambda expressions [C#], => operator
ms.openlocfilehash: 61cc3c3ab4f0b22c4040a9b8a025c81071f4d942
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712702"
---
# <a name="-operator-c-reference"></a>Operatore => (Riferimenti per C#)

Il token `=>` è supportato in due formati: come [operatore lambda](#lambda-operator) e come separatore di un nome di membro e dell'implementazione del membro in una [definizione del corpo dell'espressione](#expression-body-definition).

## <a name="lambda-operator"></a>Operatore lambda

Nelle [espressioni lambda](../../programming-guide/statements-expressions-operators/lambda-expressions.md)l'operatore lambda `=>` separa i parametri di input sul lato sinistro dal corpo dell'espressione lambda sul lato destro.

L'esempio seguente illustra l'utilizzo delle espressioni lambda tramite la funzionalità [LINQ](../../programming-guide/concepts/linq/index.md) con la sintassi dei metodi:

[!code-csharp-interactive[infer types of input variables](~/samples/csharp/language-reference/operators/LambdaOperator.cs#InferredTypes)]

I parametri di input di un'espressione lambda sono fortemente tipizzati in fase di compilazione. Quando il compilatore può dedurre i tipi di parametri di input, come nell'esempio precedente, è possibile omettere le dichiarazioni di tipo. Se è necessario specificare il tipo di parametri di input, è necessario eseguire questa operazione per ogni parametro, come illustrato nell'esempio seguente:

[!code-csharp-interactive[specify types of input variables](~/samples/csharp/language-reference/operators/LambdaOperator.cs#ExplicitTypes)]

Nell'esempio seguente viene illustrato come definire un'espressione lambda senza parametri di input:

[!code-csharp-interactive[without input variables](~/samples/csharp/language-reference/operators/LambdaOperator.cs#WithoutInput)]

Per altre informazioni, vedere [Espressioni lambda](../../programming-guide/statements-expressions-operators/lambda-expressions.md).

## <a name="expression-body-definition"></a>Definizione del corpo dell'espressione

Una definizione di corpo di espressione presenta la seguente sintassi generale:

```csharp
member => expression;
```

dove `expression` è un'espressione valida. Il tipo restituito di `expression` deve essere convertibile in modo implicito nel tipo restituito del membro. Se il tipo restituito del membro è `void` o se il membro è un costruttore, un finalizzatore o una proprietà `set` funzione di accesso, `expression` deve essere un' [*espressione di istruzione*](~/_csharplang/spec/statements.md#expression-statements), che può essere di qualsiasi tipo.

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

Le definizioni del corpo dell'espressione per metodi, operatori e proprietà di sola lettura sono supportate C# a partire da 6. Le definizioni del corpo dell'espressione per costruttori, finalizzatori e funzioni di accesso a proprietà e indicizzatori sono C# supportate a partire da 7,0.

Per altre informazioni, vedere [Membri con corpo di espressione](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).

## <a name="operator-overloadability"></a>Overload degli operatori

Non è possibile eseguire l'overload dell'operatore `=>`.

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per ulteriori informazioni sull'operatore lambda, vedere la sezione [espressioni di funzione anonime](~/_csharplang/spec/expressions.md#anonymous-function-expressions) della [ C# specifica del linguaggio](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Operatori C#](index.md)
