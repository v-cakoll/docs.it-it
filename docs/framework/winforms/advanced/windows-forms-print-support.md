---
title: Supporto per la stampa in Windows Form
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms, printing
- printing [Windows Forms]
- forms [Windows Forms], printing (using designer)
- printing [Windows Forms], Windows Forms, support
- printing [Windows Forms], print support
ms.assetid: a4a2960c-eb70-48e2-b641-cfb222704e46
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 81f89ee41eb9f8b492ab12e30ae4580cdffbd8f4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="windows-forms-print-support"></a>Supporto per la stampa in Windows Form
Stampa in Windows Form è costituita principalmente tramite il [sul componente PrintDocument](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md) componente per consentire all'utente di stampare e il [controllo PrintPreviewDialog](../../../../docs/framework/winforms/controls/printpreviewdialog-control-windows-forms.md) controllo [PrintDialog Componente](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md) e [componente PageSetupDialog](../../../../docs/framework/winforms/controls/pagesetupdialog-component-windows-forms.md) i componenti per fornire un'interfaccia grafica familiare agli utenti di familiarizzare con il sistema operativo Windows.  
  
 In genere, si crea una nuova istanza del <xref:System.Drawing.Printing.PrintDocument> componente, impostare le proprietà che descrivono cosa stampare utilizzando il <xref:System.Drawing.Printing.PrinterSettings> e <xref:System.Drawing.Printing.PageSettings> classi e chiamare il <xref:System.Drawing.Printing.PrintDocument.Print%2A> metodo per stampare il documento.  
  
 Nel corso di stampa da un'applicazione basata su Windows, il <xref:System.Drawing.Printing.PrintDocument> componente consentirà di visualizzare la finestra di dialogo Stampa interruzione per avvisare gli utenti per il fatto che si verifichi la stampa e per consentire il processo di stampa deve essere annullato.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Procedura: Creare processi di stampa standard per Windows Form](../../../../docs/framework/winforms/advanced/how-to-create-standard-windows-forms-print-jobs.md)  
 Viene illustrato come utilizzare il <xref:System.Drawing.Printing.PrintDocument> per stampare da un Windows Form.  
  
 [Procedura: Acquisire l'input dell'utente da un elemento PrintDialog in fase di esecuzione](../../../../docs/framework/winforms/advanced/how-to-capture-user-input-from-a-printdialog-at-run-time.md)  
 Viene descritto come modificare alcune opzioni di stampa a livello di codice utilizzando il <xref:System.Windows.Forms.PrintDialog> componente.  
  
 [Procedura: Selezionare le stampanti connesse al computer dell'utente in Windows Form](../../../../docs/framework/winforms/advanced/how-to-choose-the-printers-attached-to-user-computer-in-windows-forms.md)  
 Viene descritto come cambiare la stampante per stampare utilizzando il <xref:System.Windows.Forms.PrintDialog> componente in fase di esecuzione.  
  
 [Procedura: stampare grafica in Windows Forms](../../../../docs/framework/winforms/advanced/how-to-print-graphics-in-windows-forms.md)  
 Descrive l'invio di grafica per la stampante.  
  
 [Procedura: stampare un file di testo con più pagine in Windows Forms](../../../../docs/framework/winforms/advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md)  
 Descrive l'invio di testo alla stampante.  
  
 [Procedura: Completare processi di stampa in Windows Form](../../../../docs/framework/winforms/advanced/how-to-complete-windows-forms-print-jobs.md)  
 Viene illustrato come avvisare gli utenti per il completamento di un processo di stampa.  
  
 [Procedura: Stampare un Windows Form](../../../../docs/framework/winforms/advanced/how-to-print-a-windows-form.md)  
 Viene illustrato come stampare una copia del modulo corrente.  
  
 [Procedura: Stampare in Windows Form tramite l'anteprima di stampa](../../../../docs/framework/winforms/advanced/how-to-print-in-windows-forms-using-print-preview.md)  
 Viene illustrato come utilizzare un <xref:System.Windows.Forms.PrintPreviewDialog> per la stampa del documento.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [PrintDocument (componente)](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md)  
 Viene illustrato l'utilizzo del <xref:System.Drawing.Printing.PrintDocument> componente.  
  
 [Componente PrintDialog](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md)  
 Viene illustrato l'utilizzo del <xref:System.Windows.Forms.PrintDialog> componente.  
  
 [Controllo PrintPreviewDialog](../../../../docs/framework/winforms/controls/printpreviewdialog-control-windows-forms.md)  
 Viene illustrato l'utilizzo del <xref:System.Windows.Forms.PrintPreviewDialog> controllo.  
  
 [Componente PageSetupDialog](../../../../docs/framework/winforms/controls/pagesetupdialog-component-windows-forms.md)  
 Viene illustrato l'utilizzo del <xref:System.Windows.Forms.PageSetupDialog> componente.  
  
 <xref:System.Drawing.Printing>  
 Vengono descritte le classi di <xref:System.Drawing.Printing> dello spazio dei nomi.
