---
title: TextFieldParser non supporta token di commento che contengono spazi vuoti
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrTextFieldParser_WhitespaceInToken
ms.assetid: 55107656-270e-4bbb-841a-478904df8e07
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0e5f41b1f1019459d55d5806f45301f4248e65fc
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="textfieldparser-does-not-support-comment-tokens-that-contain-whitespace"></a>TextFieldParser non supporta token di commento che contengono spazi vuoti
È stato fornito un token di commento che contiene spazi vuoti. `TextFieldParser` non supporta i token di commento che contengono spazi vuoti a meno che lo spazio vuoto non sia presente all'inizio del token. Gli spazi vuoti all'inizio di un token vengono ignorati.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Fornire un token di commento corretto.  
  
## <a name="see-also"></a>Vedere anche  
 [TextFieldParser.CommentTokens Property](http://msdn.microsoft.com/library/2e6b6435-4bee-4c14-a353-e8f2c82e2d61)  
 [Analisi dei file di testo con l'oggetto TextFieldParser](../../visual-basic/developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object.md)  
 [Oggetto TextFieldParser](../../visual-basic/language-reference/objects/textfieldparser-object.md)
