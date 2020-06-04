---
title: Le larghezze di tutti i campi, ad eccezione dell'ultimo elemento, devono essere maggiori di zero
ms.date: 07/20/2015
f1_keywords:
- vbrTextFieldParser_FieldWidthsMustPositive
ms.assetid: 41d8c661-a749-4c89-be56-905c6e7c3c9d
ms.openlocfilehash: 0e81652a0f9e97ce40851170ed050bd1f047ba5f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84412936"
---
# <a name="all-field-widths-except-the-last-element-must-be-greater-than-zero"></a><span data-ttu-id="29b1f-102">Le larghezze di tutti i campi, ad eccezione dell'ultimo elemento, devono essere maggiori di zero</span><span class="sxs-lookup"><span data-stu-id="29b1f-102">All field widths, except the last element, must be greater than zero</span></span>
<span data-ttu-id="29b1f-103">Le larghezze di tutti i campi, ad eccezione dell'ultimo elemento, devono essere maggiori di zero.</span><span class="sxs-lookup"><span data-stu-id="29b1f-103">All field widths, except the last element, must be greater than zero.</span></span> <span data-ttu-id="29b1f-104">Una larghezza di campo inferiore o uguale a zero nell'ultimo elemento indica che l'ultimo campo è di lunghezza variabile.</span><span class="sxs-lookup"><span data-stu-id="29b1f-104">A field width less than or equal to zero in the last element indicates the last field is of variable length.</span></span>  
  
 <span data-ttu-id="29b1f-105">L'operazione ha avuto esito negativo perché la larghezza di un campo che non è l'ultimo elemento è impostata su un valore uguale o minore di zero.</span><span class="sxs-lookup"><span data-stu-id="29b1f-105">The operation has failed because a field width other than the last element is set to zero or less.</span></span> <span data-ttu-id="29b1f-106">È possibile usare una larghezza di campo con un valore minore o uguale a zero nell'ultimo elemento per indicare che l'ultimo campo è di lunghezza variabile, ma non è possibile usarla per nessun altro elemento.</span><span class="sxs-lookup"><span data-stu-id="29b1f-106">A field width less than or equal to zero can be used as the last element to indicate that the last field is of variable length, but it cannot be used as any other element.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="29b1f-107">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="29b1f-107">To correct this error</span></span>  
  
- <span data-ttu-id="29b1f-108">Impostare la larghezza del campo di lunghezza corretta.</span><span class="sxs-lookup"><span data-stu-id="29b1f-108">Set the field width to the correct length.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29b1f-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="29b1f-109">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.SetFieldWidths%2A?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.FieldWidths>
- [<span data-ttu-id="29b1f-110">Procedura: Leggere da file di testo a larghezza fissa</span><span class="sxs-lookup"><span data-stu-id="29b1f-110">How to: Read From Fixed-width Text Files</span></span>](../developing-apps/programming/drives-directories-files/how-to-read-from-fixed-width-text-files.md)
- [<span data-ttu-id="29b1f-111">TextFieldParser Object</span><span class="sxs-lookup"><span data-stu-id="29b1f-111">TextFieldParser Object</span></span>](../language-reference/objects/textfieldparser-object.md)
