---
title: '&lt;codice&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- code XML tag
- <code> XML tag
ms.assetid: 925e5342-be05-45f2-bf66-7398bbd6710e
ms.openlocfilehash: e66aebe35dd8f6443fefe3b07842b37270159e6e
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "43858639"
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
 Usare il `<code>` tag per indicare più righe come codice. Usare [\<c>](../../../visual-basic/language-reference/xmldoc/c.md) per indicare che il testo all'interno di una descrizione deve essere contrassegnato come codice.  
  
 Compilare con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.  
  
## <a name="example"></a>Esempio  
 Questo esempio Usa la \<codice > tag per includere il codice di esempio per l'uso di `ID` campo.  
  
 [!code-vb[VbVbcnXmlDocComments#2](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/code_1.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Tag di commento XML](../../../visual-basic/language-reference/xmldoc/index.md)
