---
title: <see>-Guida per programmatori C#
ms.date: 07/20/2015
f1_keywords:
- <see>
- see
helpviewer_keywords:
- cref [C#], <see> tag
- <see> C# XML tag
- cross-references [C#]
- see C# XML tag
ms.assetid: 0200de01-7e2f-45c4-9094-829d61236383
ms.openlocfilehash: 0f10feb0931c6d38c817fdecb925f68d439abb59
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287246"
---
# <a name="see-c-programming-guide"></a>\<see>(Guida per programmatori C#)

## <a name="syntax"></a>Sintassi

```xml
<see cref="member"/>
```

## <a name="parameters"></a>Parametri

- cref = " `member` "

  Riferimento a un membro o a un campo disponibile per essere chiamato dall'ambiente di compilazione corrente. Il compilatore verifica l'esistenza dell'elemento di codice specificato e passa `member` al nome dell'elemento nel file XML di output. Racchiudere *member* tra virgolette doppie (" ").

## <a name="remarks"></a>Osservazioni

Il `<see>` tag consente di specificare un collegamento dall'interno del testo. Usare [\<seealso>](./seealso.md) per indicare che il testo deve essere inserito in una sezione vedere anche. Usare l'[attributo cref](./cref-attribute.md) per creare collegamenti ipertestuali interni alle pagine della documentazione per gli elementi di codice.

Compilare con [-doc](../../language-reference/compiler-options/doc-compiler-option.md) per elaborare i commenti relativi alla documentazione in un file.

Nell'esempio seguente viene illustrato un `<see>` tag all'interno di una sezione di riepilogo.

[!code-csharp[csProgGuideDocComments#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#12)]

## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../index.md)
- [Tag consigliati per i commenti relativi alla documentazione](./recommended-tags-for-documentation-comments.md)
