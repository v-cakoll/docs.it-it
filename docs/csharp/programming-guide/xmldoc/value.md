---
title: <value> -Guida per programmatori C#
ms.date: 07/20/2015
f1_keywords:
- <value>
helpviewer_keywords:
- <value> C# XML tag
- value C# XML tag
ms.assetid: 08dbadaf-9ab6-43d9-9493-98e43bed199a
ms.openlocfilehash: bd6630a8d5894fda39ad289c8dd584f6d84e5490
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287194"
---
# <a name="value-c-programming-guide"></a>\<value>(Guida per programmatori C#)

## <a name="syntax"></a>Sintassi

```xml
<value>property-description</value>
```

## <a name="parameters"></a>Parametri

- `property-description`

  Descrizione della proprietà.

## <a name="remarks"></a>Osservazioni

Il `<value>` tag consente di descrivere il valore rappresentato da una proprietà. Quando si aggiunge una proprietà tramite la creazione guidata codice nell'ambiente di sviluppo Visual Studio .NET, viene aggiunto un [\<summary>](./summary.md) tag per la nuova proprietà. È quindi necessario aggiungere manualmente un `<value>` tag per descrivere il valore rappresentato dalla proprietà.

Compilare con [-doc](../../language-reference/compiler-options/doc-compiler-option.md) per elaborare i commenti relativi alla documentazione in un file.

## <a name="example"></a>Esempio

[!code-csharp[csProgGuideDocComments#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#14)]

## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../index.md)
- [Tag consigliati per i commenti relativi alla documentazione](./recommended-tags-for-documentation-comments.md)
