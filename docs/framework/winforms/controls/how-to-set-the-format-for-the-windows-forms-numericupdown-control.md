---
title: 'Procedura: Impostare il formato per il controllo NumericUpDown di Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- NumericUpDown control [Windows Forms], formatting values
- up-down controls [Windows Forms], formatting numeric values
ms.assetid: fa7c5557-6bfb-45b2-975d-8887b23b0ba0
ms.openlocfilehash: 5957a44c7b07aa1b8d8df32667f023c0873ec1de
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62013192"
---
# <a name="how-to-set-the-format-for-the-windows-forms-numericupdown-control"></a><span data-ttu-id="ef53f-102">Procedura: Impostare il formato per il controllo NumericUpDown di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ef53f-102">How to: Set the Format for the Windows Forms NumericUpDown Control</span></span>
<span data-ttu-id="ef53f-103">È possibile configurare come valori vengono visualizzati nei moduli di Windows <xref:System.Windows.Forms.NumericUpDown> controllo.</span><span class="sxs-lookup"><span data-stu-id="ef53f-103">You can configure how values are displayed in the Windows Forms <xref:System.Windows.Forms.NumericUpDown> control.</span></span> <span data-ttu-id="ef53f-104">Il <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> proprietà determina il numero di cifre visualizzate dopo il separatore decimale; il valore predefinito è 0.</span><span class="sxs-lookup"><span data-stu-id="ef53f-104">The <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> property determines how many numbers appear after the decimal point; the default is 0.</span></span> <span data-ttu-id="ef53f-105">Il <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> proprietà determina se inserire un separatore tra ogni tre cifre decimali; il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="ef53f-105">The <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> property determines whether a separator will be inserted between every three decimal digits; the default is `false`.</span></span> <span data-ttu-id="ef53f-106">Il controllo può visualizzare i valori in formato esadecimale invece di formato decimale, se il <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> è impostata su `true`; il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="ef53f-106">The control can display values in hexadecimal instead of decimal format, if the <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> property is set to `true`; the default is `false`.</span></span>  
  
### <a name="to-format-the-numeric-value"></a><span data-ttu-id="ef53f-107">Per formattare il valore numerico</span><span class="sxs-lookup"><span data-stu-id="ef53f-107">To format the numeric value</span></span>  
  
- <span data-ttu-id="ef53f-108">Visualizzare un valore decimale impostando il <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> proprietà a un numero intero e impostare il <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> proprietà `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="ef53f-108">Display a decimal value by setting the <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> property to an integer and setting the <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> property to `true` or `false`.</span></span>  
  
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
  
     <span data-ttu-id="ef53f-109">-oppure-</span><span class="sxs-lookup"><span data-stu-id="ef53f-109">-or-</span></span>  
  
- <span data-ttu-id="ef53f-110">Visualizzare un valore esadecimale, impostando il <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> proprietà `true`.</span><span class="sxs-lookup"><span data-stu-id="ef53f-110">Display a hexadecimal value by setting the <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> property to `true`.</span></span>  
  
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
    >  <span data-ttu-id="ef53f-111">Anche se il valore viene visualizzato nel form come cifre esadecimali, eventuali test eseguito sul <xref:System.Windows.Forms.NumericUpDown.Value%2A> proprietà verrà testato il valore decimale.</span><span class="sxs-lookup"><span data-stu-id="ef53f-111">Even if the value is displayed on the form as hexadecimal, any tests you perform on the <xref:System.Windows.Forms.NumericUpDown.Value%2A> property will be testing its decimal value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef53f-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ef53f-112">See also</span></span>

- <xref:System.Windows.Forms.NumericUpDown>
- [<span data-ttu-id="ef53f-113">Controllo NumericUpDown</span><span class="sxs-lookup"><span data-stu-id="ef53f-113">NumericUpDown Control</span></span>](numericupdown-control-windows-forms.md)
- [<span data-ttu-id="ef53f-114">Cenni preliminari sul controllo NumericUpDown</span><span class="sxs-lookup"><span data-stu-id="ef53f-114">NumericUpDown Control Overview</span></span>](numericupdown-control-overview-windows-forms.md)
