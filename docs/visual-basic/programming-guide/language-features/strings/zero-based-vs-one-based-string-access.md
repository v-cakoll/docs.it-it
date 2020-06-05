---
title: Accesso con stringa in base zero e in base uno
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], indexing
ms.assetid: 0ed39f35-d68e-421d-ae14-460a5c0373b8
ms.openlocfilehash: ce2fcb2610c09a9591a5fd79da4baa74cc533c99
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84363656"
---
# <a name="zero-based-vs-one-based-string-access-in-visual-basic"></a><span data-ttu-id="3464d-102">Accesso alle stringhe in base zero o in base uno in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3464d-102">Zero-based vs. One-based String Access in Visual Basic</span></span>
<span data-ttu-id="3464d-103">In questo argomento viene illustrato il modo in cui Visual Basic e il .NET Framework consentono di accedere ai caratteri in una stringa.</span><span class="sxs-lookup"><span data-stu-id="3464d-103">This topic compares how Visual Basic and the .NET Framework provide access to the characters in a string.</span></span> <span data-ttu-id="3464d-104">Il .NET Framework fornisce sempre l'accesso in base zero ai caratteri in una stringa, mentre Visual Basic fornisce l'accesso in base zero e uno a seconda della funzione.</span><span class="sxs-lookup"><span data-stu-id="3464d-104">The .NET Framework always provides zero-based access to the characters in a string, whereas Visual Basic provides zero-based and one-based access, depending on the function.</span></span>  
  
## <a name="one-based"></a><span data-ttu-id="3464d-105">In base uno</span><span class="sxs-lookup"><span data-stu-id="3464d-105">One-Based</span></span>  
 <span data-ttu-id="3464d-106">Per un esempio di una funzione Visual Basic basata su uno, prendere in considerazione la `Mid` funzione.</span><span class="sxs-lookup"><span data-stu-id="3464d-106">For an example of a one-based Visual Basic function, consider the `Mid` function.</span></span> <span data-ttu-id="3464d-107">Accetta un argomento che indica la posizione del carattere in corrispondenza della quale verrà avviata la sottostringa, a partire dalla posizione 1.</span><span class="sxs-lookup"><span data-stu-id="3464d-107">It takes an argument that indicates the character position at which the substring will start, starting with position 1.</span></span> <span data-ttu-id="3464d-108">Il <xref:System.String.Substring%2A?displayProperty=nameWithType> metodo .NET Framework accetta un indice del carattere nella stringa in corrispondenza del quale viene avviata la sottostringa, a partire dalla posizione 0.</span><span class="sxs-lookup"><span data-stu-id="3464d-108">The .NET Framework <xref:System.String.Substring%2A?displayProperty=nameWithType> method takes an index of the character in the string at which the substring is to start, starting with position 0.</span></span> <span data-ttu-id="3464d-109">Pertanto, se si dispone di una stringa "ABCDe", i singoli caratteri sono numerati 1, 2, 3, 4, 5 per l'utilizzo con la `Mid` funzione, ma 0, 1, 2, 3, 4 per l'utilizzo con il <xref:System.String.Substring%2A?displayProperty=nameWithType> metodo.</span><span class="sxs-lookup"><span data-stu-id="3464d-109">Thus, if you have a string "ABCDE", the individual characters are numbered 1,2,3,4,5 for use with the `Mid` function, but 0,1,2,3,4 for use with the <xref:System.String.Substring%2A?displayProperty=nameWithType> method.</span></span>  
  
## <a name="zero-based"></a><span data-ttu-id="3464d-110">In base zero</span><span class="sxs-lookup"><span data-stu-id="3464d-110">Zero-Based</span></span>  
 <span data-ttu-id="3464d-111">Per un esempio di funzione Visual Basic in base zero, prendere in considerazione la `Split` funzione.</span><span class="sxs-lookup"><span data-stu-id="3464d-111">For an example of a zero-based Visual Basic function, consider the `Split` function.</span></span> <span data-ttu-id="3464d-112">Suddivide una stringa e restituisce una matrice contenente le sottostringhe.</span><span class="sxs-lookup"><span data-stu-id="3464d-112">It splits a string and returns an array containing the substrings.</span></span> <span data-ttu-id="3464d-113">Il <xref:System.String.Split%2A?displayProperty=nameWithType> metodo .NET Framework suddivide anche una stringa e restituisce una matrice contenente le sottostringhe.</span><span class="sxs-lookup"><span data-stu-id="3464d-113">The .NET Framework <xref:System.String.Split%2A?displayProperty=nameWithType> method also splits a string and returns an array containing the substrings.</span></span> <span data-ttu-id="3464d-114">Poiché la `Split` funzione e il <xref:System.String.Split%2A> metodo restituiscono matrici di .NET Framework, devono essere in base zero.</span><span class="sxs-lookup"><span data-stu-id="3464d-114">Because the `Split` function and <xref:System.String.Split%2A> method return .NET Framework arrays, they must be zero-based.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3464d-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3464d-115">See also</span></span>

- <xref:Microsoft.VisualBasic.Strings.Mid%2A>
- <xref:Microsoft.VisualBasic.Strings.Split%2A>
- <xref:System.String.Substring%2A>
- <xref:System.String.Split%2A>
- [<span data-ttu-id="3464d-116">Introduzione alle stringhe in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3464d-116">Introduction to Strings in Visual Basic</span></span>](introduction-to-strings.md)
