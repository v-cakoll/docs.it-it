---
title: Cenni preliminari sul controllo NumericUpDown (Windows Form)
ms.date: 03/30/2017
f1_keywords:
- NumericUpDown
helpviewer_keywords:
- numeric spin button control [Windows Forms], Windows Forms
- NumericUpDown control [Windows Forms], about NumericUpDown control
- spin button control [Windows Forms], Windows Forms
ms.assetid: cff3cf30-4d46-4381-87df-37bfe83c71c5
ms.openlocfilehash: b1f32a767d27ef2f4e5629947d67097272695d9f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="numericupdown-control-overview-windows-forms"></a>Cenni preliminari sul controllo NumericUpDown (Windows Form)
Il <xref:System.Windows.Forms.NumericUpDown> controllo è simile a una combinazione di una casella di testo e una coppia di frecce che l'utente può fare clic per modificare un valore. Il controllo Visualizza e imposta un valore numerico singolo da un elenco di scelte fisse di valori numerici. L'utente può aumentare e ridurre il numero facendo clic sulla freccia e freccia giù, premendo i tasti freccia su e giù o digitando un numero nella casella di testo inclusa del controllo. Fare clic su freccia su Sposta il numero verso il valore massimo; Fare clic sulla freccia giù sposta il numero verso il valore minimo.  
  
 A causa di sua versatilità questo controllo è una scelta ovvia, ad esempio, se si desidera creare un controllo volume per un'applicazione lettore musicale. Il <xref:System.Windows.Forms.NumericUpDown> controllo viene utilizzato in molte applicazioni del Pannello di controllo di Windows.  
  
## <a name="key-properties-and-methods"></a>Metodi e proprietà chiave  
 I numeri visualizzati nella casella di testo del controllo possono essere una varietà di formati, tra cui esadecimali. Per ulteriori informazioni, vedere [procedura: impostare il formato per il controllo NumericUpDown Windows Form](../../../../docs/framework/winforms/controls/how-to-set-the-format-for-the-windows-forms-numericupdown-control.md). Le proprietà principali del controllo sono <xref:System.Windows.Forms.NumericUpDown.Value%2A>, <xref:System.Windows.Forms.NumericUpDown.Maximum%2A> (valore predefinito 100), <xref:System.Windows.Forms.NumericUpDown.Minimum%2A> (valore predefinito: 0), e <xref:System.Windows.Forms.NumericUpDown.Increment%2A> (valore 1 (impostazione predefinita). Il <xref:System.Windows.Forms.NumericUpDown.Value%2A> proprietà imposta il numero corrente selezionato nel controllo. Il <xref:System.Windows.Forms.NumericUpDown.Increment%2A> proprietà imposta la quantità che il numero viene modificato da quando l'utente fa clic su una freccia su o freccia giù. Quando lo stato attivo si sposta dal controllo, qualsiasi valore immesso verrà convalidato a fronte di valori numerici minimi e massimo. È possibile aumentare la velocità con cui il controllo si sposta tra i numeri, quando l'utente preme continuamente l'alto o verso il basso freccia, con la <xref:System.Windows.Forms.NumericUpDown.Accelerations%2A> proprietà. I metodi principali del controllo sono <xref:System.Windows.Forms.NumericUpDown.UpButton%2A> e <xref:System.Windows.Forms.NumericUpDown.DownButton%2A>.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.NumericUpDown>  
 [Controllo NumericUpDown](../../../../docs/framework/winforms/controls/numericupdown-control-windows-forms.md)  
 [Procedura: Impostare il formato per il controllo NumericUpDown Windows Form](../../../../docs/framework/winforms/controls/how-to-set-the-format-for-the-windows-forms-numericupdown-control.md)  
 [Controllo TextBox](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)
