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
# <a name="how-to-set-the-format-for-the-windows-forms-numericupdown-control"></a>Procedura: impostare il formato per il controllo NumericUpDown Windows Form
È possibile configurare la modalità di visualizzazione dei valori nel controllo Windows Forms <xref:System.Windows.Forms.NumericUpDown>. La proprietà <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> determina il numero di numeri visualizzati dopo il separatore decimale. il valore predefinito è 0. La proprietà <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> determina se verrà inserito un separatore tra tre cifre decimali. il valore predefinito è `false`. Il controllo può visualizzare i valori in formato esadecimale anziché decimale, se la proprietà <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> è impostata su `true`; il valore predefinito è `false`.  
  
### <a name="to-format-the-numeric-value"></a>Per formattare il valore numerico  
  
- Visualizzare un valore decimale impostando la proprietà <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> su un valore integer e impostando la proprietà <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> su `true` o `false`.  
  
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
  
- Consente di visualizzare un valore esadecimale impostando la proprietà <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> su `true`.  
  
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
    > Anche se il valore viene visualizzato nel formato esadecimale, i test eseguiti sulla proprietà <xref:System.Windows.Forms.NumericUpDown.Value%2A> ne verificheranno il valore decimale.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.NumericUpDown>
- [Controllo NumericUpDown](numericupdown-control-windows-forms.md)
- [Cenni preliminari sul controllo NumericUpDown](numericupdown-control-overview-windows-forms.md)
