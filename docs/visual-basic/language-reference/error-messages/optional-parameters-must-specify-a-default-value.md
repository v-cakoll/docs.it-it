---
title: I parametri facoltativi devono specificare un valore predefinito
ms.date: 07/20/2015
f1_keywords:
- vbc30812
- bc30812
helpviewer_keywords:
- BC30812
ms.assetid: 5091a250-be66-413b-98a3-2a9974c4d600
ms.openlocfilehash: eb782b2fa1fb73c7407b57a0942e5eebb30474ff
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040932"
---
# <a name="optional-parameters-must-specify-a-default-value"></a><span data-ttu-id="fd961-102">I parametri facoltativi devono specificare un valore predefinito</span><span class="sxs-lookup"><span data-stu-id="fd961-102">Optional parameters must specify a default value</span></span>

<span data-ttu-id="fd961-103">I parametri facoltativi devono fornire valori predefiniti che possono essere usati se non viene fornito alcun parametro da una routine chiamante.</span><span class="sxs-lookup"><span data-stu-id="fd961-103">Optional parameters must provide default values that can be used if no parameter is supplied by a calling procedure.</span></span>

<span data-ttu-id="fd961-104">**ID errore:** BC30812</span><span class="sxs-lookup"><span data-stu-id="fd961-104">**Error ID:** BC30812</span></span>

## <a name="example"></a><span data-ttu-id="fd961-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="fd961-105">Example</span></span>

<span data-ttu-id="fd961-106">L'esempio seguente genera l'BC30812:</span><span class="sxs-lookup"><span data-stu-id="fd961-106">The following example generates BC30812:</span></span>

```vb
Sub Proc1(x As Integer, Optional y As String)
    Console.WriteLine("Default argument is: " & y)
End Sub
```

## <a name="to-correct-this-error"></a><span data-ttu-id="fd961-107">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="fd961-107">To correct this error</span></span>

<span data-ttu-id="fd961-108">Specificare i valori predefiniti per i parametri facoltativi:</span><span class="sxs-lookup"><span data-stu-id="fd961-108">Specify default values for optional parameters:</span></span>

```vb
Sub Proc1(x As Integer, Optional y As String = "Default Value")
    Console.WriteLine("Default argument is: " & y)
End Sub
```

## <a name="see-also"></a><span data-ttu-id="fd961-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fd961-109">See also</span></span>

- [<span data-ttu-id="fd961-110">Optional</span><span class="sxs-lookup"><span data-stu-id="fd961-110">Optional</span></span>](../modifiers/optional.md)
