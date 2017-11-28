---
title: '&lt;codice&gt; (Visual Basic)'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- code XML tag
- <code> XML tag
ms.assetid: 925e5342-be05-45f2-bf66-7398bbd6710e
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a7c1d8ab3db0c36c6a2935b9ffbef15e87df5ebc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="ltcodegt-visual-basic"></a>&lt;codice&gt; (Visual Basic)
Indica che il testo è più righe di codice.  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<code>content</code>  
```  
  
#### <a name="parameters"></a>Parametri  
 `content`  
 Testo da contrassegnare come codice.  
  
## <a name="remarks"></a>Note  
 Utilizzare il `<code>` tag per indicare più righe di codice. Usare [\<c>](../../../visual-basic/language-reference/xmldoc/c.md) per indicare che il testo all'interno di una descrizione deve essere contrassegnato come codice.  
  
 Compilare con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.  
  
## <a name="example"></a>Esempio  
 Questo esempio viene utilizzato il \<codice > tag per includere il codice di esempio per l'utilizzo di `ID` campo.  
  
 [!code-vb[VbVbcnXmlDocComments#2](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/code_1.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Tag di commento XML](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
