---
title: I parametri facoltativi devono specificare un valore predefinito
ms.date: 07/20/2015
f1_keywords:
- vbc30812
- bc30812
helpviewer_keywords:
- BC30812
ms.assetid: 5091a250-be66-413b-98a3-2a9974c4d600
ms.openlocfilehash: b32c150f0faf4a9dcec3cec7620c3a9c050f6f20
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71696880"
---
# <a name="optional-parameters-must-specify-a-default-value"></a>I parametri facoltativi devono specificare un valore predefinito
I parametri facoltativi devono fornire valori predefiniti che possono essere usati se non viene fornito alcun parametro da una routine chiamante.  
  
 **ID errore:** BC30812  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Specificare i valori predefiniti per i parametri facoltativi. Per esempio:  
  
    ```vb  
    Sub Proc1(ByVal X As Integer,   
          Optional ByVal Y As String = "Default Value")  
       MsgBox("Default argument is: " & Y)  
    End Sub  
    ```  
  
## <a name="see-also"></a>Vedere anche

- [Facoltativo](../../../visual-basic/language-reference/modifiers/optional.md)
