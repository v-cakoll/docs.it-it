---
title: TextFieldParser non supporta i token di commento che contengono spazi vuoti
ms.date: 07/20/2015
f1_keywords:
- vbrTextFieldParser_WhitespaceInToken
ms.assetid: 55107656-270e-4bbb-841a-478904df8e07
ms.openlocfilehash: 9a14bc29ecfa917b6213f32cd170aa83d6f60f58
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54525014"
---
# <a name="textfieldparser-does-not-support-comment-tokens-that-contain-white-space"></a>TextFieldParser non supporta i token di commento che contengono spazi vuoti
È stato fornito un token di commento che contiene spazi vuoti. `TextFieldParser` non supporta i token di commento che contengono spazi vuoti a meno che lo spazio vuoto non sia presente all'inizio del token. Gli spazi vuoti all'inizio di un token vengono ignorati.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Fornire un token di commento corretto.  
  
## <a name="see-also"></a>Vedere anche

- [TextFieldParser.CommentTokens Property](xref:Microsoft.VisualBasic.FileIO.TextFieldParser.CommentTokens%2A)
- [Analisi dei file di testo con l'oggetto TextFieldParser](../../visual-basic/developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object.md)
- [Oggetto TextFieldParser](../../visual-basic/language-reference/objects/textfieldparser-object.md)
