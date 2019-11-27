---
title: 'Procedura: convertire stringhe esadecimali in numeri'
ms.date: 01/31/2018
helpviewer_keywords:
- numbers [Visual Basic], hexadecimals
- hexadecimals [Visual Basic], decimals
- examples [Visual Basic], string conversion
- decimals [Visual Basic], hexadecimals
- string conversion [Visual Basic], hexadecimal to numbers
ms.assetid: 76675807-eadb-4c08-bd50-e6c6ff4b8ced
ms.openlocfilehash: f0a97a0c212a64bfa4db4606ee526b666f07877a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347169"
---
# <a name="how-to-convert-hexadecimal-strings-to-numbers-visual-basic"></a><span data-ttu-id="10db0-102">Procedura: convertire stringhe esadecimali in numeri (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="10db0-102">How to: Convert Hexadecimal Strings to Numbers (Visual Basic)</span></span>

<span data-ttu-id="10db0-103">Questo esempio converte una stringa esadecimale in un Integer usando il metodo <xref:System.Convert.ToInt32%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="10db0-103">This example converts a hexadecimal string to an integer using the <xref:System.Convert.ToInt32%2A?displayProperty=nameWithType> method.</span></span>

## <a name="to-convert-a-hexadecimal-string-to-a-number"></a><span data-ttu-id="10db0-104">Per convertire una stringa esadecimale in un numero</span><span class="sxs-lookup"><span data-stu-id="10db0-104">To convert a hexadecimal string to a number</span></span>

- <span data-ttu-id="10db0-105">Usare il metodo <xref:System.Convert.ToInt32(System.String,System.Int32)> per convertire il numero espresso in base-16 in un valore integer.</span><span class="sxs-lookup"><span data-stu-id="10db0-105">Use the <xref:System.Convert.ToInt32(System.String,System.Int32)> method to convert the number expressed in base-16 to an integer.</span></span>

  <span data-ttu-id="10db0-106">Il primo argomento del metodo <xref:System.Convert.ToInt32(System.String,System.Int32)> è la stringa da convertire.</span><span class="sxs-lookup"><span data-stu-id="10db0-106">The first argument of the <xref:System.Convert.ToInt32(System.String,System.Int32)> method is the string to convert.</span></span> <span data-ttu-id="10db0-107">Il secondo argomento descrive la base in cui è espresso il numero; il formato esadecimale è base 16.</span><span class="sxs-lookup"><span data-stu-id="10db0-107">The second argument describes what base the number is expressed in; hexadecimal is base 16.</span></span>

  [!code-vb[VbVbalrStrings#62](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#62)]

- <span data-ttu-id="10db0-108">Si noti che la stringa esadecimale presenta le restrizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="10db0-108">Note that the hexadecimal string has the following restrictions:</span></span>

  - <span data-ttu-id="10db0-109">Non può includere il prefisso `&h`.</span><span class="sxs-lookup"><span data-stu-id="10db0-109">It cannot include the `&h` prefix.</span></span>
  - <span data-ttu-id="10db0-110">Non può includere il separatore di cifre `_`.</span><span class="sxs-lookup"><span data-stu-id="10db0-110">It cannot include the `_` digit separator.</span></span>

  <span data-ttu-id="10db0-111">Se è presente il prefisso o un separatore di cifre, la chiamata al metodo <xref:System.Convert.ToInt32(System.String,System.Int32)> genera un'<xref:System.FormatException>.</span><span class="sxs-lookup"><span data-stu-id="10db0-111">If the prefix or a digit separator is present, the call to the <xref:System.Convert.ToInt32(System.String,System.Int32)> method throws a <xref:System.FormatException>.</span></span>

## <a name="see-also"></a><span data-ttu-id="10db0-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="10db0-112">See also</span></span>

- <xref:Microsoft.VisualBasic.Conversion.Hex%2A>
- <xref:System.Convert.ToInt32%2A?displayProperty=nameWithType>
