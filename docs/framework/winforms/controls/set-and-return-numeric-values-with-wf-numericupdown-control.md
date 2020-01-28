---
title: Impostare e restituire valori numerici con il controllo NumericUpDown
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
ms.openlocfilehash: a0b264fec9619b467c293bcb96278c4517775ac3
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743029"
---
# <a name="how-to-set-and-return-numeric-values-with-the-windows-forms-numericupdown-control"></a>Procedura: impostare e restituire valori numerici con il controllo NumericUpDown Windows Form
Il valore numerico della Windows Forms <xref:System.Windows.Forms.NumericUpDown> controllo è determinato dalla relativa proprietà <xref:System.Windows.Forms.NumericUpDown.Value%2A>. È possibile scrivere test condizionali per il valore del controllo esattamente come per qualsiasi altra proprietà. Una volta impostata la proprietà <xref:System.Windows.Forms.NumericUpDown.Value%2A>, è possibile modificarla direttamente scrivendo codice per eseguire operazioni su di esso oppure è possibile chiamare i metodi <xref:System.Windows.Forms.NumericUpDown.UpButton%2A> e <xref:System.Windows.Forms.NumericUpDown.DownButton%2A>.  
  
### <a name="to-set-the-numeric-value"></a>Per impostare il valore numerico  
  
1. Assegnare un valore alla proprietà <xref:System.Windows.Forms.NumericUpDown.Value%2A> nel codice o nel Finestra Proprietà.  
  
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
  
2. Chiamare il metodo <xref:System.Windows.Forms.NumericUpDown.UpButton%2A> o <xref:System.Windows.Forms.NumericUpDown.DownButton%2A> per aumentare o diminuire il valore in base alla quantità specificata nella proprietà <xref:System.Windows.Forms.NumericUpDown.Increment%2A>.  
  
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
  
- Accedere alla proprietà <xref:System.Windows.Forms.NumericUpDown.Value%2A> nel codice.  
  
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
