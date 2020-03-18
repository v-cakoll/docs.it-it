---
title: tipo bool - Informazioni di riferimento su C
ms.date: 11/26/2019
f1_keywords:
- bool
- bool_CSharpKeyword
helpviewer_keywords:
- bool data type [C#]
- Boolean [C#]
ms.assetid: 551cfe35-2632-4343-af49-33ad12da08e2
ms.openlocfilehash: 2ba2e54a6b0f24402fc3728dfe19b548a2368830
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "78846445"
---
# <a name="bool-c-reference"></a>bool (riferimenti per C

La `bool` parola chiave type è <xref:System.Boolean?displayProperty=nameWithType> un alias per il tipo di `true` struttura `false`.NET che rappresenta un valore booleano, che può essere o .

Per eseguire operazioni logiche `bool` con valori del tipo, utilizzare operatori [logici booleani.](../operators/boolean-logical-operators.md) Il `bool` tipo è il tipo di risultato degli operatori di [confronto](../operators/comparison-operators.md) e [uguaglianza.](../operators/equality-operators.md) Un'espressione `bool` può essere un'espressione condizionale di controllo nelle istruzioni [if](../keywords/if-else.md), [do](../keywords/do.md), [while](../keywords/while.md)e [for](../keywords/for.md) e [nell'operatore `?:`condizionale ](../operators/conditional-operator.md).

Il valore predefinito `bool` del `false`tipo è .

## <a name="literals"></a>Valori letterali

È possibile `true` utilizzare `false` i valori `bool` letterali e `bool` per inizializzare una variabile o per passare un valore:You can use the and literals to initialize a variable or to pass a value:

[!code-csharp-interactive[bool literals](snippets/BoolType.cs#Literals)]

## <a name="three-valued-boolean-logic"></a>Logica booleana a tre valori

Utilizzare il `bool?` tipo nullable, se è necessario supportare la logica a tre valori, ad esempio, quando si utilizzano database che supportano un tipo booleano a tre valori. Per gli operandi `bool?`, gli operatori `&` e `|` predefiniti supportano la logica a tre valori. Per altre informazioni, vedere la sezione [Operatori logici booleani nullable](../operators/boolean-logical-operators.md#nullable-boolean-logical-operators) dell'articolo [Operatori logici booleani](../operators/boolean-logical-operators.md).

Per ulteriori informazioni sui tipi di valore nullable, vedere [Tipi di valore nullable](nullable-value-types.md).

## <a name="conversions"></a>Conversioni

In C' sono disponibili solo `bool` due conversioni che coinvolgono il tipo. Si tratta di una conversione `bool?` implicita nel tipo `bool?` nullable corrispondente e di una conversione esplicita dal tipo. Tuttavia, .NET fornisce metodi aggiuntivi che è `bool` possibile utilizzare per eseguire la conversione da o verso il tipo. Per altre informazioni, vedere la sezione [Conversione da e verso valori booleani](/dotnet/api/system.boolean#converting-to-and-from-boolean-values) della pagina di riferimento dell'API. <xref:System.Boolean?displayProperty=nameWithType>

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per ulteriori informazioni, vedere la sezione [relativa al tipo bool](~/_csharplang/spec/types.md#the-bool-type) della specifica del [linguaggio C.](~/_csharplang/spec/introduction.md)

## <a name="see-also"></a>Vedere anche

- [Informazioni di riferimento su C#](../index.md)
- [Tipi valore](value-types.md)
- [Operatori true e false](../operators/true-false-operators.md)
