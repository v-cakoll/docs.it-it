---
title: typeof - Riferimenti per C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- typeof
- typeof_CSharpKeyword
helpviewer_keywords:
- typeof keyword [C#]
ms.assetid: 0c08d880-515e-46bb-8cd2-48b8dd62c08d
ms.openlocfilehash: 7962a3d0a5885e64701cb9d9a4d689cd982b9830
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/31/2019
ms.locfileid: "66422549"
---
# <a name="typeof-c-reference"></a>typeof (Riferimenti per C#)

Viene usato per ottenere l'oggetto <xref:System.Type?displayProperty=nameWithType> per un tipo. L'espressione `typeof` assume il formato seguente:

```csharp
System.Type type = typeof(int);
```

## <a name="remarks"></a>Note

Per ottenere il tipo di runtime di un'espressione, è possibile usare il metodo di .NET Framework <xref:System.Object.GetType%2A>, come nell'esempio seguente:

```csharp
int i = 0;
System.Type type = i.GetType();
```

Non è possibile sottoporre l'operatore `typeof` a overload.

L'operatore `typeof` può essere usato anche su tipi generici aperti. I tipi con più di un parametro di tipo devono avere il numero appropriato di virgole nella specifica. <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWIthType>, ad esempio, ha due argomenti tipo, quindi si usa una virgola:

```csharp
Type t = typeof(System.Collection.Generic.Dictionary<,>);
```

Nell'esempio seguente viene illustrato come determinare se il tipo restituito di un metodo è un elemento <xref:System.Collections.Generic.IEnumerable%601> generico. <xref:System.Type.GetInterface%2A?displayProperty=nameWithType> restituirà `null` se il tipo restituito non è un tipo generico <xref:System.Collections.Generic.IEnumerable%601>.

[!code-csharp[typeof_3.cs](~/samples/snippets/csharp/keywords/typeof/typeof_3.cs)]

## <a name="example"></a>Esempio

[!code-csharp[csrefKeywordsOperator#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#12)] 

## <a name="example"></a>Esempio

Questo esempio usa il metodo <xref:System.Object.GetType%2A> per determinare il tipo usato per contenere il risultato di un calcolo numerico. Ciò dipende dai requisiti di archiviazione del numero risultante.

[!code-csharp[csrefKeywordsOperator#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#13)]

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere [Operatore typeof](~/_csharplang/spec/expressions.md#the-typeof-operator) in [Specifica del linguaggio C#](../language-specification/index.md). La specifica del linguaggio costituisce il riferimento ufficiale principale per la sintassi e l'uso di C#.

## <a name="see-also"></a>Vedere anche

- <xref:System.Type?displayProperty=nameWithType>
- [Riferimenti per C#](../../../csharp/language-reference/index.md)
- [Guida per programmatori C#](../../../csharp/programming-guide/index.md)
- [Parole chiave di C#](../../../csharp/language-reference/keywords/index.md)
- [is](../../../csharp/language-reference/keywords/is.md)
