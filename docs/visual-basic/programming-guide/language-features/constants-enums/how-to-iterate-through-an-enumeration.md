---
title: 'Procedura: scorrere un''enumerazione in Visual Basic'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- arrays [Visual Basic], iterating
- enumerations [Visual Basic], iterating
- ListBox control [Windows Forms], populating from an enumeration
ms.assetid: e5aa10eb-cfcd-4a3b-8e76-f06b8f2002be
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 439e6eae7d475316625a2cc1d3a70a9e7181f68a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-iterate-through-an-enumeration-in-visual-basic"></a><span data-ttu-id="cb660-102">Procedura: scorrere un'enumerazione in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="cb660-102">How to: Iterate Through An Enumeration in Visual Basic</span></span>
<span data-ttu-id="cb660-103">Le enumerazioni offrono un modo pratico per usare i set di costanti correlate e per associare i valori delle costanti ai nomi.</span><span class="sxs-lookup"><span data-stu-id="cb660-103">Enumerations provide a convenient way to work with sets of related constants, and to associate constant values with names.</span></span> <span data-ttu-id="cb660-104">Per scorrere un'enumerazione, è possibile spostarla in una matrice usando il <xref:System.Enum.GetValues%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="cb660-104">To iterate through an enumeration, you can move it into an array using the <xref:System.Enum.GetValues%2A> method.</span></span> <span data-ttu-id="cb660-105">È anche possibile scorrere un'enumerazione utilizzando un `For...Each` istruzione, utilizzando il <xref:System.Enum.GetNames%2A> o <xref:System.Enum.GetValues%2A> metodo per estrarre il valore di stringa o numerica.</span><span class="sxs-lookup"><span data-stu-id="cb660-105">You could also iterate through an enumeration using a `For...Each` statement, using the <xref:System.Enum.GetNames%2A> or <xref:System.Enum.GetValues%2A> method to extract the string or numeric value.</span></span>  
  
### <a name="to-iterate-through-an-enumeration"></a><span data-ttu-id="cb660-106">Per scorrere un'enumerazione</span><span class="sxs-lookup"><span data-stu-id="cb660-106">To iterate through an enumeration</span></span>  
  
-   <span data-ttu-id="cb660-107">Dichiarare una matrice in cui convertire l'enumerazione con la <xref:System.Enum.GetValues%2A> metodo prima di passare la matrice si sarebbe qualsiasi altra variabile.</span><span class="sxs-lookup"><span data-stu-id="cb660-107">Declare an array and convert the enumeration to it with the <xref:System.Enum.GetValues%2A> method before passing the array as you would any other variable.</span></span> <span data-ttu-id="cb660-108">Nell'esempio seguente viene visualizzato ogni membro dell'enumerazione <xref:Microsoft.VisualBasic.FirstDayOfWeek> mentre si scorre l'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="cb660-108">The following example displays each member of the enumeration <xref:Microsoft.VisualBasic.FirstDayOfWeek> as it iterates through the enumeration.</span></span>  
  
     [!code-vb[VbEnumsTask#7](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-iterate-through-an-enumeration_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="cb660-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cb660-109">See Also</span></span>  
 [<span data-ttu-id="cb660-110">Cenni preliminari sulle enumerazioni</span><span class="sxs-lookup"><span data-stu-id="cb660-110">Enumerations Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)  
 [<span data-ttu-id="cb660-111">Procedura: dichiarare un'enumerazione</span><span class="sxs-lookup"><span data-stu-id="cb660-111">How to: Declare an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)  
 [<span data-ttu-id="cb660-112">Quando usare un'enumerazione</span><span class="sxs-lookup"><span data-stu-id="cb660-112">When to Use an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)  
 [<span data-ttu-id="cb660-113">Procedura: Determinare la stringa associata a un valore di enumerazione</span><span class="sxs-lookup"><span data-stu-id="cb660-113">How to: Determine the String Associated with an Enumeration Value</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)  
 [<span data-ttu-id="cb660-114">Procedura: Fare riferimento a un membro di enumerazione</span><span class="sxs-lookup"><span data-stu-id="cb660-114">How to: Refer to an Enumeration Member</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)  
 [<span data-ttu-id="cb660-115">Qualifica di nomi ed enumerazioni</span><span class="sxs-lookup"><span data-stu-id="cb660-115">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)  
 [<span data-ttu-id="cb660-116">Array</span><span class="sxs-lookup"><span data-stu-id="cb660-116">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
