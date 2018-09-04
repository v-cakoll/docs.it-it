---
title: TextFieldParser non supporta i token di commento che contengono spazi vuoti
ms.date: 07/20/2015
f1_keywords:
- vbrTextFieldParser_WhitespaceInToken
ms.assetid: 55107656-270e-4bbb-841a-478904df8e07
ms.openlocfilehash: 2beda651dba952969593ffc7d64f01fd51ab7919
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43556276"
---
# <a name="textfieldparser-does-not-support-comment-tokens-that-contain-white-space"></a>TextFieldParser non supporta i token di commento che contengono spazi vuoti
È stato fornito un token di commento che contiene spazi vuoti. `TextFieldParser` non supporta i token di commento che contengono spazi vuoti a meno che lo spazio vuoto non sia presente all'inizio del token. Gli spazi vuoti all'inizio di un token vengono ignorati.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Fornire un token di commento corretto.  
  
## <a name="see-also"></a>Vedere anche  
 [TextFieldParser.CommentTokens Property](https://msdn.microsoft.com/library/2e6b6435-4bee-4c14-a353-e8f2c82e2d61)  
 [Analisi dei file di testo con l'oggetto TextFieldParser](../../visual-basic/developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object.md)  
 [Oggetto TextFieldParser](../../visual-basic/language-reference/objects/textfieldparser-object.md)
