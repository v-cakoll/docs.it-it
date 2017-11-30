---
title: 'Procedura: convertire una matrice di byte in una stringa in Visual Basic'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- string conversion [Visual Basic], arrays
- byte arrays [Visual Basic], converting to strings
- examples [Visual Basic], strings
- arrays [Visual Basic], converting to strings
ms.assetid: d0dc8317-9ab3-4324-99f7-3f5788c0e72a
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4133109ef334c7e87884deb7db963db3291da1d5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-convert-an-array-of-bytes-into-a-string-in-visual-basic"></a><span data-ttu-id="f0d22-102">Procedura: convertire una matrice di byte in una stringa in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f0d22-102">How to: Convert an Array of Bytes into a String in Visual Basic</span></span>
<span data-ttu-id="f0d22-103">In questo argomento viene illustrato come convertire i byte di una matrice di byte in una stringa.</span><span class="sxs-lookup"><span data-stu-id="f0d22-103">This topic shows how to convert the bytes from a byte array into a string.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f0d22-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="f0d22-104">Example</span></span>  
 <span data-ttu-id="f0d22-105">Questo esempio viene utilizzato il <xref:System.Text.Encoding.GetString%2A> metodo la <xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType> classe per convertire tutti i byte di una matrice di byte in una stringa di codifica.</span><span class="sxs-lookup"><span data-stu-id="f0d22-105">This example uses the <xref:System.Text.Encoding.GetString%2A> method of the <xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType> encoding class to convert all the bytes from a byte array into a string.</span></span>  
  
 [!code-vb[VbVbalrStrings#72](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-convert-an-array-of-bytes-into-a-string_1.vb)]  
  
 <span data-ttu-id="f0d22-106">È possibile scegliere tra diverse opzioni di codifica per convertire una matrice di byte in una stringa:</span><span class="sxs-lookup"><span data-stu-id="f0d22-106">You can choose from several encoding options to convert a byte array into a string:</span></span>  
  
-   <span data-ttu-id="f0d22-107"><xref:System.Text.Encoding.ASCII%2A?displayProperty=nameWithType>: Ottiene una codifica per i caratteri ASCII (7 bit) del set.</span><span class="sxs-lookup"><span data-stu-id="f0d22-107"><xref:System.Text.Encoding.ASCII%2A?displayProperty=nameWithType>: Gets an encoding for the ASCII (7-bit) character set.</span></span>  
  
-   <span data-ttu-id="f0d22-108"><xref:System.Text.Encoding.BigEndianUnicode%2A?displayProperty=nameWithType>: Ottiene una codifica per il formato UTF-16 nell'ordine dei byte big-endian.</span><span class="sxs-lookup"><span data-stu-id="f0d22-108"><xref:System.Text.Encoding.BigEndianUnicode%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-16 format using the big-endian byte order.</span></span>  
  
-   <span data-ttu-id="f0d22-109"><xref:System.Text.Encoding.Default%2A?displayProperty=nameWithType>: Ottiene una codifica per la tabella codici ANSI corrente del sistema.</span><span class="sxs-lookup"><span data-stu-id="f0d22-109"><xref:System.Text.Encoding.Default%2A?displayProperty=nameWithType>: Gets an encoding for the system's current ANSI code page.</span></span>  
  
-   <span data-ttu-id="f0d22-110"><xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType>: Ottiene una codifica per il formato UTF-16 nell'ordine dei byte little-endian.</span><span class="sxs-lookup"><span data-stu-id="f0d22-110"><xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-16 format using the little-endian byte order.</span></span>  
  
-   <span data-ttu-id="f0d22-111"><xref:System.Text.Encoding.UTF32%2A?displayProperty=nameWithType>: Ottiene una codifica per il formato UTF-32 Usa l'ordine dei byte little-endian.</span><span class="sxs-lookup"><span data-stu-id="f0d22-111"><xref:System.Text.Encoding.UTF32%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-32 format using the little-endian byte order.</span></span>  
  
-   <span data-ttu-id="f0d22-112"><xref:System.Text.Encoding.UTF7%2A?displayProperty=nameWithType>: Ottiene una codifica per il formato UTF-7.</span><span class="sxs-lookup"><span data-stu-id="f0d22-112"><xref:System.Text.Encoding.UTF7%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-7 format.</span></span>  
  
-   <span data-ttu-id="f0d22-113"><xref:System.Text.Encoding.UTF8%2A?displayProperty=nameWithType>: Ottiene una codifica per il formato UTF-8.</span><span class="sxs-lookup"><span data-stu-id="f0d22-113"><xref:System.Text.Encoding.UTF8%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-8 format.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0d22-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f0d22-114">See Also</span></span>  
 <xref:System.Text.Encoding?displayProperty=nameWithType>  
 <xref:System.Text.Encoding.GetString%2A>  
 [<span data-ttu-id="f0d22-115">Procedura: convertire stringhe in una matrice di byte in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f0d22-115">How to: Convert Strings into an Array of Bytes in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-strings-into-an-array-of-bytes.md)
