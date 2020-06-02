---
title: <paramref>-Guida per programmatori C#
ms.date: 07/20/2015
f1_keywords:
- paramref
- <paramref>
helpviewer_keywords:
- <paramref> C# XML tag
- paramref C# XML tag
ms.assetid: 756c24c1-f591-40e8-a838-559761539b0b
ms.openlocfilehash: 4f3b521d24c8b4677a05b0b145cb36c31b2793f2
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287311"
---
# <a name="paramref-c-programming-guide"></a>\<paramref>(Guida per programmatori C#)

## <a name="syntax"></a>Sintassi

```xml
<paramref name="name"/>
```

## <a name="parameters"></a>Parametri

- `name`

  Nome del parametro a cui fare riferimento. Racchiudere il nome tra virgolette doppie (" ").

## <a name="remarks"></a>Osservazioni

Il `<paramref>` tag fornisce un modo per indicare che una parola nei commenti del codice, ad esempio in un `<summary>` blocco o `<remarks>` fa riferimento a un parametro. È possibile elaborare il file XML in modo da formattare la parola in modo specifico, ad esempio in grassetto o in corsivo.

Compilare con [-doc](../../language-reference/compiler-options/doc-compiler-option.md) per elaborare i commenti relativi alla documentazione in un file.

## <a name="example"></a>Esempio

[!code-csharp[csProgGuideDocComments#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#7)]

## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../index.md)
- [Tag consigliati per i commenti relativi alla documentazione](./recommended-tags-for-documentation-comments.md)
