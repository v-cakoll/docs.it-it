---
title: 'Procedura: impostare e restituire valori numerici con il controllo NumericUpDown Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- numeric values [Windows Forms], Windows Forms
- Windows Forms, numeric values
- Windows Forms controls, NumericUpDown
- NumericUpDown control [Windows Forms], setting and returning values
ms.assetid: 5bd8f8cd-4c12-49ea-9cc3-2a647d064689
ms.openlocfilehash: e214f556224577c3029b2b742784e58932d792f3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33535561"
---
# <a name="how-to-set-and-return-numeric-values-with-the-windows-forms-numericupdown-control"></a>Procedura: impostare e restituire valori numerici con il controllo NumericUpDown Windows Form
Il valore numerico di Windows Form <xref:System.Windows.Forms.NumericUpDown> controllo è determinato dal relativo <xref:System.Windows.Forms.NumericUpDown.Value%2A> proprietà. Come con qualsiasi altra proprietà, è possibile scrivere un test condizionale per il valore del controllo. Una volta il <xref:System.Windows.Forms.NumericUpDown.Value%2A> proprietà è impostata, è possibile modificare direttamente scrivendo il codice per eseguire operazioni su di esso oppure è possibile chiamare il <xref:System.Windows.Forms.NumericUpDown.UpButton%2A> e <xref:System.Windows.Forms.NumericUpDown.DownButton%2A> metodi.  
  
### <a name="to-set-the-numeric-value"></a>Per impostare il valore numerico  
  
1.  Assegnare un valore per il <xref:System.Windows.Forms.NumericUpDown.Value%2A> proprietà nel codice o nella finestra Proprietà.  
  
    ```vb  
    NumericUpDown1.Value = 55  
    ```  
  
    ```csharp  
    numericUpDown1.Value = 55;  
    ```  
  
    ```cpp  
    numericUpDown1->Value = 55;  
    ```  
  
     oppure  
  
2.  Chiamare il <xref:System.Windows.Forms.NumericUpDown.UpButton%2A> o <xref:System.Windows.Forms.NumericUpDown.DownButton%2A> metodo per aumentare o diminuire il valore di quello specificato nel <xref:System.Windows.Forms.NumericUpDown.Increment%2A> proprietà.  
  
    ```vb  
    NumericUpDown1.UpButton()  
    ```  
  
    ```csharp  
    numericUpDown1.UpButton();  
    ```  
  
    ```cpp  
    numericUpDown1->UpButton();  
    ```  
  
### <a name="to-return-the-numeric-value"></a>Per restituire il valore numerico  
  
-   Accesso di <xref:System.Windows.Forms.NumericUpDown.Value%2A> proprietà nel codice.  
  
    ```vb  
    If NumericUpDown1.Value >= 65 Then  
       MessageBox.Show("Age is: " & NumericUpDown1.Value.ToString)  
    Else  
       MessageBox.Show("The customer is ineligible for a senior citizen discount.")  
    End If  
    ```  
  
    ```csharp  
    if(numericUpDown1.Value >= 65)  
    {  
       MessageBox.Show("Age is: " + numericUpDown1.Value.ToString());  
    }  
    else  
    {  
       MessageBox.Show("The customer is ineligible for a senior citizen discount.");  
    }  
    ```  
  
    ```cpp  
    if(numericUpDown1->Value >= 65)  
    {  
       MessageBox::Show(String::Concat("Age is: ",  
          numericUpDown1->Value.ToString()));  
    }  
    else  
    {  
       MessageBox::Show  
          ("The customer is ineligible for a senior citizen discount.");  
    }  
    ```  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.NumericUpDown>  
 <xref:System.Windows.Forms.NumericUpDown.Value%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.NumericUpDown.Increment%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.NumericUpDown.UpButton%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.NumericUpDown.DownButton%2A?displayProperty=nameWithType>  
 [Controllo NumericUpDown](../../../../docs/framework/winforms/controls/numericupdown-control-windows-forms.md)  
 [Cenni preliminari sul controllo NumericUpDown](../../../../docs/framework/winforms/controls/numericupdown-control-overview-windows-forms.md)
