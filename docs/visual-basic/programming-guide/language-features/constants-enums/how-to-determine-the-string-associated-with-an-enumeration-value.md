---
title: 'Procedura: Determinare la stringa associata a un valore di enumerazione (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic]
- strings [Visual Basic], enumeration values
- values [Visual Basic], enumeration members
ms.assetid: 9253e7c8-579c-49a2-8f26-392b20ea99eb
ms.openlocfilehash: 25c55c14507c67b9bdd8606cb85afd55f9a748fa
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64610538"
---
# <a name="how-to-determine-the-string-associated-with-an-enumeration-value-visual-basic"></a><span data-ttu-id="4ae8d-102">Procedura: Determinare la stringa associata a un valore di enumerazione (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4ae8d-102">How to: Determine the String Associated with an Enumeration Value (Visual Basic)</span></span>
<span data-ttu-id="4ae8d-103">Il <xref:System.Enum.GetValues%2A> e <xref:System.Enum.GetNames%2A> metodi consentono di determinare le stringhe e valori associati ai membri di enumerazione.</span><span class="sxs-lookup"><span data-stu-id="4ae8d-103">The <xref:System.Enum.GetValues%2A> and <xref:System.Enum.GetNames%2A> methods allow you to determine the strings and values associated with enumeration members.</span></span>  
  
### <a name="to-determine-the-string-associated-with-an-enumeration"></a><span data-ttu-id="4ae8d-104">Per determinare la stringa associata a un'enumerazione</span><span class="sxs-lookup"><span data-stu-id="4ae8d-104">To determine the string associated with an enumeration</span></span>  
  
- <span data-ttu-id="4ae8d-105">Usare il <xref:System.Enum.GetNames%2A> metodo per recuperare le stringhe associate ai membri di enumerazione.</span><span class="sxs-lookup"><span data-stu-id="4ae8d-105">Use the <xref:System.Enum.GetNames%2A> method to retrieve the strings associated with the enumeration members.</span></span> <span data-ttu-id="4ae8d-106">In questo esempio dichiara un'enumerazione `flavorEnum`, quindi Usa il <xref:System.Enum.GetNames%2A> metodo per visualizzare le stringhe associate a ogni membro.</span><span class="sxs-lookup"><span data-stu-id="4ae8d-106">This example declares an enumeration, `flavorEnum`, then uses the <xref:System.Enum.GetNames%2A> method to display the strings associated with each member.</span></span>  
  
     [!code-vb[VbEnumsTask#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="4ae8d-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4ae8d-107">See also</span></span>

- <xref:System.Enum.GetValues%2A>
- <xref:System.Enum.GetNames%2A>
- <xref:System.Enum>
- [<span data-ttu-id="4ae8d-108">Procedura: Dichiarare un'enumerazione</span><span class="sxs-lookup"><span data-stu-id="4ae8d-108">How to: Declare an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)
- [<span data-ttu-id="4ae8d-109">Procedura: Fare riferimento a un membro di enumerazione</span><span class="sxs-lookup"><span data-stu-id="4ae8d-109">How to: Refer to an Enumeration Member</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)
- [<span data-ttu-id="4ae8d-110">Qualifica di nomi ed enumerazioni</span><span class="sxs-lookup"><span data-stu-id="4ae8d-110">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [<span data-ttu-id="4ae8d-111">Procedura: Scorrere un'enumerazione in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4ae8d-111">How to: Iterate Through An Enumeration in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)
- [<span data-ttu-id="4ae8d-112">Quando usare un'enumerazione</span><span class="sxs-lookup"><span data-stu-id="4ae8d-112">When to Use an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)
- [<span data-ttu-id="4ae8d-113">Istruzione Enum</span><span class="sxs-lookup"><span data-stu-id="4ae8d-113">Enum Statement</span></span>](../../../../visual-basic/language-reference/statements/enum-statement.md)
