---
title: Guida alla C# programmazione di <exception>
ms.date: 07/20/2015
f1_keywords:
- exception
- <exception>
helpviewer_keywords:
- <exception> C# XML tag
- exception C# XML tag
ms.assetid: dd73aac5-3c74-4fcf-9498-f11bff3a2f3c
ms.openlocfilehash: 14318ac0b0cdf781d0488eecaf934879017d91f6
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789795"
---
# <a name="exception-c-programming-guide"></a>\<> eccezioni (C# guida per programmatori)

## <a name="syntax"></a>Sintassi

```xml
<exception cref="member">description</exception>
```

## <a name="parameters"></a>Parametri

- cref = " `member`"

  Riferimento ad un'eccezione disponibile dall'ambiente di compilazione corrente. Il compilatore controlla che l'eccezione specificata esista e converte `member` nel nome canonico dell'elemento nel file XML di output. `member` deve essere racchiuso tra virgolette doppie (" ").

  Per altre informazioni su come formattare `member` per fare riferimento a un tipo generico, vedere [Elaborazione del file XML](processing-the-xml-file.md).

- `description`

  Descrizione dell'eccezione.

## <a name="remarks"></a>Note

Il tag \<exception> consente di specificare le eccezioni che possono essere generate. Questo tag può essere applicato alle definizioni di metodi, proprietà, eventi e indicizzatori.

Compilare con [-doc](../../language-reference/compiler-options/doc-compiler-option.md) per elaborare i commenti relativi alla documentazione in un file.

Per altre informazioni sulla gestione delle eccezioni, vedere [Eccezioni e gestione delle eccezioni](../exceptions/index.md).

## <a name="example"></a>Esempio

[!code-csharp[csProgGuideDocComments#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#4)]

## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../index.md)
- [Tag consigliati per i commenti relativi alla documentazione](recommended-tags-for-documentation-comments.md)
