---
title: <c> - Guida per programmatori C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- c
- <c>
helpviewer_keywords:
- text, marking as code [C#]
- code, marking text as [C#]
- c C# XML tag
- <c> C# XML tag
ms.assetid: aad5b16e-a29e-445e-bd0d-eea0b138d7b2
ms.openlocfilehash: 8471681f979fdd030490a5ecc306c4a4b9f624f9
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55276757"
---
# <a name="c-c-programming-guide"></a>\<c> (Guida per programmatori C#)
## <a name="syntax"></a>Sintassi  
  
```xml  
<c>text</c>  
```  
  
#### <a name="parameters"></a>Parametri  
 `text`  
 Il testo che si desidera indicare come codice.  
  
## <a name="remarks"></a>Note  
 Il tag \<c> consente di indicare che il testo all'interno di una descrizione deve essere contrassegnato come codice. Usare [\<code>](../../../csharp/programming-guide/xmldoc/code.md) per indicare più righe come codice.  
  
 Compilare con [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) per elaborare i commenti relativi alla documentazione in un file.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[csProgGuideDocComments#2](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/code-inline_1.cs)]  
  
## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../../../csharp/programming-guide/index.md)
- [Tag consigliati per i commenti relativi alla documentazione](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
