---
title: I parametri facoltativi devono specificare un valore predefinito
ms.date: 07/20/2015
f1_keywords:
- vbc30812
- bc30812
helpviewer_keywords:
- BC30812
ms.assetid: 5091a250-be66-413b-98a3-2a9974c4d600
ms.openlocfilehash: dbbcc748a65942e3a89785b267e9231f4a4a01a8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54686179"
---
# <a name="optional-parameters-must-specify-a-default-value"></a>I parametri facoltativi devono specificare un valore predefinito
I parametri facoltativi devono fornire valori predefiniti che possono essere utilizzati se nessun parametro viene fornito da una routine chiamante.  
  
 **ID errore:** BC30812  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Specificare i valori predefiniti per i parametri facoltativi; Per esempio:  
  
    ```  
    Sub Proc1(ByVal X As Integer,   
          Optional ByVal Y As String = "Default Value")  
       MsgBox("Default argument is: " & Y)  
    End Sub  
    ```  
  
## <a name="see-also"></a>Vedere anche
- [Optional](../../../visual-basic/language-reference/modifiers/optional.md)
