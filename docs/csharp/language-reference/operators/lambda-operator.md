---
title: Operatore => Riferimenti per C#
ms.date: 01/22/2019
f1_keywords:
- =>_CSharpKeyword
helpviewer_keywords:
- lambda operator [C#]
- => operator [C#]
- lambda expressions [C#], => operator
ms.openlocfilehash: 15c02e11610866f359e3e3a7e2751ded918154b7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "78846253"
---
# <a name="-operator-c-reference"></a>Operatore => (Riferimenti per C#)

Il `=>` token è supportato in due formati: come [operatore lambda](#lambda-operator) e come separatore del nome di un membro e dell'implementazione del membro in una definizione del [corpo dell'espressione.](#expression-body-definition)

## <a name="lambda-operator"></a>Operatore lambda

Nelle [espressioni lambda](../../programming-guide/statements-expressions-operators/lambda-expressions.md), `=>` l'operatore lambda separa i parametri di input sul lato sinistro dal corpo dell'espressione lambda sul lato destro.

L'esempio seguente illustra l'utilizzo delle espressioni lambda tramite la funzionalità [LINQ](../../programming-guide/concepts/linq/index.md) con la sintassi dei metodi:

[!code-csharp-interactive[infer types of input variables](snippets/LambdaOperator.cs#InferredTypes)]

I parametri di input di un'espressione lambda sono fortemente tipizzati in fase di compilazione. Quando il compilatore può dedurre i tipi di parametri di input, come nell'esempio precedente, è possibile omettere le dichiarazioni di tipo. Se è necessario specificare il tipo di parametri di input, è necessario farlo per ogni parametro, come illustrato nell'esempio seguente:

[!code-csharp-interactive[specify types of input variables](snippets/LambdaOperator.cs#ExplicitTypes)]

L'esempio seguente mostra come definire un'espressione lambda senza parametri di input:The following example shows how to define a lambda expression without input parameters:

[!code-csharp-interactive[without input variables](snippets/LambdaOperator.cs#WithoutInput)]

Per altre informazioni, vedere [Espressioni lambda](../../programming-guide/statements-expressions-operators/lambda-expressions.md).

## <a name="expression-body-definition"></a>Definizione del corpo dell'espressione

Una definizione di corpo di espressione presenta la seguente sintassi generale:

```csharp
member => expression;
```

dove `expression` è un'espressione valida. Il tipo restituito di `expression` deve essere convertibile in modo implicito nel tipo restituito del membro. Se il tipo restituito `void` del membro è o se il membro è `set` un `expression` costruttore, un finalizzatore o una funzione di accesso alla proprietà, deve essere [*un'espressione*](~/_csharplang/spec/statements.md#expression-statements)di istruzione , che può essere di qualsiasi tipo.

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

Le definizioni del corpo dell'espressione per metodi, operatori e proprietà di sola lettura sono supportate a partire da C . Le definizioni del corpo dell'espressione per i costruttori, i finalizzatori e le funzioni di accesso di proprietà e indicizzatore sono supportate a partire da C .

Per altre informazioni, vedere [Membri con corpo di espressione](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).

## <a name="operator-overloadability"></a>Overload degli operatori

Non è possibile eseguire l'overload dell'operatore `=>`.

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per ulteriori informazioni sull'operatore lambda, vedere la sezione [Espressioni di funzione anonime](~/_csharplang/spec/expressions.md#anonymous-function-expressions) della specifica del [linguaggio C.](~/_csharplang/spec/introduction.md)

## <a name="see-also"></a>Vedere anche

- [Informazioni di riferimento su C#](../index.md)
- [Operatori C#](index.md)
