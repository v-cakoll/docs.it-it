---
title: Supporto per la stampa in Windows Form
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, printing
- printing [Windows Forms]
- forms [Windows Forms], printing (using designer)
- printing [Windows Forms], Windows Forms, support
- printing [Windows Forms], print support
ms.assetid: a4a2960c-eb70-48e2-b641-cfb222704e46
ms.openlocfilehash: 8e008f2cb4b2f32cdba676e68d9fd790530e2b06
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57708132"
---
# <a name="windows-forms-print-support"></a>Supporto per la stampa in Windows Form
Stampa in Windows Form è costituita principalmente tramite il [sul componente PrintDocument](../controls/printdocument-component-windows-forms.md) componente per consentire all'utente di stampare e il [controllo PrintPreviewDialog](../controls/printpreviewdialog-control-windows-forms.md) controllo, [PrintDialog Componente](../controls/printdialog-component-windows-forms.md) e [componente PageSetupDialog](../controls/pagesetupdialog-component-windows-forms.md) componenti per fornire un'interfaccia grafica familiare agli utenti di familiarizzare con il sistema operativo Windows.  
  
 In genere, si crea una nuova istanza della <xref:System.Drawing.Printing.PrintDocument> componente, impostare le proprietà che descrivono cosa stampare utilizzando la <xref:System.Drawing.Printing.PrinterSettings> e <xref:System.Drawing.Printing.PageSettings> classi e chiamare il <xref:System.Drawing.Printing.PrintDocument.Print%2A> metodo effettivamente stampa del documento.  
  
 Nel corso di stampa da un'applicazione basata su Windows, il <xref:System.Drawing.Printing.PrintDocument> componente consentirà di visualizzare la finestra di dialogo Stampa abort per avvisare gli utenti per il fatto che è in corso la stampa e per consentire il processo di stampa deve essere annullata.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Procedura: Creare processi di stampa Standard di Windows Form](how-to-create-standard-windows-forms-print-jobs.md)  
 Viene illustrato come utilizzare il <xref:System.Drawing.Printing.PrintDocument> componente stampare da un modulo di Windows.  
  
 [Procedura: Acquisire l'Input dell'utente da un elemento PrintDialog in fase di esecuzione](how-to-capture-user-input-from-a-printdialog-at-run-time.md)  
 Viene spiegato come modificare alcune opzioni di stampa a livello di codice usando il <xref:System.Windows.Forms.PrintDialog> componente.  
  
 [Procedura: Selezionare le stampanti connesse al Computer dell'utente in Windows Form](how-to-choose-the-printers-attached-to-user-computer-in-windows-forms.md)  
 Viene descritto come cambiare la stampante per stampare utilizzando la <xref:System.Windows.Forms.PrintDialog> componente in fase di esecuzione.  
  
 [Procedura: Stampare grafica in Windows Form](how-to-print-graphics-in-windows-forms.md)  
 Descrive l'invio della grafica per la stampante.  
  
 [Procedura: Stampare un File di testo con più pagine in Windows Form](how-to-print-a-multi-page-text-file-in-windows-forms.md)  
 Descrive il testo inviano alla stampante.  
  
 [Procedura: Processi di stampa di Windows completo form](how-to-complete-windows-forms-print-jobs.md)  
 Viene illustrato come gli utenti per il completamento di un processo di stampa di avviso.  
  
 [Procedura: Stampare un Windows Form](how-to-print-a-windows-form.md)  
 Viene illustrato come stampare una copia del modulo corrente.  
  
 [Procedura: Stampa in Windows Form tramite l'anteprima di stampa](how-to-print-in-windows-forms-using-print-preview.md)  
 Viene illustrato come utilizzare un <xref:System.Windows.Forms.PrintPreviewDialog> per stampare un documento.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [PrintDocument (componente)](../controls/printdocument-component-windows-forms.md)  
 Illustra l'utilizzo del <xref:System.Drawing.Printing.PrintDocument> componente.  
  
 [Componente PrintDialog](../controls/printdialog-component-windows-forms.md)  
 Illustra l'utilizzo del <xref:System.Windows.Forms.PrintDialog> componente.  
  
 [Controllo PrintPreviewDialog](../controls/printpreviewdialog-control-windows-forms.md)  
 Illustra l'utilizzo del <xref:System.Windows.Forms.PrintPreviewDialog> controllo.  
  
 [Componente PageSetupDialog](../controls/pagesetupdialog-component-windows-forms.md)  
 Illustra l'utilizzo del <xref:System.Windows.Forms.PageSetupDialog> componente.  
  
 <xref:System.Drawing.Printing>  
 Vengono descritte le classi di <xref:System.Drawing.Printing> dello spazio dei nomi.
