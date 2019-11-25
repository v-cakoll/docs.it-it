---
title: Le virgolette non sono un token di commento valido per i campi delimitati se EscapeQuote è impostato su True
ms.date: 07/20/2015
f1_keywords:
- vbrTextFieldParser_InvalidComment
ms.assetid: 636d4b81-00ba-4cfd-98f7-4d57036f494d
ms.openlocfilehash: df7868c510eaacbad1d4421259234f4187f60cd7
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/12/2019
ms.locfileid: "73976212"
---
# <a name="a-double-quote-is-not-a-valid-comment-token-for-delimited-fields-where-escapequote-is-set-to-true"></a>Le virgolette non sono un token di commento valido per i campi delimitati se EscapeQuote è impostato su True

Sono state fornite le virgolette come delimitatore per `TextFieldParser`, ma `EscapeQuotes` è impostato su `True`.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Impostare `EscapeQuotes` su `False`.  
  
## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.SetDelimiters%2A>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.Delimiters%2A>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser>
- [Procedura: leggere da file di testo delimitati da virgola](../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-comma-delimited-text-files.md)
