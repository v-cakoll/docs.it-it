---
title: "Procedura: Scorrere un'enumerazione in Visual Basic"
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [Visual Basic], iterating
- enumerations [Visual Basic], iterating
- ListBox control [Windows Forms], populating from an enumeration
ms.assetid: e5aa10eb-cfcd-4a3b-8e76-f06b8f2002be
ms.openlocfilehash: dd7a540839fd833d3a316506e433c576edae5384
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56979086"
---
# <a name="how-to-iterate-through-an-enumeration-in-visual-basic"></a><span data-ttu-id="b5a1d-102">Procedura: Scorrere un'enumerazione in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b5a1d-102">How to: Iterate Through An Enumeration in Visual Basic</span></span>
<span data-ttu-id="b5a1d-103">Le enumerazioni offrono un modo pratico per usare i set di costanti correlate e per associare i valori delle costanti ai nomi.</span><span class="sxs-lookup"><span data-stu-id="b5a1d-103">Enumerations provide a convenient way to work with sets of related constants, and to associate constant values with names.</span></span> <span data-ttu-id="b5a1d-104">Per scorrere un'enumerazione, è possibile spostarlo in una matrice usando la <xref:System.Enum.GetValues%2A> (metodo).</span><span class="sxs-lookup"><span data-stu-id="b5a1d-104">To iterate through an enumeration, you can move it into an array using the <xref:System.Enum.GetValues%2A> method.</span></span> <span data-ttu-id="b5a1d-105">È stato possibile anche scorrere un'enumerazione utilizzando un `For...Each` istruzione, usando il <xref:System.Enum.GetNames%2A> o <xref:System.Enum.GetValues%2A> metodo per estrarre il valore di stringa o numerica.</span><span class="sxs-lookup"><span data-stu-id="b5a1d-105">You could also iterate through an enumeration using a `For...Each` statement, using the <xref:System.Enum.GetNames%2A> or <xref:System.Enum.GetValues%2A> method to extract the string or numeric value.</span></span>  
  
### <a name="to-iterate-through-an-enumeration"></a><span data-ttu-id="b5a1d-106">Per scorrere un'enumerazione</span><span class="sxs-lookup"><span data-stu-id="b5a1d-106">To iterate through an enumeration</span></span>  
  
-   <span data-ttu-id="b5a1d-107">Dichiarare una matrice e convertire l'enumerazione a esso con il <xref:System.Enum.GetValues%2A> metodo prima di passare la matrice come si sarebbe qualsiasi altra variabile.</span><span class="sxs-lookup"><span data-stu-id="b5a1d-107">Declare an array and convert the enumeration to it with the <xref:System.Enum.GetValues%2A> method before passing the array as you would any other variable.</span></span> <span data-ttu-id="b5a1d-108">Nell'esempio seguente consente di visualizzare ogni membro dell'enumerazione <xref:Microsoft.VisualBasic.FirstDayOfWeek> perché viene iterata tramite l'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="b5a1d-108">The following example displays each member of the enumeration <xref:Microsoft.VisualBasic.FirstDayOfWeek> as it iterates through the enumeration.</span></span>  
  
     [!code-vb[VbEnumsTask#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="b5a1d-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b5a1d-109">See also</span></span>
- [<span data-ttu-id="b5a1d-110">Cenni preliminari sulle enumerazioni</span><span class="sxs-lookup"><span data-stu-id="b5a1d-110">Enumerations Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)
- [<span data-ttu-id="b5a1d-111">Procedura: Dichiarare un'enumerazione</span><span class="sxs-lookup"><span data-stu-id="b5a1d-111">How to: Declare an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)
- [<span data-ttu-id="b5a1d-112">Quando usare un'enumerazione</span><span class="sxs-lookup"><span data-stu-id="b5a1d-112">When to Use an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)
- [<span data-ttu-id="b5a1d-113">Procedura: Determinare la stringa associata a un valore di enumerazione</span><span class="sxs-lookup"><span data-stu-id="b5a1d-113">How to: Determine the String Associated with an Enumeration Value</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [<span data-ttu-id="b5a1d-114">Procedura: Fare riferimento a un membro di enumerazione</span><span class="sxs-lookup"><span data-stu-id="b5a1d-114">How to: Refer to an Enumeration Member</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)
- [<span data-ttu-id="b5a1d-115">Qualifica di nomi ed enumerazioni</span><span class="sxs-lookup"><span data-stu-id="b5a1d-115">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [<span data-ttu-id="b5a1d-116">Matrici</span><span class="sxs-lookup"><span data-stu-id="b5a1d-116">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
