---
title: Supporto stampa
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, printing
- printing [Windows Forms]
- forms [Windows Forms], printing (using designer)
- printing [Windows Forms], Windows Forms, support
- printing [Windows Forms], print support
ms.assetid: a4a2960c-eb70-48e2-b641-cfb222704e46
ms.openlocfilehash: d6e8f60db7afe2f1b04eaae6fe71aa93e5c22cae
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76732499"
---
# <a name="windows-forms-print-support"></a>Supporto per la stampa in Windows Form
La stampa in Windows Forms è costituita principalmente dall'utilizzo del componente [PrintDocument](../controls/printdocument-component-windows-forms.md) per consentire all'utente di stampare e dal controllo di [controllo PrintPreviewDialog](../controls/printpreviewdialog-control-windows-forms.md) , dal [componente PrintDialog](../controls/printdialog-component-windows-forms.md) e dai componenti [PageSetupDialog](../controls/pagesetupdialog-component-windows-forms.md) per fornire un'interfaccia grafica familiare agli utenti abituati al sistema operativo Windows.  
  
 In genere, si crea una nuova istanza del componente <xref:System.Drawing.Printing.PrintDocument>, si impostano le proprietà che descrivono cosa stampare usando le classi <xref:System.Drawing.Printing.PrinterSettings> e <xref:System.Drawing.Printing.PageSettings> e si chiama il metodo <xref:System.Drawing.Printing.PrintDocument.Print%2A> per stampare effettivamente il documento.  
  
 Durante la stampa da un'applicazione basata su Windows, nel componente <xref:System.Drawing.Printing.PrintDocument> verrà visualizzata una finestra di dialogo Interrompi stampa per segnalare agli utenti il fatto che la stampa è in corso e per consentire l'annullamento del processo di stampa.  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Procedura: Creare processi di stampa standard per Windows Form](how-to-create-standard-windows-forms-print-jobs.md)  
 Viene illustrato come utilizzare il componente <xref:System.Drawing.Printing.PrintDocument> per stampare da un Windows Form.  
  
 [Procedura: Acquisire l'input dell'utente da un elemento PrintDialog in fase di esecuzione](how-to-capture-user-input-from-a-printdialog-at-run-time.md)  
 Viene illustrato come modificare le opzioni di stampa selezionate a livello di codice utilizzando il componente <xref:System.Windows.Forms.PrintDialog>.  
  
 [Procedura: Selezionare le stampanti connesse al computer dell'utente in Windows Form](how-to-choose-the-printers-attached-to-user-computer-in-windows-forms.md)  
 Viene descritta la modifica della stampante per la stampa in utilizzando il componente <xref:System.Windows.Forms.PrintDialog> in fase di esecuzione.  
  
 [Procedura: stampare grafica in Windows Forms](how-to-print-graphics-in-windows-forms.md)  
 Viene descritto come inviare grafica alla stampante.  
  
 [Procedura: stampare un file di testo con più pagine in Windows Forms](how-to-print-a-multi-page-text-file-in-windows-forms.md)  
 Viene descritto come inviare testo alla stampante.  
  
 [Procedura: Completare processi di stampa in Windows Form](how-to-complete-windows-forms-print-jobs.md)  
 Viene illustrato come segnalare agli utenti il completamento di un processo di stampa.  
  
 [Procedura: Stampare un Windows Form](how-to-print-a-windows-form.md)  
 Viene illustrato come stampare una copia del form corrente.  
  
 [Procedura: Stampare in Windows Form tramite l'anteprima di stampa](how-to-print-in-windows-forms-using-print-preview.md)  
 Viene illustrato come utilizzare un <xref:System.Windows.Forms.PrintPreviewDialog> per la stampa di un documento.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Componente PrintDocument](../controls/printdocument-component-windows-forms.md)  
 Viene illustrato l'utilizzo del componente <xref:System.Drawing.Printing.PrintDocument>.  
  
 [Componente PrintDialog](../controls/printdialog-component-windows-forms.md)  
 Viene illustrato l'utilizzo del componente <xref:System.Windows.Forms.PrintDialog>.  
  
 [Controllo PrintPreviewDialog](../controls/printpreviewdialog-control-windows-forms.md)  
 Viene illustrato l'utilizzo del controllo <xref:System.Windows.Forms.PrintPreviewDialog>.  
  
 [Componente PageSetupDialog](../controls/pagesetupdialog-component-windows-forms.md)  
 Viene illustrato l'utilizzo del componente <xref:System.Windows.Forms.PageSetupDialog>.  
  
 <xref:System.Drawing.Printing>  
 Descrive le classi nello spazio dei nomi <xref:System.Drawing.Printing>.
