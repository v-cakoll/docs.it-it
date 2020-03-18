---
title: <param> - Guida alla programmazione in C
ms.date: 07/20/2015
f1_keywords:
- param
- <param>
helpviewer_keywords:
- <param> C# XML tag
- param C# XML tag
ms.assetid: 46d329b1-5b84-4537-9e17-73ca97313e4e
ms.openlocfilehash: d16070a82531519dd276b2ea999623017769d716
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "76789764"
---
# <a name="param-c-programming-guide"></a>\<> param (Guida per programmatori C

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

Il tag \<param> viene usato nel commento di una dichiarazione di metodo per descrivere uno dei parametri del metodo. Per documentare più parametri, usare più tag \<param>.

Il testo del tag \<param> verrà visualizzato in IntelliSense, nella finestra Visualizzatore oggetti e nel report Web sui commenti del codice.

Compilare con [-doc](../../language-reference/compiler-options/doc-compiler-option.md) per elaborare i commenti relativi alla documentazione in un file.

## <a name="example"></a>Esempio

[!code-csharp[csProgGuideDocComments#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#1)]

## <a name="see-also"></a>Vedere anche

- [Guida alla programmazione in C](../index.md)
- [Tag consigliati per i commenti relativi alla documentazione](./recommended-tags-for-documentation-comments.md)
