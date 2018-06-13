---
title: 'Procedura: impostare il formato per il controllo NumericUpDown Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- NumericUpDown control [Windows Forms], formatting values
- up-down controls [Windows Forms], formatting numeric values
ms.assetid: fa7c5557-6bfb-45b2-975d-8887b23b0ba0
ms.openlocfilehash: 1cb8f8b7d2f86125736c08cd9eadf4eee30063bb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33533959"
---
# <a name="how-to-set-the-format-for-the-windows-forms-numericupdown-control"></a>Procedura: impostare il formato per il controllo NumericUpDown Windows Form
È possibile configurare la modalità di visualizzazione dei valori in Windows Form <xref:System.Windows.Forms.NumericUpDown> controllo. Il <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> proprietà determina il numero di cifre visualizzate dopo il separatore decimale; il valore predefinito è 0. Il <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> proprietà determina se inserire un separatore tra ogni tre cifre decimali, il valore predefinito è `false`. Se il controllo può visualizzare i valori in formato decimale, esadecimale anziché il <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> è impostata su `true`; il valore predefinito è `false`.  
  
### <a name="to-format-the-numeric-value"></a>Per formattare il valore numerico  
  
-   Visualizzare un valore decimale impostando il <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> proprietà su un valore integer e l'impostazione di <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> proprietà `true` o `false`.  
  
    ```vb  
    NumericUpDown1.DecimalPlaces = 2  
    NumericUpDown1.ThousandsSeparator = True  
    ```  
  
    ```csharp  
    numericUpDown1.DecimalPlaces = 2;  
    numericUpDown1.ThousandsSeparator = true;  
    ```  
  
    ```cpp  
    numericUpDown1->DecimalPlaces = 2;  
    numericUpDown1->ThousandsSeparator = true;  
    ```  
  
     oppure  
  
-   Visualizzare un valore esadecimale impostando il <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> proprietà `true`.  
  
    ```vb  
    NumericUpDown1.Hexadecimal = True  
    ```  
  
    ```csharp  
    numericUpDown1.Hexadecimal = true;  
    ```  
  
    ```cpp  
    numericUpDown1->Hexadecimal = true;  
    ```  
  
    > [!NOTE]
    >  Anche se il valore viene visualizzato nel form come esadecimale, qualsiasi test eseguito sul <xref:System.Windows.Forms.NumericUpDown.Value%2A> proprietà verrà sottoposta a test il valore decimale.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.NumericUpDown>  
 [Controllo NumericUpDown](../../../../docs/framework/winforms/controls/numericupdown-control-windows-forms.md)  
 [Cenni preliminari sul controllo NumericUpDown](../../../../docs/framework/winforms/controls/numericupdown-control-overview-windows-forms.md)
