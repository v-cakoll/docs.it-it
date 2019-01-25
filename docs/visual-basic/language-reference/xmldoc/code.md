---
title: '&lt;code&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- code XML tag
- <code> XML tag
ms.assetid: 925e5342-be05-45f2-bf66-7398bbd6710e
ms.openlocfilehash: 8a4708a7b50b0e221c1ebe7f95d4f8ff80cd1ebe
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54566307"
---
# <a name="ltcodegt-visual-basic"></a>&lt;code&gt; (Visual Basic)
Indica che il testo è più righe di codice.  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<code>content</code>  
```  
  
#### <a name="parameters"></a>Parametri  
 `content`  
 Testo da contrassegnare come codice.  
  
## <a name="remarks"></a>Note  
 Usare il `<code>` tag per indicare più righe come codice. Usare [\<c>](../../../visual-basic/language-reference/xmldoc/c.md) per indicare che il testo all'interno di una descrizione deve essere contrassegnato come codice.  
  
 Compilare con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.  
  
## <a name="example"></a>Esempio  
 Questo esempio Usa la \<codice > tag per includere il codice di esempio per l'uso di `ID` campo.  
  
 [!code-vb[VbVbcnXmlDocComments#2](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/code_1.vb)]  
  
## <a name="see-also"></a>Vedere anche
- [Tag di commento XML](../../../visual-basic/language-reference/xmldoc/index.md)
