---
title: <code> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- code XML tag
- <code> XML tag
ms.assetid: 925e5342-be05-45f2-bf66-7398bbd6710e
ms.openlocfilehash: d4e887e3bbbc01e4cef5278f67b8c4afe273bf28
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524029"
---
# <a name="code-visual-basic"></a>\<code > (Visual Basic)
Indica che il testo è costituito da più righe di codice.  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<code>content</code>  
```  
  
## <a name="parameters"></a>Parametri  
 `content`  
 Testo da contrassegnare come codice.  
  
## <a name="remarks"></a>Note  
 Usare il tag `<code>` per indicare più righe come codice. Usare [\<c>](../../../visual-basic/language-reference/xmldoc/c.md) per indicare che il testo all'interno di una descrizione deve essere contrassegnato come codice.  
  
 Compilare con [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.  
  
## <a name="example"></a>Esempio  
 Questo esempio usa il tag \<code > per includere il codice di esempio per l'uso del campo `ID`.  
  
 [!code-vb[VbVbcnXmlDocComments#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#2)]  
  
## <a name="see-also"></a>Vedere anche

- [Tag di commento XML](../../../visual-basic/language-reference/xmldoc/index.md)
