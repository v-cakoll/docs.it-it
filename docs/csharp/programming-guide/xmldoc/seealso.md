---
title: <seealso> - C# Guida alla programmazione
ms.date: 07/20/2015
f1_keywords:
- cref
- <seealso>
- seealso
helpviewer_keywords:
- cref [C#], see also
- seealso C# XML tag
- cref [C#]
- cross-references [C#], tags
- <seealso> C# XML tag
ms.assetid: 8e157f3f-f220-4fcf-9010-88905b080b18
ms.openlocfilehash: e24d5910ab21f01aebb5a32ce7646cf56886a81a
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2020
ms.locfileid: "77093461"
---
# <a name="seealso-c-programming-guide"></a>> seealso \<(C# guida per programmatori)

## <a name="syntax"></a>Sintassi

```xml
<seealso cref="member"/>
```

## <a name="parameters"></a>Parametri

- cref = " `member`"

  Riferimento a un membro o a un campo disponibile per essere chiamato dall'ambiente di compilazione corrente. Il compilatore verifica l'esistenza dell'elemento di codice specificato e passa `member` al nome dell'elemento nel file XML di output. `member` deve essere racchiuso tra virgolette doppie (" ").

  Per informazioni su come creare un riferimento cref a un tipo generico, vedere l' [attributo cref](./cref-attribute.md).

## <a name="remarks"></a>Osservazioni

Il tag \<seealso> consente di specificare il testo da visualizzare in una sezione Vedere anche. Usare [\<see>](./see.md) per specificare un collegamento nel testo.

Compilare con [-doc](../../language-reference/compiler-options/doc-compiler-option.md) per elaborare i commenti relativi alla documentazione in un file.

## <a name="example"></a>Esempio

Per un esempio d'uso di [seealso>, vedere \<](./summary.md)summary>\<.

## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../index.md)
- [Tag consigliati per i commenti relativi alla documentazione](./recommended-tags-for-documentation-comments.md)
