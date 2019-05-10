---
title: TextFieldParser non supporta i token di commento che contengono spazi vuoti
ms.date: 07/20/2015
f1_keywords:
- vbrTextFieldParser_WhitespaceInToken
ms.assetid: 55107656-270e-4bbb-841a-478904df8e07
ms.openlocfilehash: af0f09bb7a8afc3b6e63cfab1a7176ba26cf20a6
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64660890"
---
# <a name="textfieldparser-does-not-support-comment-tokens-that-contain-white-space"></a>TextFieldParser non supporta i token di commento che contengono spazi vuoti
È stato fornito un token di commento che contiene spazi vuoti. `TextFieldParser` non supporta i token di commento che contengono spazi vuoti a meno che lo spazio vuoto non sia presente all'inizio del token. Gli spazi vuoti all'inizio di un token vengono ignorati.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Fornire un token di commento corretto.  
  
## <a name="see-also"></a>Vedere anche

- [TextFieldParser.CommentTokens Property](xref:Microsoft.VisualBasic.FileIO.TextFieldParser.CommentTokens%2A)
- [Analisi dei file di testo con l'oggetto TextFieldParser](../../visual-basic/developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object.md)
- [Oggetto TextFieldParser](../../visual-basic/language-reference/objects/textfieldparser-object.md)
