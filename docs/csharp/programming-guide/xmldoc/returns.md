---
title: <returns> - C# Guida alla programmazione
ms.date: 07/20/2015
f1_keywords:
- returns
- <returns>
helpviewer_keywords:
- <returns> C# XML tag
- returns C# XML tag
ms.assetid: bb2d9958-62fc-47c7-9511-6311171f119f
ms.openlocfilehash: 784d9effa589c962b8a2b982fd199f74309fb4dc
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789705"
---
# <a name="returns-c-programming-guide"></a>\<restituisce > (C# guida per programmatori)

## <a name="syntax"></a>Sintassi

```xml
<returns>description</returns>
```

## <a name="parameters"></a>Parametri

- `description`

  Descrizione del valore restituito.

## <a name="remarks"></a>Note

Il tag \<returns> deve essere usato nel commento per una dichiarazione di metodo per descrivere il valore restituito.

Compilare con [-doc](../../language-reference/compiler-options/doc-compiler-option.md) per elaborare i commenti relativi alla documentazione in un file.

## <a name="example"></a>Esempio

[!code-csharp[csProgGuideDocComments#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#10)]

## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../index.md)
- [Tag consigliati per i commenti relativi alla documentazione](./recommended-tags-for-documentation-comments.md)
