---
title: <example> - C# Guida alla programmazione
ms.date: 07/20/2015
f1_keywords:
- <example>
- example
helpviewer_keywords:
- <example> C# XML tag
- example C# XML tag
ms.assetid: 32d6e73b-2554-4abb-83ee-a1e321334fd2
ms.openlocfilehash: 615eccbc427b6a5bbbed061acd0c8b0b9be7f46c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789811"
---
# <a name="example-c-programming-guide"></a>> di esempio \<C# (Guida per programmatori)

## <a name="syntax"></a>Sintassi

```xml
<example>description</example>
```

## <a name="parameters"></a>Parametri

- `description`

  Descrizione dell'esempio di codice.

## <a name="remarks"></a>Note

Il tag \<example> consente di specificare un esempio di come usare un metodo o un altro membro della libreria. In genere comporta l'uso del tag [\<code>](./code.md).

Compilare con [-doc](../../language-reference/compiler-options/doc-compiler-option.md) per elaborare i commenti relativi alla documentazione in un file.

## <a name="example"></a>Esempio

[!code-csharp[csProgGuideDocComments#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#3)]

## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../index.md)
- [Tag consigliati per i commenti relativi alla documentazione](./recommended-tags-for-documentation-comments.md)
