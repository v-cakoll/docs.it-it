---
title: <seealso> - Guida alla programmazione in C
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
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "77093461"
---
# <a name="seealso-c-programming-guide"></a>\<seealso> (Guida per programmatori C

## <a name="syntax"></a>Sintassi

```xml
<seealso cref="member"/>
```

## <a name="parameters"></a>Parametri

- cref = " `member`"

  Riferimento a un membro o a un campo disponibile per essere chiamato dall'ambiente di compilazione corrente. Il compilatore verifica l'esistenza dell'elemento di codice specificato e passa `member` al nome dell'elemento nel file XML di output. `member` deve essere racchiuso tra virgolette doppie (" ").

  Per informazioni su come creare un riferimento cref a un tipo generico, vedere [cref attribute](./cref-attribute.md).

## <a name="remarks"></a>Osservazioni

Il tag \<seealso> consente di specificare il testo da visualizzare in una sezione Vedere anche. Utilizzare [ \<le>](./see.md) per specificare un collegamento dall'interno del testo.

Compilare con [-doc](../../language-reference/compiler-options/doc-compiler-option.md) per elaborare i commenti relativi alla documentazione in un file.

## <a name="example"></a>Esempio

Per un esempio di \<utilizzo di seealso>, vedere [ \<>](./summary.md) di riepilogo.

## <a name="see-also"></a>Vedere anche

- [Guida alla programmazione in C](../index.md)
- [Tag consigliati per i commenti relativi alla documentazione](./recommended-tags-for-documentation-comments.md)
