---
title: "Procedura: scorrere un'enumerazione"
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [Visual Basic], iterating
- enumerations [Visual Basic], iterating
- ListBox control [Windows Forms], populating from an enumeration
ms.assetid: e5aa10eb-cfcd-4a3b-8e76-f06b8f2002be
ms.openlocfilehash: 6e8fd6760565a73d9d3b3d1d02fc872992eea354
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74354017"
---
# <a name="how-to-iterate-through-an-enumeration-in-visual-basic"></a><span data-ttu-id="b5474-102">Procedura: scorrere un'enumerazione in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b5474-102">How to: Iterate Through An Enumeration in Visual Basic</span></span>
<span data-ttu-id="b5474-103">Le enumerazioni offrono un modo pratico per usare i set di costanti correlate e per associare i valori delle costanti ai nomi.</span><span class="sxs-lookup"><span data-stu-id="b5474-103">Enumerations provide a convenient way to work with sets of related constants, and to associate constant values with names.</span></span> <span data-ttu-id="b5474-104">Per scorrere un'enumerazione, è possibile spostarla in una matrice usando il metodo <xref:System.Enum.GetValues%2A>.</span><span class="sxs-lookup"><span data-stu-id="b5474-104">To iterate through an enumeration, you can move it into an array using the <xref:System.Enum.GetValues%2A> method.</span></span> <span data-ttu-id="b5474-105">È anche possibile scorrere un'enumerazione usando un'istruzione `For...Each`, usando il metodo <xref:System.Enum.GetNames%2A> o <xref:System.Enum.GetValues%2A> per estrarre la stringa o il valore numerico.</span><span class="sxs-lookup"><span data-stu-id="b5474-105">You could also iterate through an enumeration using a `For...Each` statement, using the <xref:System.Enum.GetNames%2A> or <xref:System.Enum.GetValues%2A> method to extract the string or numeric value.</span></span>  
  
### <a name="to-iterate-through-an-enumeration"></a><span data-ttu-id="b5474-106">Per scorrere un'enumerazione</span><span class="sxs-lookup"><span data-stu-id="b5474-106">To iterate through an enumeration</span></span>  
  
- <span data-ttu-id="b5474-107">Dichiarare una matrice e convertirvi l'enumerazione con il metodo <xref:System.Enum.GetValues%2A> prima di passare la matrice come qualsiasi altra variabile.</span><span class="sxs-lookup"><span data-stu-id="b5474-107">Declare an array and convert the enumeration to it with the <xref:System.Enum.GetValues%2A> method before passing the array as you would any other variable.</span></span> <span data-ttu-id="b5474-108">Nell'esempio seguente vengono visualizzati tutti i membri dell'enumerazione <xref:Microsoft.VisualBasic.FirstDayOfWeek> durante l'iterazione dell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="b5474-108">The following example displays each member of the enumeration <xref:Microsoft.VisualBasic.FirstDayOfWeek> as it iterates through the enumeration.</span></span>  
  
     [!code-vb[VbEnumsTask#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="b5474-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b5474-109">See also</span></span>

- [<span data-ttu-id="b5474-110">Cenni preliminari sulle enumerazioni</span><span class="sxs-lookup"><span data-stu-id="b5474-110">Enumerations Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)
- [<span data-ttu-id="b5474-111">Procedura: dichiarare un'enumerazione</span><span class="sxs-lookup"><span data-stu-id="b5474-111">How to: Declare an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)
- [<span data-ttu-id="b5474-112">Quando usare un'enumerazione</span><span class="sxs-lookup"><span data-stu-id="b5474-112">When to Use an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)
- [<span data-ttu-id="b5474-113">Procedura: Determinare la stringa associata a un valore di enumerazione</span><span class="sxs-lookup"><span data-stu-id="b5474-113">How to: Determine the String Associated with an Enumeration Value</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [<span data-ttu-id="b5474-114">Procedura: Fare riferimento a un membro di enumerazione</span><span class="sxs-lookup"><span data-stu-id="b5474-114">How to: Refer to an Enumeration Member</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)
- [<span data-ttu-id="b5474-115">Qualifica di nomi ed enumerazioni</span><span class="sxs-lookup"><span data-stu-id="b5474-115">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [<span data-ttu-id="b5474-116">Matrici</span><span class="sxs-lookup"><span data-stu-id="b5474-116">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
