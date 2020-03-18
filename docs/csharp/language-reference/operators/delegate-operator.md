---
title: Operatore delegate - Riferimenti per C#
ms.date: 07/18/2019
helpviewer_keywords:
- delegate [C#]
- anonymous method [C#]
ms.openlocfilehash: 1dd27fe5fdfdc1bc8a63e1298da00d252e800a72
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "78847339"
---
# <a name="delegate-operator-c-reference"></a>Operatore delegate (Riferimenti per C#)

L'operatore `delegate` crea un metodo anonimo che può essere convertito in un tipo delegato:

[!code-csharp-interactive[anonymous method](snippets/DelegateOperator.cs#AnonymousMethod)]

> [!NOTE]
> A partire da C# 3, le espressioni lambda forniscono un modo più conciso ed espressivo per creare una funzione anonima. Usare l'[operatore =>](lambda-operator.md) per costruire un'espressione lambda:
>
> [!code-csharp-interactive[lambda expression](snippets/DelegateOperator.cs#Lambda)]
>
> Per altre informazioni sulle funzionalità delle espressioni lambda, ad esempio l'acquisizione di variabili esterne, vedere [Espressioni lambda](../../programming-guide/statements-expressions-operators/lambda-expressions.md).

Quando si usa l'operatore `delegate`, è possibile omettere l'elenco di parametri. In tal caso, il metodo anonimo creato può essere convertito in un tipo delegato con qualsiasi elenco di parametri, come illustrato nell'esempio seguente:

[!code-csharp-interactive[no parameter list](snippets/DelegateOperator.cs#WithoutParameterList)]

Questa è l'unica funzionalità di metodi anonimi non supportata dalle espressioni lambda. In tutti gli altri casi, un'espressione lambda è la modalità preferita per scrivere codice inline.

È anche possibile usare la parola chiave `delegate` per dichiarare un [tipo delegato](../builtin-types/reference-types.md#the-delegate-type).

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere la sezione [Espressioni di funzioni anonime](~/_csharplang/spec/expressions.md#anonymous-function-expressions) della [specifica del linguaggio C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Vedere anche

- [Informazioni di riferimento su C#](../index.md)
- [Operatori C#](index.md)
- [- operatore>](lambda-operator.md)
