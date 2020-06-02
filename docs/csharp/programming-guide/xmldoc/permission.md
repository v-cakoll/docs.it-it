---
title: <permission> -Guida per programmatori C#
ms.date: 07/20/2015
f1_keywords:
- permission
- <permission>
helpviewer_keywords:
- <permission> C# XML tag
- permission C# XML tag
ms.assetid: 769e93fe-8404-443f-bf99-577aa42b6a49
ms.openlocfilehash: bb7172042f0b472d03c3fa2d9dbd0d4d4265076b
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287272"
---
# <a name="permission-c-programming-guide"></a>\<permission>(Guida per programmatori C#)

## <a name="syntax"></a>Sintassi

```xml
<permission cref="member">description</permission>
```

## <a name="parameters"></a>Parametri

- cref = " `member`"

  Riferimento a un membro o a un campo disponibile per essere chiamato dall'ambiente di compilazione corrente. Il compilatore verifica l'esistenza dell'elemento di codice specificato e converte `member` nel nome canonico dell'elemento nel file XML di output. *member* deve essere racchiuso tra virgolette doppie (" ").

  Per informazioni su come creare un riferimento cref a un tipo generico, vedere l' [attributo cref](./cref-attribute.md).

- `description`

  Descrizione dell'accesso al membro.

## <a name="remarks"></a>Osservazioni

Il `<permission>` tag consente di documentare l'accesso di un membro. La classe <xref:System.Security.PermissionSet> consente di specificare l'accesso a un membro.

Compilare con [-doc](../../language-reference/compiler-options/doc-compiler-option.md) per elaborare i commenti relativi alla documentazione in un file.

## <a name="example"></a>Esempio

[!code-csharp[csProgGuideDocComments#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#8)]

## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../index.md)
- [Tag consigliati per i commenti relativi alla documentazione](./recommended-tags-for-documentation-comments.md)
