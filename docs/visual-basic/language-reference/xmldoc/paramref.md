---
title: '&lt;paramref&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- paramref XML tag
- <paramref> XML tag
ms.assetid: 8979d53b-beb1-41b7-b41e-6bbea1c17a03
ms.openlocfilehash: 153f5ddeeb7d09159049af4d466b0695f5cb6f23
ms.sourcegitcommit: a368166a51e5204c0224fbf5e46476e3ed122817
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/31/2018
ms.locfileid: "43331359"
---
# <a name="ltparamrefgt-visual-basic"></a>&lt;paramref&gt; (Visual Basic)
Formatta una parola come parametro.  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<paramref name="name"/>  
```  
  
#### <a name="parameters"></a>Parametri  
 `name`  
 Nome del parametro a cui fare riferimento. Racchiudere il nome tra virgolette doppie (" ").  
  
## <a name="remarks"></a>Note  
 Il `<paramref>` tag offre un modo per indicare che una parola è un parametro. Il file XML può essere elaborato per formattare questo parametro in modo specifico.  
  
 Compilare con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.  
  
## <a name="example"></a>Esempio  
 Questo esempio Usa la `<paramref>` tag per fare riferimento al `id` parametro.  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/paramref_1.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Tag di commento XML](../../../visual-basic/language-reference/xmldoc/index.md)
