---
title: I parametri facoltativi devono specificare un valore predefinito
ms.date: 07/20/2015
f1_keywords:
- vbc30812
- bc30812
helpviewer_keywords:
- BC30812
ms.assetid: 5091a250-be66-413b-98a3-2a9974c4d600
ms.openlocfilehash: 8ec4627d070cc670ce04be3a5d0298dba0a279d0
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582141"
---
# <a name="optional-parameters-must-specify-a-default-value"></a><span data-ttu-id="48c7d-102">I parametri facoltativi devono specificare un valore predefinito</span><span class="sxs-lookup"><span data-stu-id="48c7d-102">Optional parameters must specify a default value</span></span>

<span data-ttu-id="48c7d-103">I parametri facoltativi devono fornire valori predefiniti che possono essere usati se non viene fornito alcun parametro da una routine chiamante.</span><span class="sxs-lookup"><span data-stu-id="48c7d-103">Optional parameters must provide default values that can be used if no parameter is supplied by a calling procedure.</span></span>

<span data-ttu-id="48c7d-104">**ID errore:** BC30812</span><span class="sxs-lookup"><span data-stu-id="48c7d-104">**Error ID:** BC30812</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="48c7d-105">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="48c7d-105">To correct this error</span></span>

<span data-ttu-id="48c7d-106">Specificare i valori predefiniti per i parametri facoltativi. Per esempio:</span><span class="sxs-lookup"><span data-stu-id="48c7d-106">Specify default values for optional parameters; for example:</span></span>

```vb
Sub Proc1(ByVal X As Integer,
      Optional ByVal Y As String = "Default Value")
    MsgBox("Default argument is: " & Y)
End Sub
```

## <a name="see-also"></a><span data-ttu-id="48c7d-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="48c7d-107">See also</span></span>

- [<span data-ttu-id="48c7d-108">Optional</span><span class="sxs-lookup"><span data-stu-id="48c7d-108">Optional</span></span>](../../../visual-basic/language-reference/modifiers/optional.md)
