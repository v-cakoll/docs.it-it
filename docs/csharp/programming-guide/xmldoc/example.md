---
title: <example> -Guida per programmatori C#
ms.date: 07/20/2015
f1_keywords:
- <example>
- example
helpviewer_keywords:
- <example> C# XML tag
- example C# XML tag
ms.assetid: 32d6e73b-2554-4abb-83ee-a1e321334fd2
ms.openlocfilehash: e8d26f82562cc5140662f5b32ea9fedf5481d8f8
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287388"
---
# <a name="example-c-programming-guide"></a>\<example>(Guida per programmatori C#)

## <a name="syntax"></a>Sintassi

```xml
<example>description</example>
```

## <a name="parameters"></a>Parametri

- `description`

  Descrizione dell'esempio di codice.

## <a name="remarks"></a>Osservazioni

Il `<example>` tag consente di specificare un esempio di come usare un metodo o un altro membro della libreria. Questa operazione comporta in genere l'uso del [\<code>](./code.md) tag.

Compilare con [-doc](../../language-reference/compiler-options/doc-compiler-option.md) per elaborare i commenti relativi alla documentazione in un file.

## <a name="example"></a>Esempio

[!code-csharp[csProgGuideDocComments#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#3)]

## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../index.md)
- [Tag consigliati per i commenti relativi alla documentazione](./recommended-tags-for-documentation-comments.md)
