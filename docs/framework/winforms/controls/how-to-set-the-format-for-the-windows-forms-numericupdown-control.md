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
ms.openlocfilehash: 6db7a1b2aeb7282c3ac827cb8319706ed348fc22
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69949156"
---
# <a name="how-to-set-the-format-for-the-windows-forms-numericupdown-control"></a>Procedura: Impostare il formato per il controllo NumericUpDown di Windows Forms
È possibile configurare la modalità di visualizzazione dei valori nel <xref:System.Windows.Forms.NumericUpDown> controllo Windows Forms. La <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> proprietà determina il numero di numeri visualizzati dopo il separatore decimale. il valore predefinito è 0. La <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> proprietà determina se un separatore verrà inserito tra tre cifre decimali. il valore `false`predefinito è. Il controllo può visualizzare i valori in formato esadecimale anziché decimale <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> , se la proprietà `true`è impostata su. `false`il valore predefinito è.  
  
### <a name="to-format-the-numeric-value"></a>Per formattare il valore numerico  
  
- Visualizzare un valore decimale <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> impostando la proprietà su un intero e impostando la `false` <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> proprietà su `true` o.  
  
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
  
     -oppure-  
  
- Per visualizzare un valore esadecimale, <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> impostare la `true`proprietà su.  
  
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
    > Anche se il valore viene visualizzato nel formato esadecimale, i test eseguiti sulla <xref:System.Windows.Forms.NumericUpDown.Value%2A> proprietà ne verificheranno il valore decimale.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.NumericUpDown>
- [Controllo NumericUpDown](numericupdown-control-windows-forms.md)
- [Cenni preliminari sul controllo NumericUpDown](numericupdown-control-overview-windows-forms.md)
