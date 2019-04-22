---
title: I parametri facoltativi devono specificare un valore predefinito
ms.date: 07/20/2015
f1_keywords:
- vbc30812
- bc30812
helpviewer_keywords:
- BC30812
ms.assetid: 5091a250-be66-413b-98a3-2a9974c4d600
ms.openlocfilehash: 01c0abb366e8605a9b153333e645fc3276b6bd16
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58821725"
---
# <a name="optional-parameters-must-specify-a-default-value"></a><span data-ttu-id="f3910-102">I parametri facoltativi devono specificare un valore predefinito</span><span class="sxs-lookup"><span data-stu-id="f3910-102">Optional parameters must specify a default value</span></span>
<span data-ttu-id="f3910-103">I parametri facoltativi devono fornire valori predefiniti che possono essere utilizzati se nessun parametro viene fornito da una routine chiamante.</span><span class="sxs-lookup"><span data-stu-id="f3910-103">Optional parameters must provide default values that can be used if no parameter is supplied by a calling procedure.</span></span>  
  
 <span data-ttu-id="f3910-104">**ID errore:** BC30812</span><span class="sxs-lookup"><span data-stu-id="f3910-104">**Error ID:** BC30812</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f3910-105">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="f3910-105">To correct this error</span></span>  
  
-   <span data-ttu-id="f3910-106">Specificare i valori predefiniti per i parametri facoltativi; Per esempio:</span><span class="sxs-lookup"><span data-stu-id="f3910-106">Specify default values for optional parameters; for example:</span></span>  
  
    ```  
    Sub Proc1(ByVal X As Integer,   
          Optional ByVal Y As String = "Default Value")  
       MsgBox("Default argument is: " & Y)  
    End Sub  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="f3910-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f3910-107">See also</span></span>

- [<span data-ttu-id="f3910-108">Optional</span><span class="sxs-lookup"><span data-stu-id="f3910-108">Optional</span></span>](../../../visual-basic/language-reference/modifiers/optional.md)
