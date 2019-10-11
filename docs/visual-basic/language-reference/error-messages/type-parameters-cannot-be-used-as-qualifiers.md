---
title: Impossibile utilizzare i parametri di tipo come qualificatori
ms.date: 07/20/2015
f1_keywords:
- vbc32098
- bc32098
helpviewer_keywords:
- BC32098
ms.assetid: bab05325-dde8-4621-a5f6-368b5b7b2d76
ms.openlocfilehash: 3ff4b189539bf119351a94dabadd596c336ac723
ms.sourcegitcommit: d7c298f6c2e3aab0c7498bfafc0a0a94ea1fe23e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/10/2019
ms.locfileid: "72250335"
---
# <a name="type-parameters-cannot-be-used-as-qualifiers"></a><span data-ttu-id="89342-102">Impossibile utilizzare i parametri di tipo come qualificatori</span><span class="sxs-lookup"><span data-stu-id="89342-102">Type parameters cannot be used as qualifiers</span></span>

<span data-ttu-id="89342-103">Un elemento di programmazione è qualificato con una stringa di qualificazione che include un parametro di tipo.</span><span class="sxs-lookup"><span data-stu-id="89342-103">A programming element is qualified with a qualification string that includes a type parameter.</span></span>

<span data-ttu-id="89342-104">Un parametro di tipo rappresenta un requisito per un tipo che deve essere specificato quando viene costruito il tipo generico.</span><span class="sxs-lookup"><span data-stu-id="89342-104">A type parameter represents a requirement for a type that is to be supplied when the generic type is constructed.</span></span> <span data-ttu-id="89342-105">Non rappresenta un tipo definito specifico.</span><span class="sxs-lookup"><span data-stu-id="89342-105">It does not represent a specific defined type.</span></span> <span data-ttu-id="89342-106">Una stringa di qualificazione deve includere solo elementi definiti in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="89342-106">A qualification string must include only elements that are defined at compile time.</span></span>

<span data-ttu-id="89342-107">Il codice seguente può generare questo errore:</span><span class="sxs-lookup"><span data-stu-id="89342-107">The following code can generate this error:</span></span>

```vb  
Public Function CheckText(Of c As System.Windows.Forms.Control)(
    badText As String) As Boolean
  
    Dim saveText As c.Text  
    ' Insert code to look for badText within saveText.
End Function  
```  
  
 <span data-ttu-id="89342-108">**ID errore:** BC32098</span><span class="sxs-lookup"><span data-stu-id="89342-108">**Error ID:** BC32098</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="89342-109">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="89342-109">To correct this error</span></span>  
  
1. <span data-ttu-id="89342-110">Rimuovere il parametro di tipo dalla stringa di qualificazione o sostituirlo con un tipo definito.</span><span class="sxs-lookup"><span data-stu-id="89342-110">Remove the type parameter from the qualification string, or replace it with a defined type.</span></span>  
  
2. <span data-ttu-id="89342-111">Se è necessario usare un tipo costruito per individuare l'elemento di programmazione qualificato, è necessario usare la logica di programma aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="89342-111">If you need to use a constructed type to locate the programming element being qualified, you must use additional program logic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89342-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="89342-112">See also</span></span>

- [<span data-ttu-id="89342-113">Riferimenti a elementi dichiarati</span><span class="sxs-lookup"><span data-stu-id="89342-113">References to Declared Elements</span></span>](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [<span data-ttu-id="89342-114">Generic Types in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="89342-114">Generic Types in Visual Basic</span></span>](../../programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="89342-115">Elenco dei tipi</span><span class="sxs-lookup"><span data-stu-id="89342-115">Type List</span></span>](../statements/type-list.md)
