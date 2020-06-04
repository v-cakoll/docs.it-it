---
title: 'Procedura: determinare la stringa associata a un valore di enumerazione'
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic]
- strings [Visual Basic], enumeration values
- values [Visual Basic], enumeration members
ms.assetid: 9253e7c8-579c-49a2-8f26-392b20ea99eb
ms.openlocfilehash: 525da9206472afefa9f85b49ceee0775cbd168c3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84414466"
---
# <a name="how-to-determine-the-string-associated-with-an-enumeration-value-visual-basic"></a><span data-ttu-id="32ab2-102">Procedura: determinare la stringa associata a un valore di enumerazione (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="32ab2-102">How to: Determine the String Associated with an Enumeration Value (Visual Basic)</span></span>
<span data-ttu-id="32ab2-103">I <xref:System.Enum.GetValues%2A> <xref:System.Enum.GetNames%2A> metodi e consentono di determinare le stringhe e i valori associati ai membri dell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="32ab2-103">The <xref:System.Enum.GetValues%2A> and <xref:System.Enum.GetNames%2A> methods allow you to determine the strings and values associated with enumeration members.</span></span>  
  
### <a name="to-determine-the-string-associated-with-an-enumeration"></a><span data-ttu-id="32ab2-104">Per determinare la stringa associata a un'enumerazione</span><span class="sxs-lookup"><span data-stu-id="32ab2-104">To determine the string associated with an enumeration</span></span>  
  
- <span data-ttu-id="32ab2-105">Usare il <xref:System.Enum.GetNames%2A> metodo per recuperare le stringhe associate ai membri dell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="32ab2-105">Use the <xref:System.Enum.GetNames%2A> method to retrieve the strings associated with the enumeration members.</span></span> <span data-ttu-id="32ab2-106">Questo esempio dichiara un'enumerazione, `flavorEnum` , quindi usa il <xref:System.Enum.GetNames%2A> metodo per visualizzare le stringhe associate a ogni membro.</span><span class="sxs-lookup"><span data-stu-id="32ab2-106">This example declares an enumeration, `flavorEnum`, then uses the <xref:System.Enum.GetNames%2A> method to display the strings associated with each member.</span></span>  
  
     [!code-vb[VbEnumsTask#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="32ab2-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="32ab2-107">See also</span></span>

- <xref:System.Enum.GetValues%2A>
- <xref:System.Enum.GetNames%2A>
- <xref:System.Enum>
- [<span data-ttu-id="32ab2-108">Procedura: dichiarare un'enumerazione</span><span class="sxs-lookup"><span data-stu-id="32ab2-108">How to: Declare an Enumeration</span></span>](how-to-declare-enumerations.md)
- [<span data-ttu-id="32ab2-109">Procedura: fare riferimento a un membro di enumerazione</span><span class="sxs-lookup"><span data-stu-id="32ab2-109">How to: Refer to an Enumeration Member</span></span>](how-to-refer-to-an-enumeration-member.md)
- [<span data-ttu-id="32ab2-110">Qualifica di nomi ed enumerazioni</span><span class="sxs-lookup"><span data-stu-id="32ab2-110">Enumerations and Name Qualification</span></span>](enumerations-and-name-qualification.md)
- [<span data-ttu-id="32ab2-111">Procedura: scorrere un'enumerazione in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="32ab2-111">How to: Iterate Through An Enumeration in Visual Basic</span></span>](how-to-iterate-through-an-enumeration.md)
- [<span data-ttu-id="32ab2-112">Quando utilizzare un'enumerazione</span><span class="sxs-lookup"><span data-stu-id="32ab2-112">When to Use an Enumeration</span></span>](when-to-use-an-enumeration.md)
- [<span data-ttu-id="32ab2-113">Istruzione Enum</span><span class="sxs-lookup"><span data-stu-id="32ab2-113">Enum Statement</span></span>](../../../language-reference/statements/enum-statement.md)
