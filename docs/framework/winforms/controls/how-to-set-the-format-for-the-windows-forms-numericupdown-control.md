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
# <a name="how-to-set-the-format-for-the-windows-forms-numericupdown-control"></a>Procedura: Impostare il formato per il controllo NumericUpDown di Windows Forms
È possibile configurare come valori vengono visualizzati nei moduli di Windows <xref:System.Windows.Forms.NumericUpDown> controllo. Il <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> proprietà determina il numero di cifre visualizzate dopo il separatore decimale; il valore predefinito è 0. Il <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> proprietà determina se inserire un separatore tra ogni tre cifre decimali; il valore predefinito è `false`. Il controllo può visualizzare i valori in formato esadecimale invece di formato decimale, se il <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> è impostata su `true`; il valore predefinito è `false`.  
  
### <a name="to-format-the-numeric-value"></a>Per formattare il valore numerico  
  
- Visualizzare un valore decimale impostando il <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> proprietà a un numero intero e impostare il <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> proprietà `true` o `false`.  
  
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
  
- Visualizzare un valore esadecimale, impostando il <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> proprietà `true`.  
  
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
    >  Anche se il valore viene visualizzato nel form come cifre esadecimali, eventuali test eseguito sul <xref:System.Windows.Forms.NumericUpDown.Value%2A> proprietà verrà testato il valore decimale.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.NumericUpDown>
- [Controllo NumericUpDown](numericupdown-control-windows-forms.md)
- [Cenni preliminari sul controllo NumericUpDown](numericupdown-control-overview-windows-forms.md)
