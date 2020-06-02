---
title: <remarks> -Guida per programmatori C#
ms.date: 07/20/2015
f1_keywords:
- remarks
- <remarks>
helpviewer_keywords:
- remarks C# XML tag
- <remarks> C# XML tag
ms.assetid: f8641391-31f3-4735-af7a-c502a5b6a251
ms.openlocfilehash: 739027786e02e559d86f990bf614e261b497c76f
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287285"
---
# <a name="remarks-c-programming-guide"></a>\<remarks>(Guida per programmatori C#)

## <a name="syntax"></a>Sintassi

```xml
<remarks>description</remarks>
```

## <a name="parameters"></a>Parametri

- `Description`

  Descrizione del membro.

## <a name="remarks"></a>Osservazioni

Il `<remarks>` tag viene usato per aggiungere informazioni su un tipo, integrando le informazioni specificate con [\<summary>](./summary.md) . Queste informazioni vengono visualizzate nella finestra Visualizzatore oggetti.

Compilare con [-doc](../../language-reference/compiler-options/doc-compiler-option.md) per elaborare i commenti relativi alla documentazione in un file.

## <a name="example"></a>Esempio

[!code-csharp[csProgGuideDocComments#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#9)]

## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../index.md)
- [Tag consigliati per i commenti relativi alla documentazione](./recommended-tags-for-documentation-comments.md)
