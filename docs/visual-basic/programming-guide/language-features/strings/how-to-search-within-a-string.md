---
title: "Procedura: Cercare all'interno di una stringa (Visual Basic)"
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], finding
- strings [Visual Basic], searching
- examples [Visual Basic], strings
ms.assetid: ae4c79e0-08ea-489f-bdb2-5eb6d355f284
ms.openlocfilehash: 6ac75c99270deb14e23691d32e8ebf4e8b0a91b6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54542548"
---
# <a name="how-to-search-within-a-string-visual-basic"></a><span data-ttu-id="f32b9-102">Procedura: Cercare all'interno di una stringa (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f32b9-102">How to: Search Within a String (Visual Basic)</span></span>
<span data-ttu-id="f32b9-103">Questo esempio chiama il <xref:System.String.IndexOf%2A> metodo su un <xref:System.String> per segnalare l'indice della prima occorrenza di una sottostringa.</span><span class="sxs-lookup"><span data-stu-id="f32b9-103">This example calls the <xref:System.String.IndexOf%2A> method on a <xref:System.String> object to report the index of the first occurrence of a substring.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f32b9-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="f32b9-104">Example</span></span>  
 [!code-vb[VbVbalrStrings#71](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-search-within-a-string_1.vb)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f32b9-105">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="f32b9-105">Compiling the Code</span></span>  
 <span data-ttu-id="f32b9-106">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="f32b9-106">This example requires:</span></span>  
  
-   <span data-ttu-id="f32b9-107">Un' `Imports` istruzione che specifica il <xref:System> dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="f32b9-107">An `Imports` statement specifying the <xref:System> namespace.</span></span> <span data-ttu-id="f32b9-108">Per altre informazioni, vedere [Istruzione Imports (tipo e spazio dei nomi .NET)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span><span class="sxs-lookup"><span data-stu-id="f32b9-108">For more information, see [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="f32b9-109">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="f32b9-109">Robust Programming</span></span>  
 <span data-ttu-id="f32b9-110">Il <xref:System.String.IndexOf%2A> metodo segnala la posizione del primo carattere della prima occorrenza della sottostringa.</span><span class="sxs-lookup"><span data-stu-id="f32b9-110">The <xref:System.String.IndexOf%2A> method reports the location of the first character of the first occurrence of the substring.</span></span> <span data-ttu-id="f32b9-111">L'indice è basato su 0, ovvero che il primo carattere della stringa ha indice 0.</span><span class="sxs-lookup"><span data-stu-id="f32b9-111">The index is 0-based, which means the first character of a string has an index of 0.</span></span>  
  
 <span data-ttu-id="f32b9-112">Se <xref:System.String.IndexOf%2A> non trova la sottostringa, restituisce -1.</span><span class="sxs-lookup"><span data-stu-id="f32b9-112">If <xref:System.String.IndexOf%2A> does not find the substring, it returns -1.</span></span>  
  
 <span data-ttu-id="f32b9-113">Il <xref:System.String.IndexOf%2A> metodo tra maiuscole e minuscole e Usa le impostazioni cultura correnti.</span><span class="sxs-lookup"><span data-stu-id="f32b9-113">The <xref:System.String.IndexOf%2A> method is case-sensitive and uses the current culture.</span></span>  
  
 <span data-ttu-id="f32b9-114">Per un controllo ottimale degli errori, è possibile racchiudere la stringa di ricerca nel `Try` blocco di un [Try... Catch... Istruzione finally](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md) costruzione.</span><span class="sxs-lookup"><span data-stu-id="f32b9-114">For optimal error control, you might want to enclose the string search in the `Try` block of a [Try...Catch...Finally Statement](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md) construction.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f32b9-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f32b9-115">See also</span></span>
- <xref:System.String.IndexOf%2A>
- [<span data-ttu-id="f32b9-116">Istruzione Try...Catch...Finally</span><span class="sxs-lookup"><span data-stu-id="f32b9-116">Try...Catch...Finally Statement</span></span>](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [<span data-ttu-id="f32b9-117">Introduzione alle stringhe in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f32b9-117">Introduction to Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
- [<span data-ttu-id="f32b9-118">Stringhe</span><span class="sxs-lookup"><span data-stu-id="f32b9-118">Strings</span></span>](../../../../visual-basic/programming-guide/language-features/strings/index.md)
