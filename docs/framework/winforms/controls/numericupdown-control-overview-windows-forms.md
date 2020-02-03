---
title: Cenni preliminari sul controllo NumericUpDown
ms.date: 03/30/2017
f1_keywords:
- NumericUpDown
helpviewer_keywords:
- numeric spin button control [Windows Forms], Windows Forms
- NumericUpDown control [Windows Forms], about NumericUpDown control
- spin button control [Windows Forms], Windows Forms
ms.assetid: cff3cf30-4d46-4381-87df-37bfe83c71c5
ms.openlocfilehash: 3e24fa543df9028e9866d91ec60c3cf88578ac56
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740795"
---
# <a name="numericupdown-control-overview-windows-forms"></a>Cenni preliminari sul controllo NumericUpDown (Windows Form)
Il controllo <xref:System.Windows.Forms.NumericUpDown> si presenta come una combinazione di una casella di testo e di una coppia di frecce su cui l'utente può fare clic per modificare un valore. Il controllo Visualizza e imposta un singolo valore numerico da un elenco di scelte valore numerico fisse. L'utente può aumentare e diminuire il numero facendo clic sulle frecce verso l'alto e verso il basso, premendo i tasti freccia su e giù oppure digitando un numero nella casella di testo del controllo. Se si fa clic sul tasto freccia su, il numero viene spostato verso il valore massimo. facendo clic sul tasto freccia giù si sposta il numero verso il minimo.  
  
 Grazie alla relativa funzionalità versatile, questo controllo è una scelta ovvia, ad esempio, se si vuole creare un controllo del volume per un'applicazione Music Player. Il controllo <xref:System.Windows.Forms.NumericUpDown> viene usato in molte applicazioni del pannello di controllo di Windows.  
  
## <a name="key-properties-and-methods"></a>Proprietà e metodi chiave  
 I numeri visualizzati nella casella di testo del controllo possono avere un'ampia gamma di formati, incluso l'esadecimale. Per altre informazioni, vedere [procedura: impostare il formato per il controllo NumericUpDown Windows Forms](how-to-set-the-format-for-the-windows-forms-numericupdown-control.md). Le proprietà chiave del controllo sono <xref:System.Windows.Forms.NumericUpDown.Value%2A>, <xref:System.Windows.Forms.NumericUpDown.Maximum%2A> (valore predefinito 100), <xref:System.Windows.Forms.NumericUpDown.Minimum%2A> (valore predefinito 0) e <xref:System.Windows.Forms.NumericUpDown.Increment%2A> (valore predefinito 1). La proprietà <xref:System.Windows.Forms.NumericUpDown.Value%2A> imposta il numero corrente selezionato nel controllo. La proprietà <xref:System.Windows.Forms.NumericUpDown.Increment%2A> imposta la quantità di adattata al numero quando l'utente fa clic su una freccia verso l'alto o verso il basso. Quando lo stato attivo viene spostato fuori dal controllo, qualsiasi input tipizzato verrà convalidato in base ai valori numerici minimi e massimi. È possibile aumentare la velocità con cui il controllo passa attraverso i numeri, quando l'utente preme continuamente la freccia su o giù, con la proprietà <xref:System.Windows.Forms.NumericUpDown.Accelerations%2A>. I metodi principali del controllo sono <xref:System.Windows.Forms.NumericUpDown.UpButton%2A> e <xref:System.Windows.Forms.NumericUpDown.DownButton%2A>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.NumericUpDown>
- [Controllo NumericUpDown](numericupdown-control-windows-forms.md)
- [Procedura: Impostare il formato per il controllo NumericUpDown Windows Form](how-to-set-the-format-for-the-windows-forms-numericupdown-control.md)
- [Controllo TextBox](textbox-control-windows-forms.md)
