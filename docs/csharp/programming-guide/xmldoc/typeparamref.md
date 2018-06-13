---
title: '&lt;typeparamref&gt; (Guida per programmatori C#)'
ms.date: 07/20/2015
f1_keywords:
- typeparamref
helpviewer_keywords:
- typeparamref C# XML tag
- <typeparamref> C# XML tag
ms.assetid: 6d8ffc58-12c5-4688-8db6-833a7ded5886
ms.openlocfilehash: 36e5a8998018839214da00287a2bf8dc2c5925a8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33356263"
---
# <a name="lttypeparamrefgt-c-programming-guide"></a>&lt;typeparamref&gt; (Guida per programmatori C#)
## <a name="syntax"></a>Sintassi  
  
```xml  
<typeparamref name="name"/>  
```  
  
#### <a name="parameters"></a>Parametri  
 `name`  
 Nome del parametro di tipo. Racchiudere il nome tra virgolette doppie (" ").  
  
## <a name="remarks"></a>Note  
 Per altre informazioni sui parametri di tipo in tipi e metodi generici, vedere [Generics](../../../csharp/programming-guide/generics/index.md).  
  
 Usare questo tag per consentire ai consumer del file di documentazione di formattare la parola in un modo specifico, ad esempio in corsivo.  
  
 Compilare con [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) per elaborare i commenti relativi alla documentazione in un file.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[csProgGuideDocComments#13](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/typeparamref_1.cs)]  
  
## <a name="see-also"></a>Vedere anche  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Tag consigliati per i commenti relativi alla documentazione](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
