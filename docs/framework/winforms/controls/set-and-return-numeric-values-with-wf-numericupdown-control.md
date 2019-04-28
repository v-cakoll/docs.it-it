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
ms.openlocfilehash: c73200eb1c373f1d723ba82f2e6be5b625496b59
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61902226"
---
# <a name="how-to-set-and-return-numeric-values-with-the-windows-forms-numericupdown-control"></a><span data-ttu-id="da3c8-102">Procedura: Impostare e restituire valori numerici con il controllo NumericUpDown di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="da3c8-102">How to: Set and Return Numeric Values with the Windows Forms NumericUpDown Control</span></span>
<span data-ttu-id="da3c8-103">Il valore numerico di moduli di Windows <xref:System.Windows.Forms.NumericUpDown> controllo è determinato dal relativo <xref:System.Windows.Forms.NumericUpDown.Value%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="da3c8-103">The numeric value of the Windows Forms <xref:System.Windows.Forms.NumericUpDown> control is determined by its <xref:System.Windows.Forms.NumericUpDown.Value%2A> property.</span></span> <span data-ttu-id="da3c8-104">È possibile scrivere test condizionali per il valore del controllo come avviene con qualsiasi altra proprietà.</span><span class="sxs-lookup"><span data-stu-id="da3c8-104">You can write conditional tests for the control's value just as with any other property.</span></span> <span data-ttu-id="da3c8-105">Una volta il <xref:System.Windows.Forms.NumericUpDown.Value%2A> è impostata, è possibile modificarlo direttamente scrivendo codice per eseguire operazioni su di esso o è possibile chiamare il <xref:System.Windows.Forms.NumericUpDown.UpButton%2A> e <xref:System.Windows.Forms.NumericUpDown.DownButton%2A> metodi.</span><span class="sxs-lookup"><span data-stu-id="da3c8-105">Once the <xref:System.Windows.Forms.NumericUpDown.Value%2A> property is set, you can adjust it directly by writing code to perform operations on it, or you can call the <xref:System.Windows.Forms.NumericUpDown.UpButton%2A> and <xref:System.Windows.Forms.NumericUpDown.DownButton%2A> methods.</span></span>  
  
### <a name="to-set-the-numeric-value"></a><span data-ttu-id="da3c8-106">Per impostare il valore numerico</span><span class="sxs-lookup"><span data-stu-id="da3c8-106">To set the numeric value</span></span>  
  
1. <span data-ttu-id="da3c8-107">Assegnare un valore per il <xref:System.Windows.Forms.NumericUpDown.Value%2A> proprietà nel codice o nella finestra Proprietà.</span><span class="sxs-lookup"><span data-stu-id="da3c8-107">Assign a value to the <xref:System.Windows.Forms.NumericUpDown.Value%2A> property in code or in the Properties window.</span></span>  
  
    ```vb  
    NumericUpDown1.Value = 55  
    ```  
  
    ```csharp  
    numericUpDown1.Value = 55;  
    ```  
  
    ```cpp  
    numericUpDown1->Value = 55;  
    ```  
  
     <span data-ttu-id="da3c8-108">-oppure-</span><span class="sxs-lookup"><span data-stu-id="da3c8-108">-or-</span></span>  
  
2. <span data-ttu-id="da3c8-109">Chiamare il <xref:System.Windows.Forms.NumericUpDown.UpButton%2A> oppure <xref:System.Windows.Forms.NumericUpDown.DownButton%2A> metodo per aumentare o diminuire il valore di base al valore specificato nel <xref:System.Windows.Forms.NumericUpDown.Increment%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="da3c8-109">Call the <xref:System.Windows.Forms.NumericUpDown.UpButton%2A> or <xref:System.Windows.Forms.NumericUpDown.DownButton%2A> method to increase or decrease the value by the amount specified in the <xref:System.Windows.Forms.NumericUpDown.Increment%2A> property.</span></span>  
  
    ```vb  
    NumericUpDown1.UpButton()  
    ```  
  
    ```csharp  
    numericUpDown1.UpButton();  
    ```  
  
    ```cpp  
    numericUpDown1->UpButton();  
    ```  
  
### <a name="to-return-the-numeric-value"></a><span data-ttu-id="da3c8-110">Per restituire il valore numerico</span><span class="sxs-lookup"><span data-stu-id="da3c8-110">To return the numeric value</span></span>  
  
- <span data-ttu-id="da3c8-111">Accesso di <xref:System.Windows.Forms.NumericUpDown.Value%2A> proprietà nel codice.</span><span class="sxs-lookup"><span data-stu-id="da3c8-111">Access the <xref:System.Windows.Forms.NumericUpDown.Value%2A> property in code.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="da3c8-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="da3c8-112">See also</span></span>

- <xref:System.Windows.Forms.NumericUpDown>
- <xref:System.Windows.Forms.NumericUpDown.Value%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.NumericUpDown.Increment%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.NumericUpDown.UpButton%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.NumericUpDown.DownButton%2A?displayProperty=nameWithType>
- [<span data-ttu-id="da3c8-113">Controllo NumericUpDown</span><span class="sxs-lookup"><span data-stu-id="da3c8-113">NumericUpDown Control</span></span>](numericupdown-control-windows-forms.md)
- [<span data-ttu-id="da3c8-114">Cenni preliminari sul controllo NumericUpDown</span><span class="sxs-lookup"><span data-stu-id="da3c8-114">NumericUpDown Control Overview</span></span>](numericupdown-control-overview-windows-forms.md)
