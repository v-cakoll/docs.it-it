---
title: Impossibile utilizzare i parametri di tipo come qualificatori
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc32098
- bc32098
helpviewer_keywords:
- BC32098
ms.assetid: bab05325-dde8-4621-a5f6-368b5b7b2d76
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 58be51e0c05750ee044f0287cde8db037718b4aa
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="type-parameters-cannot-be-used-as-qualifiers"></a><span data-ttu-id="73b2f-102">Impossibile utilizzare i parametri di tipo come qualificatori</span><span class="sxs-lookup"><span data-stu-id="73b2f-102">Type parameters cannot be used as qualifiers</span></span>
<span data-ttu-id="73b2f-103">Un elemento di programmazione è qualificato con la stringa di qualificazione che include un parametro di tipo.</span><span class="sxs-lookup"><span data-stu-id="73b2f-103">A programming element is qualified with a qualification string that includes a type parameter.</span></span>  
  
 <span data-ttu-id="73b2f-104">Un parametro di tipo rappresenta un requisito per un tipo che deve essere fornito quando il tipo generico viene costruito.</span><span class="sxs-lookup"><span data-stu-id="73b2f-104">A type parameter represents a requirement for a type that is to be supplied when the generic type is constructed.</span></span> <span data-ttu-id="73b2f-105">Non rappresenta un tipo specifico definito.</span><span class="sxs-lookup"><span data-stu-id="73b2f-105">It does not represent a specific defined type.</span></span> <span data-ttu-id="73b2f-106">La stringa di qualificazione deve includere solo gli elementi definiti in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="73b2f-106">A qualification string must include only elements that are defined at compile time.</span></span>  
  
 <span data-ttu-id="73b2f-107">Le istruzioni seguenti possono generare questo errore.</span><span class="sxs-lookup"><span data-stu-id="73b2f-107">The following statements can generate this error.</span></span>  
  
```  
Public Function checkText(Of c As System.Windows.Forms.Control)(  
    ByVal badText As String) As Boolean  
  
    Dim saveText As c.Text  
    ' Insert code to look for badText within saveText.  
End Function  
```  
  
 <span data-ttu-id="73b2f-108">**ID errore:** BC32098</span><span class="sxs-lookup"><span data-stu-id="73b2f-108">**Error ID:** BC32098</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="73b2f-109">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="73b2f-109">To correct this error</span></span>  
  
1.  <span data-ttu-id="73b2f-110">Rimuovere il parametro di tipo stringa di qualificazione o sostituirlo con un tipo definito.</span><span class="sxs-lookup"><span data-stu-id="73b2f-110">Remove the type parameter from the qualification string, or replace it with a defined type.</span></span>  
  
2.  <span data-ttu-id="73b2f-111">Se è necessario utilizzare un tipo costruito per individuare l'elemento di programmazione qualificato, è necessario utilizzare la logica di programma aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="73b2f-111">If you need to use a constructed type to locate the programming element being qualified, you must use additional program logic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73b2f-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="73b2f-112">See Also</span></span>  
 [<span data-ttu-id="73b2f-113">Riferimenti a elementi dichiarati</span><span class="sxs-lookup"><span data-stu-id="73b2f-113">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
 [<span data-ttu-id="73b2f-114">Tipi generici in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="73b2f-114">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [<span data-ttu-id="73b2f-115">Elenco dei tipi</span><span class="sxs-lookup"><span data-stu-id="73b2f-115">Type List</span></span>](../../../visual-basic/language-reference/statements/type-list.md)
