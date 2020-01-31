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
ms.openlocfilehash: ad22b423d085a152f47c4e34d7ee4247ef9836b8
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789686"
---
# <a name="seealso-c-programming-guide"></a>> seealso \<(C# guida per programmatori)

## <a name="syntax"></a>Sintassi

```xml
<seealso cref="member"/>
```

## <a name="parameters"></a>Parametri

- cref = " `member`"

  Riferimento a un membro o a un campo disponibile per essere chiamato dall'ambiente di compilazione corrente. Il compilatore verifica l'esistenza dell'elemento di codice specificato e passa `member` al nome dell'elemento nel file XML di output. `member` deve essere racchiuso tra virgolette doppie (" ").

  Per informazioni su come creare un riferimento cref a un tipo generico, vedere [\<see>](./see.md).

## <a name="remarks"></a>Note

Il tag \<seealso> consente di specificare il testo da visualizzare in una sezione Vedere anche. Usare [\<see>](./see.md) per specificare un collegamento nel testo.

Compilare con [-doc](../../language-reference/compiler-options/doc-compiler-option.md) per elaborare i commenti relativi alla documentazione in un file.

## <a name="example"></a>Esempio

Per un esempio d'uso di \<seealso>, vedere [\<summary>](./summary.md).

## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../index.md)
- [Tag consigliati per i commenti relativi alla documentazione](./recommended-tags-for-documentation-comments.md)
