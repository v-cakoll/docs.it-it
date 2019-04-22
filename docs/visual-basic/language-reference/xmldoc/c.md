---
title: <c> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- c XML tag
- <c> XML tag
ms.assetid: 36ad5d1b-11f7-4012-8932-41962ac327d1
ms.openlocfilehash: 9be9f9e96fc1b79ea97d54c54352da63b93ef264
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58838040"
---
# <a name="c-visual-basic"></a>\<c> (Visual Basic)
Indica che il testo all'interno di una descrizione è codice.  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<c>text</c>  
```  
  
## <a name="parameters"></a>Parametri  
  
|Parametro|Descrizione|  
|---|---|  
|`text`|Il testo che si desidera indicare come codice.|  
  
## <a name="remarks"></a>Note  
 Il `<c>` tag offre un modo per indicare che il testo all'interno di una descrizione deve essere contrassegnato come codice. Usare [\<code>](../../../visual-basic/language-reference/xmldoc/code.md) per indicare più righe come codice.  
  
 Compilare con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.  
  
## <a name="example"></a>Esempio  
 Questo esempio Usa la `<c>` tag nella sezione di riepilogo per indicare che `Counter` è codice.  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a>Vedere anche

- [Tag di commento XML](../../../visual-basic/language-reference/xmldoc/index.md)
