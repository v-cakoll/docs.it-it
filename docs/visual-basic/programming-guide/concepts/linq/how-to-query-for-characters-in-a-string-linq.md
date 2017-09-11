---
title: 'Procedura: eseguire una Query per i caratteri in una stringa (LINQ) (Visual Basic) | Documenti di Microsoft'
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
ms.assetid: 499ebbe0-746c-4235-9dba-ce722c12b50e
caps.latest.revision: 4
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: dabd63e52707f3078c6cdc41db8c4f0e7dfbf70e
ms.contentlocale: it-it
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-query-for-characters-in-a-string-linq-visual-basic"></a><span data-ttu-id="d27a8-102">Procedura: eseguire una Query per i caratteri in una stringa (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d27a8-102">How to: Query for Characters in a String (LINQ) (Visual Basic)</span></span>
<span data-ttu-id="d27a8-103">Poiché la <xref:System.String>classe implementa l'interfaccia generica <xref:System.Collections.Generic.IEnumerable%601>interfaccia, è possibile eseguire query di qualsiasi stringa come una sequenza di caratteri.</xref:System.Collections.Generic.IEnumerable%601> </xref:System.String></span><span class="sxs-lookup"><span data-stu-id="d27a8-103">Because the <xref:System.String> class implements the generic <xref:System.Collections.Generic.IEnumerable%601> interface, any string can be queried as a sequence of characters.</span></span> <span data-ttu-id="d27a8-104">Tuttavia, questo non è un utilizzo comune di LINQ.</span><span class="sxs-lookup"><span data-stu-id="d27a8-104">However, this is not a common use of LINQ.</span></span> <span data-ttu-id="d27a8-105">Per le operazioni di criteri di ricerca complessa, utilizzare la <xref:System.Text.RegularExpressions.Regex>classe.</xref:System.Text.RegularExpressions.Regex></span><span class="sxs-lookup"><span data-stu-id="d27a8-105">For complex pattern matching operations, use the <xref:System.Text.RegularExpressions.Regex> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d27a8-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="d27a8-106">Example</span></span>  
 <span data-ttu-id="d27a8-107">Nell'esempio seguente esegue una query per determinare il numero di cifre che contiene una stringa.</span><span class="sxs-lookup"><span data-stu-id="d27a8-107">The following example queries a string to determine the number of numeric digits it contains.</span></span> <span data-ttu-id="d27a8-108">Si noti che la query è "riutilizzare" dopo che viene eseguita la prima volta.</span><span class="sxs-lookup"><span data-stu-id="d27a8-108">Note that the query is "reused" after it is executed the first time.</span></span> <span data-ttu-id="d27a8-109">Ciò è possibile perché la query stessa non è possibile archiviare i risultati effettivi.</span><span class="sxs-lookup"><span data-stu-id="d27a8-109">This is possible because the query itself does not store any actual results.</span></span>  
  
<span data-ttu-id="d27a8-110"><CodeContentPlaceHolder>0</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="d27a8-110"><CodeContentPlaceHolder>0</CodeContentPlaceHolder></span></span>  
## <a name="compiling-the-code"></a><span data-ttu-id="d27a8-111">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="d27a8-111">Compiling the Code</span></span>  
 <span data-ttu-id="d27a8-112">Creare un progetto destinato a .NET Framework versione 3.5 o versione successiva con un riferimento a System.Core.dll e una `Imports` istruzione per lo spazio dei nomi System. Linq.</span><span class="sxs-lookup"><span data-stu-id="d27a8-112">Create a project that targets the .NET Framework version 3.5 or higher with a reference to System.Core.dll and a `Imports` statement for the System.Linq namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d27a8-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d27a8-113">See Also</span></span>  
 <span data-ttu-id="d27a8-114">[LINQ e stringhe (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md) </span><span class="sxs-lookup"><span data-stu-id="d27a8-114">[LINQ and Strings (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md) </span></span>  
<span data-ttu-id="d27a8-115"> [Procedura: combinare query LINQ con espressioni regolari (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-combine-linq-queries-with-regular-expressions.md)</span><span class="sxs-lookup"><span data-stu-id="d27a8-115"> [How to: Combine LINQ Queries with Regular Expressions (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-combine-linq-queries-with-regular-expressions.md)</span></span>
