---
title: Imposta il formato per il controllo NumericUpDown
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- NumericUpDown control [Windows Forms], formatting values
- up-down controls [Windows Forms], formatting numeric values
ms.assetid: fa7c5557-6bfb-45b2-975d-8887b23b0ba0
ms.openlocfilehash: 5ef1c801e96bef7b92e7e69dc36491144c456eeb
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742182"
---
# <a name="how-to-set-the-format-for-the-windows-forms-numericupdown-control"></a><span data-ttu-id="aec19-102">Procedura: impostare il formato per il controllo NumericUpDown Windows Form</span><span class="sxs-lookup"><span data-stu-id="aec19-102">How to: Set the Format for the Windows Forms NumericUpDown Control</span></span>
<span data-ttu-id="aec19-103">È possibile configurare la modalità di visualizzazione dei valori nel controllo Windows Forms <xref:System.Windows.Forms.NumericUpDown>.</span><span class="sxs-lookup"><span data-stu-id="aec19-103">You can configure how values are displayed in the Windows Forms <xref:System.Windows.Forms.NumericUpDown> control.</span></span> <span data-ttu-id="aec19-104">La proprietà <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> determina il numero di numeri visualizzati dopo il separatore decimale. il valore predefinito è 0.</span><span class="sxs-lookup"><span data-stu-id="aec19-104">The <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> property determines how many numbers appear after the decimal point; the default is 0.</span></span> <span data-ttu-id="aec19-105">La proprietà <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> determina se verrà inserito un separatore tra tre cifre decimali. il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="aec19-105">The <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> property determines whether a separator will be inserted between every three decimal digits; the default is `false`.</span></span> <span data-ttu-id="aec19-106">Il controllo può visualizzare i valori in formato esadecimale anziché decimale, se la proprietà <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> è impostata su `true`; il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="aec19-106">The control can display values in hexadecimal instead of decimal format, if the <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> property is set to `true`; the default is `false`.</span></span>  
  
### <a name="to-format-the-numeric-value"></a><span data-ttu-id="aec19-107">Per formattare il valore numerico</span><span class="sxs-lookup"><span data-stu-id="aec19-107">To format the numeric value</span></span>  
  
- <span data-ttu-id="aec19-108">Visualizzare un valore decimale impostando la proprietà <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> su un valore integer e impostando la proprietà <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> su `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="aec19-108">Display a decimal value by setting the <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> property to an integer and setting the <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> property to `true` or `false`.</span></span>  
  
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
  
     <span data-ttu-id="aec19-109">oppure</span><span class="sxs-lookup"><span data-stu-id="aec19-109">-or-</span></span>  
  
- <span data-ttu-id="aec19-110">Consente di visualizzare un valore esadecimale impostando la proprietà <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> su `true`.</span><span class="sxs-lookup"><span data-stu-id="aec19-110">Display a hexadecimal value by setting the <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> property to `true`.</span></span>  
  
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
    > <span data-ttu-id="aec19-111">Anche se il valore viene visualizzato nel formato esadecimale, i test eseguiti sulla proprietà <xref:System.Windows.Forms.NumericUpDown.Value%2A> ne verificheranno il valore decimale.</span><span class="sxs-lookup"><span data-stu-id="aec19-111">Even if the value is displayed on the form as hexadecimal, any tests you perform on the <xref:System.Windows.Forms.NumericUpDown.Value%2A> property will be testing its decimal value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aec19-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aec19-112">See also</span></span>

- <xref:System.Windows.Forms.NumericUpDown>
- [<span data-ttu-id="aec19-113">Controllo NumericUpDown</span><span class="sxs-lookup"><span data-stu-id="aec19-113">NumericUpDown Control</span></span>](numericupdown-control-windows-forms.md)
- [<span data-ttu-id="aec19-114">Cenni preliminari sul controllo NumericUpDown</span><span class="sxs-lookup"><span data-stu-id="aec19-114">NumericUpDown Control Overview</span></span>](numericupdown-control-overview-windows-forms.md)
