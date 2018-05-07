---
title: '&lt;esempio&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- example XML tag
- <example> XML tag
ms.assetid: 90eeda1c-3fc4-427c-879c-5046d265a97c
ms.openlocfilehash: 8c09ab934ee7457fdff39a63c58f2546cda4d643
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="ltexamplegt-visual-basic"></a>&lt;esempio&gt; (Visual Basic)
Specifica un esempio per il membro.  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<example>description</example>  
```  
  
#### <a name="parameters"></a>Parametri  
 `description`  
 Descrizione dell'esempio di codice.  
  
## <a name="remarks"></a>Note  
 Il `<example>` tag consente di specificare un esempio di come utilizzare un metodo o l'altro membro della libreria. In genere comporta l'uso del tag [\<code>](../../../visual-basic/language-reference/xmldoc/code.md).  
  
 Compilare con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.  
  
## <a name="example"></a>Esempio  
 Questo esempio viene utilizzato il `<example>` tag per includere un esempio per l'utilizzo di `ID` campo.  
  
 [!code-vb[VbVbcnXmlDocComments#2](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/example_1.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Tag di commento XML](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
