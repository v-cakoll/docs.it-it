---
title: Le virgolette non sono un token di commento valido per i campi delimitati se EscapeQuote è impostato su True
ms.date: 07/20/2015
f1_keywords:
- vbrTextFieldParser_InvalidComment
ms.assetid: 636d4b81-00ba-4cfd-98f7-4d57036f494d
ms.openlocfilehash: 6e55fde395cec2fcd4053e66d855750945ea1448
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58840861"
---
# <a name="a-double-quote-is-not-a-valid-comment-token-for-delimited-fields-where-escapequote-is-set-to-true"></a>Le virgolette non sono un token di commento valido per i campi delimitati se EscapeQuote è impostato su True
Sono state fornite le virgolette come delimitatore per `TextFieldParser`, ma `EscapeQuotes` è impostato su `True`.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Impostare `EscapeQuotes` su `False`.  
  
## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.SetDelimiters%2A>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.Delimiters%2A>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser>
- [Procedura: Leggere da file di testo con valori delimitati da virgole](../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-comma-delimited-text-files.md)
