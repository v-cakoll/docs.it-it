---
title: <remarks> - Guida alla programmazione in C
ms.date: 07/20/2015
f1_keywords:
- remarks
- <remarks>
helpviewer_keywords:
- remarks C# XML tag
- <remarks> C# XML tag
ms.assetid: f8641391-31f3-4735-af7a-c502a5b6a251
ms.openlocfilehash: e37dac9cb9fed1df6ca027f09f2c95dbbc8ea66d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "76793380"
---
# <a name="remarks-c-programming-guide"></a>\<osservazioni> (Guida per programmatori C

## <a name="syntax"></a>Sintassi

```xml
<remarks>description</remarks>
```

## <a name="parameters"></a>Parametri

- `Description`

  Descrizione del membro.

## <a name="remarks"></a>Osservazioni

Il \<tag osservazioni> viene utilizzato per aggiungere informazioni su un tipo, integrando le informazioni specificate con [ \<>di riepilogo. ](./summary.md) Queste informazioni vengono visualizzate nella finestra Visualizzatore oggetti.

Compilare con [-doc](../../language-reference/compiler-options/doc-compiler-option.md) per elaborare i commenti relativi alla documentazione in un file.

## <a name="example"></a>Esempio

[!code-csharp[csProgGuideDocComments#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#9)]

## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../index.md)
- [Tag consigliati per i commenti relativi alla documentazione](./recommended-tags-for-documentation-comments.md)
