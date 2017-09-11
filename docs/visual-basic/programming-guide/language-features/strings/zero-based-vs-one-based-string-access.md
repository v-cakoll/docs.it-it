---
title: Visual Studio in base zero. Accesso basato su una stringa in Visual Basic | Documenti di Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- strings [Visual Basic], indexing
ms.assetid: 0ed39f35-d68e-421d-ae14-460a5c0373b8
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: d8d1000f134fa8f99509d12727b9fbd84cb0e831
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="zero-based-vs-one-based-string-access-in-visual-basic"></a><span data-ttu-id="1acc7-102">Visual Studio in base zero. Accesso basato su una stringa in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1acc7-102">Zero-based vs. One-based String Access in Visual Basic</span></span>
<span data-ttu-id="1acc7-103">Questo argomento vengono confrontate come [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] e [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] forniscono l'accesso ai caratteri in una stringa.</span><span class="sxs-lookup"><span data-stu-id="1acc7-103">This topic compares how [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] and the [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] provide access to the characters in a string.</span></span> <span data-ttu-id="1acc7-104">Il [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] fornisce sempre l'accesso in base zero per i caratteri in una stringa, mentre [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] fornisce l'accesso in base zero e in base uno, a seconda della funzione.</span><span class="sxs-lookup"><span data-stu-id="1acc7-104">The [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] always provides zero-based access to the characters in a string, whereas [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] provides zero-based and one-based access, depending on the function.</span></span>  
  
## <a name="one-based"></a><span data-ttu-id="1acc7-105">In base uno</span><span class="sxs-lookup"><span data-stu-id="1acc7-105">One-Based</span></span>  
 <span data-ttu-id="1acc7-106">Per un esempio di base uno [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] funzione, prendere in considerazione il `Mid` (funzione).</span><span class="sxs-lookup"><span data-stu-id="1acc7-106">For an example of a one-based [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] function, consider the `Mid` function.</span></span> <span data-ttu-id="1acc7-107">Accetta un argomento che indica la posizione del carattere in cui inizia la sottostringa, a partire dalla posizione 1.</span><span class="sxs-lookup"><span data-stu-id="1acc7-107">It takes an argument that indicates the character position at which the substring will start, starting with position 1.</span></span> <span data-ttu-id="1acc7-108">Il [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] <xref:System.String.Substring%2A?displayProperty=fullName>metodo accetta un indice del carattere nella stringa in cui iniziare la sottostringa a partire dalla posizione 0.</xref:System.String.Substring%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="1acc7-108">The [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] <xref:System.String.Substring%2A?displayProperty=fullName> method takes an index of the character in the string at which the substring is to start, starting with position 0.</span></span> <span data-ttu-id="1acc7-109">Pertanto, se si dispone di una stringa "ABCDE", i singoli caratteri sono numerati 1,2,3,4,5 per l'utilizzo con il `Mid` funzione, ma 0,1,2,3,4 per l'utilizzo con il <xref:System.String.Substring%2A?displayProperty=fullName>(metodo).</xref:System.String.Substring%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="1acc7-109">Thus, if you have a string "ABCDE", the individual characters are numbered 1,2,3,4,5 for use with the `Mid` function, but 0,1,2,3,4 for use with the <xref:System.String.Substring%2A?displayProperty=fullName> method.</span></span>  
  
## <a name="zero-based"></a><span data-ttu-id="1acc7-110">In base zero</span><span class="sxs-lookup"><span data-stu-id="1acc7-110">Zero-Based</span></span>  
 <span data-ttu-id="1acc7-111">Per un esempio di oggetto in base zero [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] funzione, prendere in considerazione il `Split` (funzione).</span><span class="sxs-lookup"><span data-stu-id="1acc7-111">For an example of a zero-based [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] function, consider the `Split` function.</span></span> <span data-ttu-id="1acc7-112">Suddivide una stringa e restituisce una matrice contenente le sottostringhe.</span><span class="sxs-lookup"><span data-stu-id="1acc7-112">It splits a string and returns an array containing the substrings.</span></span> <span data-ttu-id="1acc7-113">Il [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] <xref:System.String.Split%2A?displayProperty=fullName>metodo inoltre suddivide una stringa e restituisce una matrice contenente le sottostringhe.</xref:System.String.Split%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="1acc7-113">The [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] <xref:System.String.Split%2A?displayProperty=fullName> method also splits a string and returns an array containing the substrings.</span></span> <span data-ttu-id="1acc7-114">Poiché il `Split` funzione e <xref:System.String.Split%2A>metodo restituiscono [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] matrici, devono essere in base zero.</xref:System.String.Split%2A></span><span class="sxs-lookup"><span data-stu-id="1acc7-114">Because the `Split` function and <xref:System.String.Split%2A> method return [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] arrays, they must be zero-based.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1acc7-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1acc7-115">See Also</span></span>  
 <span data-ttu-id="1acc7-116"><xref:Microsoft.VisualBasic.Strings.Mid%2A></xref:Microsoft.VisualBasic.Strings.Mid%2A></span><span class="sxs-lookup"><span data-stu-id="1acc7-116"><xref:Microsoft.VisualBasic.Strings.Mid%2A></span></span>   
 <span data-ttu-id="1acc7-117"><xref:Microsoft.VisualBasic.Strings.Split%2A></xref:Microsoft.VisualBasic.Strings.Split%2A></span><span class="sxs-lookup"><span data-stu-id="1acc7-117"><xref:Microsoft.VisualBasic.Strings.Split%2A></span></span>   
 <span data-ttu-id="1acc7-118"><xref:System.String.Substring%2A></xref:System.String.Substring%2A></span><span class="sxs-lookup"><span data-stu-id="1acc7-118"><xref:System.String.Substring%2A></span></span>   
 <span data-ttu-id="1acc7-119"><xref:System.String.Split%2A></xref:System.String.Split%2A></span><span class="sxs-lookup"><span data-stu-id="1acc7-119"><xref:System.String.Split%2A></span></span>   
<span data-ttu-id="1acc7-120"> [Introduzione alle stringhe in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)</span><span class="sxs-lookup"><span data-stu-id="1acc7-120"> [Introduction to Strings in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)</span></span>
