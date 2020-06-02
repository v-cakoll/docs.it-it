---
title: <param> -Guida per programmatori C#
ms.date: 07/20/2015
f1_keywords:
- param
- <param>
helpviewer_keywords:
- <param> C# XML tag
- param C# XML tag
ms.assetid: 46d329b1-5b84-4537-9e17-73ca97313e4e
ms.openlocfilehash: 396ed716c246091a674268020261069f36dd2be8
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287324"
---
# <a name="param-c-programming-guide"></a>\<param>(Guida per programmatori C#)

## <a name="syntax"></a>Sintassi

```xml
<param name="name">description</param>
```

## <a name="parameters"></a>Parametri

- `name`

  Nome di un parametro di metodo. Racchiudere il nome tra virgolette doppie (" ").

- `description`

  Descrizione del parametro.

## <a name="remarks"></a>Osservazioni

Il `<param>` tag deve essere usato nel commento per una dichiarazione di metodo per descrivere uno dei parametri per il metodo. Per documentare più parametri, usare più `<param>` tag.

Il testo per il `<param>` tag viene visualizzato in IntelliSense, il Visualizzatore oggetti e il report Web di commenti sul codice.

Compilare con [-doc](../../language-reference/compiler-options/doc-compiler-option.md) per elaborare i commenti relativi alla documentazione in un file.

## <a name="example"></a>Esempio

[!code-csharp[csProgGuideDocComments#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#1)]

## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../index.md)
- [Tag consigliati per i commenti relativi alla documentazione](./recommended-tags-for-documentation-comments.md)
