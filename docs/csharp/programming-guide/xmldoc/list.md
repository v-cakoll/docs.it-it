---
title: <list> - Guida alla programmazione in C
ms.date: 07/20/2015
f1_keywords:
- list
- <list>
helpviewer_keywords:
- list C# XML tag
- listheader C# XML tag
- <listheader> C# XML tag
- item C# XML tag
- <item> C# XML tag
- <list> C# XML tag
ms.assetid: c9620b1b-c2e6-43f1-ab88-8ab47308ffec
ms.openlocfilehash: cb289b26e9bc12d561892c421fb40da18d8c3513
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "76789744"
---
# <a name="list-c-programming-guide"></a>\<elenco> (Guida per programmatori C

## <a name="syntax"></a>Sintassi

```xml
<list type="bullet|number|table">
    <listheader>
        <term>term</term>
        <description>description</description>
    </listheader>
    <item>
        <term>term</term>
        <description>description</description>
    </item>
</list>
```

## <a name="parameters"></a>Parametri

- `term`

  Termine da definire, che verrà definito in `description`.

- `description`

  Elemento di un elenco puntato o numerato oppure la definizione di un `term`.
  
## <a name="remarks"></a>Osservazioni

Il blocco \<listheader> viene usato per definire la riga di intestazione di una tabella o di un elenco di definizioni. Per definire una tabella, è sufficiente specificare una voce per il termine nell'intestazione.

Ogni elemento dell'elenco viene specificato tramite un blocco \<item>. Quando si crea un elenco di definizioni, è necessario specificare sia `term` che `description`. Per le tabelle e gli elenchi puntati o numerati, tuttavia, è sufficiente fornire una voce per `description`.

Gli elenchi e le tabelle possono contenere un numero qualsiasi di blocchi \<item>.

Compilare con [-doc](../../language-reference/compiler-options/doc-compiler-option.md) per elaborare i commenti relativi alla documentazione in un file.

## <a name="example"></a>Esempio

[!code-csharp[csProgGuideDocComments#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#6)]

## <a name="see-also"></a>Vedere anche

- [Guida alla programmazione in C](../index.md)
- [Tag consigliati per i commenti relativi alla documentazione](./recommended-tags-for-documentation-comments.md)
