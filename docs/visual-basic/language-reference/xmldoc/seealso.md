---
title: '&lt;seealso&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- <seealso> XML tag
- seealso XML tag
ms.assetid: 36050c95-1af2-4284-b9b6-1a70691ed978
ms.openlocfilehash: a792bbea108bcdf33d430c47773466ef3dccdb0c
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2018
ms.locfileid: "47401183"
---
# <a name="ltseealsogt-visual-basic"></a>&lt;seealso&gt; (Visual Basic)
Specifica un collegamento che viene visualizzato nella sezione Vedere anche.  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<seealso cref="member"/>  
```  
  
#### <a name="parameters"></a>Parametri  
 `member`  
 Riferimento a un membro o a un campo disponibile per essere chiamato dall'ambiente di compilazione corrente. Il compilatore controlla che l'elemento di codice specificato esista e passa `member` al nome dell'elemento nel file XML di output. `member` deve essere racchiuso tra virgolette doppie (" ").  
  
## <a name="remarks"></a>Note  
 Usare il `<seealso>` tag per specificare il testo che si desidera visualizzare in una sezione Vedere anche. Usare [\<see>](../../../visual-basic/language-reference/xmldoc/see.md) per specificare un collegamento nel testo.  
  
 Compilare con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.  
  
## <a name="example"></a>Esempio  
 Questo esempio Usa la `<seealso>` contrassegnare nel `DoesRecordExist` per fare riferimento alla sezione relativa alle osservazioni di `UpdateRecord` (metodo).  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/seealso_1.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Tag di commento XML](../../../visual-basic/language-reference/xmldoc/index.md)
