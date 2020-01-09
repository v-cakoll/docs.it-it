---
title: Vincolo new - Riferimenti per C#
ms.date: 07/20/2015
helpviewer_keywords:
- new constraint keyword [C#]
ms.assetid: 58850b64-cb97-4136-be50-1f3bc7fc1da9
ms.openlocfilehash: cd67aeb82d736b8941b0637494089723e7815505
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75713346"
---
# <a name="new-constraint-c-reference"></a>Vincolo new (Riferimenti per C#)

Il vincolo `new` specifica che un argomento tipo in una dichiarazione di classe generica deve avere un costruttore pubblico senza parametri. Per usare il vincolo `new`, il tipo non può essere astratto.

Applicare il vincolo `new` a un parametro di tipo quando una classe generica crea nuove istanze del tipo, come illustrato nell'esempio seguente:

[!code-csharp[csrefKeywordsOperator#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#5)]

Quando il vincolo `new()` viene usato con altri vincoli, è necessario specificarlo per ultimo:

[!code-csharp[csrefKeywordsOperator#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#6)]

Per altre informazioni, vedere [Vincoli sui parametri di tipo](../../programming-guide/generics/constraints-on-type-parameters.md).

È anche possibile usare la parola chiave `new` per [creare un'istanza di un tipo](../operators/new-operator.md) o come [modificatore di dichiarazione di membro](new-modifier.md).

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere la sezione [Vincoli del parametro di tipo](~/_csharplang/spec/classes.md#type-parameter-constraints) della [specifica del linguaggio C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../../language-reference/index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Parole chiave di C#](index.md)
- [Generics](../../programming-guide/generics/index.md)
