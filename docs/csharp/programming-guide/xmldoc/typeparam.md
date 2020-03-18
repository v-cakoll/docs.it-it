---
title: <typeparam> - Guida alla programmazione in C
ms.date: 07/20/2015
f1_keywords:
- typeparam
helpviewer_keywords:
- <typeparam> C# XML tag
- typeparam C# XML tag
ms.assetid: 9b99d400-e911-4e55-99c6-64367c96aa4f
ms.openlocfilehash: 867ecacf58f95533395ded203a8f17bc92558ccf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "76793357"
---
# <a name="typeparam-c-programming-guide"></a>\<> typeparam (Guida per programmatori C

## <a name="syntax"></a>Sintassi

```xml
<typeparam name="name">description</typeparam>
```

## <a name="parameters"></a>Parametri

- `name`

  Nome del parametro di tipo. Racchiudere il nome tra virgolette doppie (" ").

- `description`

  Descrizione del parametro di tipo.

## <a name="remarks"></a>Osservazioni

Il tag `<typeparam>` deve essere usato nel commento per una dichiarazione di tipo o metodo generico per descrivere un parametro di tipo. Aggiungere un tag per ogni parametro di tipo del tipo o del metodo generico.

Per altre informazioni, vedere [Generics](../generics/index.md).

Il testo del tag `<typeparam>` verrà visualizzato in IntelliSense, nella [finestra Visualizzatore oggetti](/visualstudio/ide/viewing-the-structure-of-code#BKMK_ObjectBrowser) e nel report Web sui commenti del codice.

Compilare con [-doc](../../language-reference/compiler-options/doc-compiler-option.md) per elaborare i commenti relativi alla documentazione in un file.

## <a name="example"></a>Esempio

[!code-csharp[csProgGuideDocComments#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#13)]

## <a name="see-also"></a>Vedere anche

- [Informazioni di riferimento su C#](../../language-reference/index.md)
- [Guida alla programmazione in C](../index.md)
- [Tag consigliati per i commenti relativi alla documentazione](./recommended-tags-for-documentation-comments.md)
