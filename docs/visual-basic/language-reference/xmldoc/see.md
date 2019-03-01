---
title: <see> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- see XML tag
- <see> XML tag
ms.assetid: 7e18f60b-ef4a-4678-a797-5eb918635ca9
ms.openlocfilehash: c0f1293fa0161a9a11b4e80301f5c4c4ddffe7b1
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56969297"
---
# <a name="see-visual-basic"></a>\<see> (Visual Basic)
Specifica un collegamento a un altro membro.  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<see cref="member"/>  
```  
  
#### <a name="parameters"></a>Parametri  
 `member`  
 Riferimento a un membro o a un campo disponibile per essere chiamato dall'ambiente di compilazione corrente. Il compilatore verifica l'esistenza dell'elemento di codice specificato e passa `member` al nome dell'elemento nel file XML di output. `member` deve essere racchiuso tra virgolette doppie (" ").  
  
## <a name="remarks"></a>Note  
 Usare il `<see>` tag per specificare un collegamento nel testo. Uso [ \<seealso >](../../../visual-basic/language-reference/xmldoc/seealso.md) per indicare il testo che è possibile visualizzare in una sezione "Vedere anche".  
  
 Compilare con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.  
  
## <a name="example"></a>Esempio  
 Questo esempio Usa la `<see>` contrassegnare nel `UpdateRecord` per fare riferimento alla sezione relativa alle osservazioni di `DoesRecordExist` (metodo).  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>Vedere anche
- [Tag di commento XML](../../../visual-basic/language-reference/xmldoc/index.md)
