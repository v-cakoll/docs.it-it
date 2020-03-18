---
title: <see>- Guida alla programmazione in C
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
ms.openlocfilehash: f4834f88c646b44269f8290c2ad08698c34e714a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "77627672"
---
# <a name="see-c-programming-guide"></a>\<Vedere> (Guida per programmatori C

## <a name="syntax"></a>Sintassi

```xml
<see cref="member"/>
```

## <a name="parameters"></a>Parametri

- cref -`member`" "

  Riferimento a un membro o a un campo disponibile per essere chiamato dall'ambiente di compilazione corrente. Il compilatore verifica l'esistenza dell'elemento di codice specificato e passa `member` al nome dell'elemento nel file XML di output. Racchiudere *member* tra virgolette doppie (" ").

## <a name="remarks"></a>Osservazioni

Con il tag \<see> è possibile specificare un collegamento nel testo. Utilizzate [ \<anche see>](./seealso.md) per indicare che il testo deve essere inserito in una sezione Vedere anche. Usare l'[attributo cref](./cref-attribute.md) per creare collegamenti ipertestuali interni alle pagine della documentazione per gli elementi di codice.

Compilare con [-doc](../../language-reference/compiler-options/doc-compiler-option.md) per elaborare i commenti relativi alla documentazione in un file.

Nell'esempio seguente viene illustrato un tag \<see> all'interno di una sezione di riepilogo.

[!code-csharp[csProgGuideDocComments#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#12)]

## <a name="see-also"></a>Vedere anche

- [Guida alla programmazione in C](../index.md)
- [Tag consigliati per i commenti relativi alla documentazione](./recommended-tags-for-documentation-comments.md)
