---
title: Guida alla C# programmazione di <c>
ms.date: 07/20/2015
f1_keywords:
- c
- <c>
helpviewer_keywords:
- text, marking as code [C#]
- code, marking text as [C#]
- c C# XML tag
- <c> C# XML tag
ms.assetid: aad5b16e-a29e-445e-bd0d-eea0b138d7b2
ms.openlocfilehash: d5b28ee6db52d191f8454592d792ac0a1e1dc73b
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793460"
---
# <a name="c-c-programming-guide"></a>> di \<cC# (Guida per programmatori)

## <a name="syntax"></a>Sintassi

```xml
<c>text</c>
```

## <a name="parameters"></a>Parametri

- `text`

  Il testo che si desidera indicare come codice.

## <a name="remarks"></a>Note

Il tag \<c> consente di indicare che il testo all'interno di una descrizione deve essere contrassegnato come codice. Usare [\<code>](./code.md) per indicare più righe come codice.

Compilare con [-doc](../../language-reference/compiler-options/doc-compiler-option.md) per elaborare i commenti relativi alla documentazione in un file.

## <a name="example"></a>Esempio

[!code-csharp[csProgGuideDocComments#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#2)]
  
## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../index.md)
- [Tag consigliati per i commenti relativi alla documentazione](./recommended-tags-for-documentation-comments.md)
