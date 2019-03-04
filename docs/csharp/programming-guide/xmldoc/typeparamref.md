---
title: <typeparamref> - Guida per programmatori C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- typeparamref
helpviewer_keywords:
- typeparamref C# XML tag
- <typeparamref> C# XML tag
ms.assetid: 6d8ffc58-12c5-4688-8db6-833a7ded5886
ms.openlocfilehash: 0ee9e3571ab601f56ddee2fd9a02bb19f50bac62
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56967360"
---
# <a name="typeparamref-c-programming-guide"></a>\<typeparamref> (Guida per programmatori C#)
## <a name="syntax"></a>Sintassi  
  
```xml  
<typeparamref name="name"/>  
```  
  
#### <a name="parameters"></a>Parametri  
 `name`  
 Nome del parametro di tipo. Racchiudere il nome tra virgolette doppie (" ").  
  
## <a name="remarks"></a>Osservazioni  
 Per altre informazioni sui parametri di tipo in tipi e metodi generici, vedere [Generics](../../../csharp/programming-guide/generics/index.md).  
  
 Usare questo tag per consentire ai consumer del file di documentazione di formattare la parola in un modo specifico, ad esempio in corsivo.  
  
 Compilare con [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) per elaborare i commenti relativi alla documentazione in un file.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[csProgGuideDocComments#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#13)]  
  
## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../../../csharp/programming-guide/index.md)
- [Tag consigliati per i commenti relativi alla documentazione](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
