---
title: '&lt;c&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- c XML tag
- <c> XML tag
ms.assetid: 36ad5d1b-11f7-4012-8932-41962ac327d1
ms.openlocfilehash: 0e3ed08a62e9a52efa231c573a8061ff92d3cee0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54604157"
---
# <a name="ltcgt-visual-basic"></a>&lt;c&gt; (Visual Basic)
Indica che il testo all'interno di una descrizione è codice.  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<c>text</c>  
```  
  
#### <a name="parameters"></a>Parametri  
  
|Parametro|Descrizione|  
|---|---|  
|`text`|Il testo che si desidera indicare come codice.|  
  
## <a name="remarks"></a>Note  
 Il `<c>` tag offre un modo per indicare che il testo all'interno di una descrizione deve essere contrassegnato come codice. Usare [\<code>](../../../visual-basic/language-reference/xmldoc/code.md) per indicare più righe come codice.  
  
 Compilare con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.  
  
## <a name="example"></a>Esempio  
 Questo esempio Usa la `<c>` tag nella sezione di riepilogo per indicare che `Counter` è codice.  
  
 [!code-vb[VbVbcnXmlDocComments#1](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/c_1.vb)]  
  
## <a name="see-also"></a>Vedere anche
- [Tag di commento XML](../../../visual-basic/language-reference/xmldoc/index.md)
