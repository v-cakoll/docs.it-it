---
title: Le virgolette non sono un token di commento valido per i campi delimitati se EscapeQuote è impostato su True
ms.date: 07/20/2015
f1_keywords:
- vbrTextFieldParser_InvalidComment
ms.assetid: 636d4b81-00ba-4cfd-98f7-4d57036f494d
ms.openlocfilehash: a66d43d249a12ffa552073866f2e0a1e6d453608
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409939"
---
# <a name="a-double-quote-is-not-a-valid-comment-token-for-delimited-fields-where-escapequote-is-set-to-true"></a><span data-ttu-id="c5a97-102">Le virgolette non sono un token di commento valido per i campi delimitati se EscapeQuote è impostato su True</span><span class="sxs-lookup"><span data-stu-id="c5a97-102">A double quote is not a valid comment token for delimited fields where EscapeQuote is set to True</span></span>

<span data-ttu-id="c5a97-103">Sono state fornite le virgolette come delimitatore per `TextFieldParser`, ma `EscapeQuotes` è impostato su `True`.</span><span class="sxs-lookup"><span data-stu-id="c5a97-103">A quotation mark has been supplied as the delimiter for the `TextFieldParser`, but `EscapeQuotes` is set to `True`.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c5a97-104">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="c5a97-104">To correct this error</span></span>  
  
- <span data-ttu-id="c5a97-105">Impostare `EscapeQuotes` su `False`.</span><span class="sxs-lookup"><span data-stu-id="c5a97-105">Set `EscapeQuotes` to `False`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5a97-106">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c5a97-106">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.SetDelimiters%2A>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.Delimiters%2A>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser>
- [<span data-ttu-id="c5a97-107">Procedura: Leggere da file di testo con valori delimitati da virgole</span><span class="sxs-lookup"><span data-stu-id="c5a97-107">How to: Read From Comma-Delimited Text Files</span></span>](../../developing-apps/programming/drives-directories-files/how-to-read-from-comma-delimited-text-files.md)
