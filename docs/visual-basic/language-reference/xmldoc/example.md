---
title: '&lt;esempio&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- example XML tag
- <example> XML tag
ms.assetid: 90eeda1c-3fc4-427c-879c-5046d265a97c
ms.openlocfilehash: 2de91d828fd9706b66f4c810486e54e2d3062de0
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43524517"
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
 Il `<example>` tag consente di specificare un esempio di come usare un metodo o un altro membro della raccolta. In genere comporta l'uso del tag [\<code>](../../../visual-basic/language-reference/xmldoc/code.md).  
  
 Compilare con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.  
  
## <a name="example"></a>Esempio  
 Questo esempio Usa il `<example>` tag per includere un esempio dell'uso di `ID` campo.  
  
 [!code-vb[VbVbcnXmlDocComments#2](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/example_1.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Tag di commento XML](../../../visual-basic/language-reference/xmldoc/index.md)
