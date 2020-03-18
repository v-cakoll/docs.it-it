---
title: <value> - Guida alla programmazione in C
ms.date: 07/20/2015
f1_keywords:
- <value>
helpviewer_keywords:
- <value> C# XML tag
- value C# XML tag
ms.assetid: 08dbadaf-9ab6-43d9-9493-98e43bed199a
ms.openlocfilehash: 120805346672738e614743ab8c98388b8dbac0f7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "76793355"
---
# <a name="value-c-programming-guide"></a>\<> di valore (Guida per programmatori C

## <a name="syntax"></a>Sintassi

```xml
<value>property-description</value>
```

## <a name="parameters"></a>Parametri

- `property-description`

  Descrizione della proprietà.

## <a name="remarks"></a>Osservazioni

Il tag \<value> consente di descrivere il valore che rappresenta una proprietà. Si noti che quando si aggiunge una proprietà tramite la creazione [ \<](./summary.md) guidata codice nell'ambiente di sviluppo di Visual Studio .NET, verrà aggiunto un riepilogo>tag per la nuova proprietà. È quindi necessario aggiungere manualmente un tag \<value> per descrivere il valore rappresentato dalla proprietà.

Compilare con [-doc](../../language-reference/compiler-options/doc-compiler-option.md) per elaborare i commenti relativi alla documentazione in un file.

## <a name="example"></a>Esempio

[!code-csharp[csProgGuideDocComments#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#14)]

## <a name="see-also"></a>Vedere anche

- [Guida alla programmazione in C](../index.md)
- [Tag consigliati per i commenti relativi alla documentazione](./recommended-tags-for-documentation-comments.md)
