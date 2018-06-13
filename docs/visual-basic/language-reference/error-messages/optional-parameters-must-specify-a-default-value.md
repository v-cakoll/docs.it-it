---
title: I parametri facoltativi devono specificare un valore predefinito
ms.date: 07/20/2015
f1_keywords:
- vbc30812
- bc30812
helpviewer_keywords:
- BC30812
ms.assetid: 5091a250-be66-413b-98a3-2a9974c4d600
ms.openlocfilehash: 6788a7908489591e266af6d141006f2aa2d0e6f1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33593916"
---
# <a name="optional-parameters-must-specify-a-default-value"></a><span data-ttu-id="a21d0-102">I parametri facoltativi devono specificare un valore predefinito</span><span class="sxs-lookup"><span data-stu-id="a21d0-102">Optional parameters must specify a default value</span></span>
<span data-ttu-id="a21d0-103">Parametri facoltativi devono fornire valori predefiniti che possono essere utilizzati se viene fornito alcun parametro per una routine chiamante.</span><span class="sxs-lookup"><span data-stu-id="a21d0-103">Optional parameters must provide default values that can be used if no parameter is supplied by a calling procedure.</span></span>  
  
 <span data-ttu-id="a21d0-104">**ID errore:** BC30812</span><span class="sxs-lookup"><span data-stu-id="a21d0-104">**Error ID:** BC30812</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a21d0-105">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="a21d0-105">To correct this error</span></span>  
  
-   <span data-ttu-id="a21d0-106">Specificare i valori predefiniti per i parametri facoltativi. Per esempio:</span><span class="sxs-lookup"><span data-stu-id="a21d0-106">Specify default values for optional parameters; for example:</span></span>  
  
    ```  
    Sub Proc1(ByVal X As Integer,   
          Optional ByVal Y As String = "Default Value")  
       MsgBox("Default argument is: " & Y)  
    End Sub  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="a21d0-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a21d0-107">See Also</span></span>  
 [<span data-ttu-id="a21d0-108">Optional</span><span class="sxs-lookup"><span data-stu-id="a21d0-108">Optional</span></span>](../../../visual-basic/language-reference/modifiers/optional.md)
