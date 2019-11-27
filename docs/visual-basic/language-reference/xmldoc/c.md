---
title: <c>
ms.date: 07/20/2015
helpviewer_keywords:
- c XML tag
- <c> XML tag
ms.assetid: 36ad5d1b-11f7-4012-8932-41962ac327d1
ms.openlocfilehash: 857ea1ccca4d74daf65bba03845004561afefd55
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348507"
---
# <a name="c-visual-basic"></a>> \<c (Visual Basic)
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
 Il tag `<c>` fornisce un modo per indicare che il testo all'interno di una descrizione deve essere contrassegnato come codice. Usare [\<code>](../../../visual-basic/language-reference/xmldoc/code.md) per indicare più righe come codice.  
  
 Compilare con [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.  
  
## <a name="example"></a>Esempio  
 Questo esempio usa il tag `<c>` nella sezione Summary per indicare che `Counter` è il codice.  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a>Vedere anche

- [Tag di commento XML](../../../visual-basic/language-reference/xmldoc/index.md)
