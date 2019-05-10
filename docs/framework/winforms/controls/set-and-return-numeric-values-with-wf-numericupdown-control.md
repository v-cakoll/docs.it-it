---
title: 'Procedura: Impostare e restituire valori numerici con il controllo NumericUpDown di Windows Forms'
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
ms.openlocfilehash: 3da2c7b057732e9b2db5e048dec037e4e9910c0a
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64625743"
---
# <a name="how-to-set-and-return-numeric-values-with-the-windows-forms-numericupdown-control"></a>Procedura: Impostare e restituire valori numerici con il controllo NumericUpDown di Windows Forms
Il valore numerico di moduli di Windows <xref:System.Windows.Forms.NumericUpDown> controllo è determinato dal relativo <xref:System.Windows.Forms.NumericUpDown.Value%2A> proprietà. È possibile scrivere test condizionali per il valore del controllo come avviene con qualsiasi altra proprietà. Una volta il <xref:System.Windows.Forms.NumericUpDown.Value%2A> è impostata, è possibile modificarlo direttamente scrivendo codice per eseguire operazioni su di esso o è possibile chiamare il <xref:System.Windows.Forms.NumericUpDown.UpButton%2A> e <xref:System.Windows.Forms.NumericUpDown.DownButton%2A> metodi.  
  
### <a name="to-set-the-numeric-value"></a>Per impostare il valore numerico  
  
1. Assegnare un valore per il <xref:System.Windows.Forms.NumericUpDown.Value%2A> proprietà nel codice o nella finestra Proprietà.  
  
    ```vb  
    NumericUpDown1.Value = 55  
    ```  
  
    ```csharp  
    numericUpDown1.Value = 55;  
    ```  
  
    ```cpp  
    numericUpDown1->Value = 55;  
    ```  
  
     -oppure-  
  
2. Chiamare il <xref:System.Windows.Forms.NumericUpDown.UpButton%2A> oppure <xref:System.Windows.Forms.NumericUpDown.DownButton%2A> metodo per aumentare o diminuire il valore di base al valore specificato nel <xref:System.Windows.Forms.NumericUpDown.Increment%2A> proprietà.  
  
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
  
- Accesso di <xref:System.Windows.Forms.NumericUpDown.Value%2A> proprietà nel codice.  
  
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

- <xref:System.Windows.Forms.NumericUpDown>
- <xref:System.Windows.Forms.NumericUpDown.Value%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.NumericUpDown.Increment%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.NumericUpDown.UpButton%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.NumericUpDown.DownButton%2A?displayProperty=nameWithType>
- [Controllo NumericUpDown](numericupdown-control-windows-forms.md)
- [Cenni preliminari sul controllo NumericUpDown](numericupdown-control-overview-windows-forms.md)
