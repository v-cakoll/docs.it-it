---
title: '&lt;vedere&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- see XML tag
- <see> XML tag
ms.assetid: 7e18f60b-ef4a-4678-a797-5eb918635ca9
ms.openlocfilehash: e790f8abd216e198ff5077beab6f857e39981d2b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33602080"
---
# <a name="ltseegt-visual-basic"></a>&lt;vedere&gt; (Visual Basic)
Specifica un collegamento a un altro membro.  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<see cref="member"/>  
```  
  
#### <a name="parameters"></a>Parametri  
 `member`  
 Riferimento a un membro o a un campo disponibile per essere chiamato dall'ambiente di compilazione corrente. Il compilatore controlla che l'elemento di codice specificata esista e che passa `member` al nome dell'elemento XML di output. `member` deve essere racchiuso tra virgolette doppie (" ").  
  
## <a name="remarks"></a>Note  
 Utilizzare il `<see>` tag per specificare un collegamento nel testo. Utilizzare [ \<seealso >](../../../visual-basic/language-reference/xmldoc/seealso.md) per indicare il testo che si desidera visualizzare nella sezione "Vedere anche".  
  
 Compilare con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.  
  
## <a name="example"></a>Esempio  
 Questo esempio viene utilizzato il `<see>` tag il `UpdateRecord` sezione per fare riferimento alla relativa alle osservazioni di `DoesRecordExist` (metodo).  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/see_1.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Tag di commento XML](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
