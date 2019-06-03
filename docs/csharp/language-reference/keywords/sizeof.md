---
title: sizeof - Riferimenti per C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- sizeof_CSharpKeyword
- sizeof
helpviewer_keywords:
- sizeof keyword [C#]
ms.assetid: c548592c-677c-4f40-a4ce-e613f7529141
ms.openlocfilehash: a00c4f96e62f7fd7d7c352aece097acd5b600ae2
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/31/2019
ms.locfileid: "66422402"
---
# <a name="sizeof-c-reference"></a>sizeof (Riferimenti per C#)

Usato per ottenere la dimensione in byte per un tipo non gestito.

I tipi non gestiti includono:

- I tipi semplici elencati nella tabella seguente:

   |Espressione|Valore costante|
   |----------------|--------------------|
   |`sizeof(sbyte)`|1|
   |`sizeof(byte)`|1|
   |`sizeof(short)`|2|
   |`sizeof(ushort)`|2|
   |`sizeof(int)`|4|
   |`sizeof(uint)`|4|
   |`sizeof(long)`|8|
   |`sizeof(ulong)`|8|
   |`sizeof(char)`|2 (Unicode)|
   |`sizeof(float)`|4|
   |`sizeof(double)`|8|
   |`sizeof(decimal)`|16|
   |`sizeof(bool)`|1|

- Tipi enumerazione.

- Tipi puntatore.

- Struct definiti dall'utente che non contengono campi di istanza o proprietà di istanza implementate automaticamente che sono tipi riferimento o tipi costruiti.

Nell'esempio seguente viene illustrato come ottenere la dimensione di un `int`:

```csharp
// Constant value 4:
int intSize = sizeof(int);
```

## <a name="remarks"></a>Osservazioni

A partire dalla versione 2.0 di C#, l'applicazione di `sizeof` a tipi semplici o tipi enumerazione non richiede più che il codice venga compilato in un contesto [non sicuro](unsafe.md).

Non è possibile sottoporre l'operatore `sizeof` a overload. I valori restituiti dall'operatore `sizeof` sono di tipo `int`. La tabella precedente mostra i valori costanti che vengono sostituiti per le espressioni `sizeof` con determinati tipi predefiniti come operandi.

Per tutti gli altri tipi, inclusi gli struct, l'operatore `sizeof` può essere usato solo nei blocchi di codice unsafe. Sebbene sia possibile usare il metodo <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType>, il valore restituito da questo metodo non è sempre uguale al valore restituito da `sizeof`. <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> restituisce la dimensione dopo il marshalling del tipo, mentre `sizeof` restituisce la dimensione allocata da Common Language Runtime, che include eventuali spaziature interne.

## <a name="example"></a>Esempio

[!code-csharp[csrefKeywordsOperator#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#11)]

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Parole chiave di C#](index.md)
- [enum](enum.md)
- [Codice unsafe e puntatori](../../programming-guide/unsafe-code-pointers/index.md)
- [Struct](../../programming-guide/classes-and-structs/structs.md)
- [Costanti](../../programming-guide/classes-and-structs/constants.md)
