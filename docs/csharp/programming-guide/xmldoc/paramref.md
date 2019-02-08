---
title: <paramref> - Guida per programmatori C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- paramref
- <paramref>
helpviewer_keywords:
- <paramref> C# XML tag
- paramref C# XML tag
ms.assetid: 756c24c1-f591-40e8-a838-559761539b0b
ms.openlocfilehash: 4fd0770bfe6c15c0e9b10239019ec265550dc372
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55262835"
---
# <a name="paramref-c-programming-guide"></a>\<paramref> (Guida per programmatori C#)
## <a name="syntax"></a>Sintassi  
  
```xml  
<paramref name="name"/>  
```  
  
#### <a name="parameters"></a>Parametri  
 `name`  
 Nome del parametro a cui fare riferimento. Racchiudere il nome tra virgolette doppie (" ").  
  
## <a name="remarks"></a>Note  
 Il tag \<paramref> consente di indicare che una parola nei commenti del codice, ad esempio in un blocco \<summary> o \<remarks>, fa riferimento a un parametro. È possibile elaborare il file XML in modo da formattare la parola in modo specifico, ad esempio in grassetto o in corsivo.  
  
 Compilare con [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) per elaborare i commenti relativi alla documentazione in un file.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[csProgGuideDocComments#7](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/paramref_1.cs)]  
  
## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../../../csharp/programming-guide/index.md)
- [Tag consigliati per i commenti relativi alla documentazione](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
