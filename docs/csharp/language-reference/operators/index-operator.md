---
title: Operatore [] - Riferimenti per C#
ms.custom: seodec18
ms.date: 01/10/2019
f1_keywords:
- '[]_CSharpKeyword'
helpviewer_keywords:
- subscript operator [C#]
- square brackets [ ] operator [C#]
- '[] operator [C#]'
- indexing operator [C#]
ms.assetid: 5c16bb45-88f7-45ff-b42c-1af1972b042c
ms.openlocfilehash: 948ce238058307631cf0e5a7a5e3d72664233052
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333395"
---
# <a name="-operator-c-reference"></a>Operatore [] (Riferimenti per C#)

Le parentesi quadre `[]` vengono in genere usate per l'accesso agli elementi matrice, indicizzatore o puntatore.

Per altre informazioni sull'accesso all'elemento puntatore, vedere [Procedura: Accedere a un elemento di matrice con un puntatore](../../programming-guide/unsafe-code-pointers/how-to-access-an-array-element-with-a-pointer.md).

Le parentesi quadre possono anche essere usate per specificare [attributi](../../programming-guide/concepts/attributes/index.md):

```csharp
[System.Diagnostics.Conditional("DEBUG")]
void TraceMethod() {}
```

## <a name="array-access"></a>Accesso a matrici

Nell'esempio seguente viene illustrato come accedere agli elementi matrice:

[!code-csharp-interactive[array access](~/samples/snippets/csharp/language-reference/operators/IndexOperatorExamples.cs#Arrays)]

Se un indice di matrice è fuori dai limiti della dimensione corrispondente di una matrice, viene generata un'eccezione <xref:System.IndexOutOfRangeException>.

Come illustrato nell'esempio precedente, le parentesi quadre vengono usate anche nella dichiarazione di un tipo matrice e nella creazione di istanze di matrice.

Per altre informazioni sulle matrici, vedere [Matrici](../../programming-guide/arrays/index.md).

## <a name="indexer-access"></a>Accesso all'indicizzatore

Nell'esempio seguente viene usato il tipo .NET <xref:System.Collections.Generic.Dictionary%602> per dimostrare l'accesso all'indicizzatore:

[!code-csharp-interactive[indexer access](~/samples/snippets/csharp/language-reference/operators/IndexOperatorExamples.cs#Indexers)]

Gli indicizzatori consentono di indicizzare le istanze di un tipo definito dall'utente con modalità simili a quelle dell'indicizzazione della matrice. A differenza degli indici di matrice, che devono essere valori interi, gli argomenti dell'indicizzatore possono essere dichiarati con qualsiasi tipo.

Per altre informazioni sugli indicizzatori, vedere [Indicizzatori](../../programming-guide/indexers/index.md).

## <a name="operator-overloadability"></a>Overload degli operatori

L'accesso all'elemento `[]` non viene considerato come operatore con supporto dell'overload. Per il supporto dell'indicizzazione con tipi definiti dall'utente, usare gli [indicizzatori](../../programming-guide/indexers/index.md).

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere le sezioni [Accesso all'elemento](~/_csharplang/spec/expressions.md#element-access) e [Accesso ai membri del puntatore](~/_csharplang/spec/unsafe-code.md#pointer-element-access) della [specifica del linguaggio C#](../language-specification/index.md).

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Operatori C#](index.md)
- [Matrici](../../programming-guide/arrays/index.md)
- [Indicizzatori](../../programming-guide/indexers/index.md)
- [Tipi di puntatori](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [Attributi](../../programming-guide/concepts/attributes/index.md)