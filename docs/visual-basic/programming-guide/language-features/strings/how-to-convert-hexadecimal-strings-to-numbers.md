---
title: 'Procedura: convertire stringhe esadecimali in numeri (Visual Basic)'
ms.custom: 
ms.date: 01/31/2018
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- numbers [Visual Basic], hexadecimals
- hexadecimals [Visual Basic], decimals
- examples [Visual Basic], string conversion
- decimals [Visual Basic], hexadecimals
- string conversion [Visual Basic], hexadecimal to numbers
ms.assetid: 76675807-eadb-4c08-bd50-e6c6ff4b8ced
author: petrusha
ms.author: ronpet
ms.manager: wpickett
ms.openlocfilehash: c35ac615e3f87710f934a1cf66e6546625298bd0
ms.sourcegitcommit: d2da0142247ef42a219a5d2907f153e62dc6ea0d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/01/2018
---
# <a name="how-to-convert-hexadecimal-strings-to-numbers-visual-basic"></a><span data-ttu-id="77457-102">Procedura: convertire stringhe esadecimali in numeri (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="77457-102">How to: Convert Hexadecimal Strings to Numbers (Visual Basic)</span></span>
<span data-ttu-id="77457-103">In questo esempio converte una stringa esadecimale in un intero usando la <xref:System.Convert.ToInt32%2A?displayProperty=nameWithType> metodo.</span><span class="sxs-lookup"><span data-stu-id="77457-103">This example converts a hexadecimal string to an integer using the <xref:System.Convert.ToInt32%2A?displayProperty=nameWithType> method.</span></span>  
  
## <a name="to-convert-a-hexadecimal-string-to-a-number"></a><span data-ttu-id="77457-104">Per convertire una stringa esadecimale di un numero</span><span class="sxs-lookup"><span data-stu-id="77457-104">To convert a hexadecimal string to a number</span></span>  
  
-   <span data-ttu-id="77457-105">Utilizzare il <xref:System.Convert.ToInt32(System.String,System.Int32)> metodo per convertire il numero espresso in base 16 in un numero intero.</span><span class="sxs-lookup"><span data-stu-id="77457-105">Use the <xref:System.Convert.ToInt32(System.String,System.Int32)> method to convert the number expressed in base-16 to an integer.</span></span>  
  
     <span data-ttu-id="77457-106">Il primo argomento del <xref:System.Convert.ToInt32(System.String,System.Int32)> metodo è la stringa da convertire.</span><span class="sxs-lookup"><span data-stu-id="77457-106">The first argument of the <xref:System.Convert.ToInt32(System.String,System.Int32)> method is the string to convert.</span></span> <span data-ttu-id="77457-107">Il secondo argomento descrive la base il numero è espresso nel; esadecimale base 16.</span><span class="sxs-lookup"><span data-stu-id="77457-107">The second argument describes what base the number is expressed in; hexadecimal is base 16.</span></span>  
  
     [!code-vb[HexConversion](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-convert-hexadecimal-strings-to-numbers_1.vb)]  

- <span data-ttu-id="77457-108">Si noti che la stringa esadecimale presenta le restrizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="77457-108">Note that the hexadecimal string has the following restrictions:</span></span>

   - <span data-ttu-id="77457-109">Non può includere il `&h` prefisso.</span><span class="sxs-lookup"><span data-stu-id="77457-109">It cannot include the `&h` prefix.</span></span>
   - <span data-ttu-id="77457-110">Non può includere il `_` il separatore di cifre.</span><span class="sxs-lookup"><span data-stu-id="77457-110">It cannot include the `_` digit separator.</span></span>

   <span data-ttu-id="77457-111">Se il prefisso o un separatore di cifre è presente, la chiamata al <xref:System.Convert.ToInt32(System.String,System.Int32)> metodo genera un <xref:System.FormatException>.</span><span class="sxs-lookup"><span data-stu-id="77457-111">If the prefix or a digit separator is present, the call to the <xref:System.Convert.ToInt32(System.String,System.Int32)> method throws a <xref:System.FormatException>.</span></span>

## <a name="see-also"></a><span data-ttu-id="77457-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="77457-112">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Conversion.Hex%2A>  
 <xref:System.Convert.ToInt32%2A?displayProperty=nameWithType>
