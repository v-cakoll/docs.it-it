---
title: Impossibile utilizzare i parametri di tipo come qualificatori
ms.date: 07/20/2015
f1_keywords:
- vbc32098
- bc32098
helpviewer_keywords:
- BC32098
ms.assetid: bab05325-dde8-4621-a5f6-368b5b7b2d76
ms.openlocfilehash: ba7348ae50965ffcf2719b20934451916c8fa95a
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59296355"
---
# <a name="type-parameters-cannot-be-used-as-qualifiers"></a><span data-ttu-id="657ad-102">Impossibile utilizzare i parametri di tipo come qualificatori</span><span class="sxs-lookup"><span data-stu-id="657ad-102">Type parameters cannot be used as qualifiers</span></span>
<span data-ttu-id="657ad-103">Un elemento di programmazione è qualificato con una stringa di qualificazione che includa un parametro di tipo.</span><span class="sxs-lookup"><span data-stu-id="657ad-103">A programming element is qualified with a qualification string that includes a type parameter.</span></span>  
  
 <span data-ttu-id="657ad-104">Un parametro di tipo rappresenta un requisito per un tipo che deve essere specificato quando viene costruito il tipo generico.</span><span class="sxs-lookup"><span data-stu-id="657ad-104">A type parameter represents a requirement for a type that is to be supplied when the generic type is constructed.</span></span> <span data-ttu-id="657ad-105">Non rappresenta un tipo specifico definito.</span><span class="sxs-lookup"><span data-stu-id="657ad-105">It does not represent a specific defined type.</span></span> <span data-ttu-id="657ad-106">La stringa di qualificazione deve includere solo gli elementi definiti in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="657ad-106">A qualification string must include only elements that are defined at compile time.</span></span>  
  
 <span data-ttu-id="657ad-107">Le istruzioni seguenti possono generare questo errore.</span><span class="sxs-lookup"><span data-stu-id="657ad-107">The following statements can generate this error.</span></span>  
  
```  
Public Function checkText(Of c As System.Windows.Forms.Control)(  
    ByVal badText As String) As Boolean  
  
    Dim saveText As c.Text  
    ' Insert code to look for badText within saveText.  
End Function  
```  
  
 <span data-ttu-id="657ad-108">**ID errore:** BC32098</span><span class="sxs-lookup"><span data-stu-id="657ad-108">**Error ID:** BC32098</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="657ad-109">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="657ad-109">To correct this error</span></span>  
  
1. <span data-ttu-id="657ad-110">Rimuovere il parametro di tipo dalla stringa di qualificazione o sostituirlo con un tipo definito.</span><span class="sxs-lookup"><span data-stu-id="657ad-110">Remove the type parameter from the qualification string, or replace it with a defined type.</span></span>  
  
2. <span data-ttu-id="657ad-111">Se è necessario utilizzare un tipo costruito per individuare l'elemento di programmazione completo in corso, è necessario usare la logica del programma aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="657ad-111">If you need to use a constructed type to locate the programming element being qualified, you must use additional program logic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="657ad-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="657ad-112">See also</span></span>

- [<span data-ttu-id="657ad-113">References to Declared Elements</span><span class="sxs-lookup"><span data-stu-id="657ad-113">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [<span data-ttu-id="657ad-114">Tipi generici in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="657ad-114">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="657ad-115">Type List</span><span class="sxs-lookup"><span data-stu-id="657ad-115">Type List</span></span>](../../../visual-basic/language-reference/statements/type-list.md)
