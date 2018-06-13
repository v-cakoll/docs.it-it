---
title: '&lt;seealso&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- <seealso> XML tag
- seealso XML tag
ms.assetid: 36050c95-1af2-4284-b9b6-1a70691ed978
ms.openlocfilehash: 1d45c0c5fa95de9cfa345c0bdbf496aa227b9af5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604679"
---
# <a name="ltseealsogt-visual-basic"></a>&lt;seealso&gt; (Visual Basic)
Specifica un collegamento visualizzato nella sezione Vedere anche.  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<seealso cref="member"/>  
```  
  
#### <a name="parameters"></a>Parametri  
 `member`  
 Riferimento a un membro o a un campo disponibile per essere chiamato dall'ambiente di compilazione corrente. Il compilatore controlla che l'elemento di codice specificata esista e che passa `member` al nome dell'elemento XML di output. `member` deve essere racchiuso tra virgolette doppie (" ").  
  
## <a name="remarks"></a>Note  
 Utilizzare il `<seealso>` tag per specificare il testo che si desidera visualizzare in una sezione Vedere anche. Usare [\<see>](../../../visual-basic/language-reference/xmldoc/see.md) per specificare un collegamento nel testo.  
  
 Compilare con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.  
  
## <a name="example"></a>Esempio  
 Questo esempio viene utilizzato il `<seealso>` tag il `DoesRecordExist` sezione per fare riferimento alla relativa alle osservazioni di `UpdateRecord` (metodo).  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/seealso_1.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Tag di commento XML](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
