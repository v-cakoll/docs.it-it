---
title: Cenni preliminari sul controllo PrintPreviewDialog (Windows Form)
ms.date: 01/08/2018
f1_keywords:
- PrintPreviewDialog
helpviewer_keywords:
- PrintPreviewDialog control (using designer), about PrintPreviewDialog
ms.assetid: efd4ee8d-6edd-47ec-88e4-4a4759bd2384
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0946220017fb78775f045bb225d84ea95aecd06b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="printpreviewdialog-control-overview-windows-forms"></a>Cenni preliminari sul controllo PrintPreviewDialog (Windows Form)
Windows Form <xref:System.Windows.Forms.PrintPreviewDialog> controllo è una finestra di dialogo preconfigurata che consente di visualizzare come un [PrintDocument](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md) verrà stampato. Utilizzato all'interno dell'applicazione basate su Windows come semplice soluzione anziché configurare la propria finestra di dialogo. Il controllo contiene pulsanti per la stampa, l'ingrandimento, la visualizzazione di una o più pagine e la chiusura della finestra di dialogo.  
  
## <a name="key-properties-and-methods"></a>Metodi e proprietà chiave  
 Proprietà chiave del controllo è <xref:System.Windows.Forms.PrintPreviewDialog.Document%2A>, che imposta il documento da visualizzare in anteprima. Il documento deve essere un <xref:System.Drawing.Printing.PrintDocument> oggetto. Per visualizzare la finestra di dialogo, è necessario chiamare il relativo <xref:System.Windows.Forms.Form.ShowDialog%2A> metodo. Anti-aliasing può visualizzare il testo più uniforme, ma può inoltre consentire la visualizzazione. Per utilizzarla, impostare il <xref:System.Windows.Forms.PrintPreviewDialog.UseAntiAlias%2A> proprietà `true`.  
  
 Alcune proprietà sono disponibili tramite il <xref:System.Windows.Forms.PrintPreviewControl> che il <xref:System.Windows.Forms.PrintPreviewDialog> contiene. (Non è necessario aggiungere questo <xref:System.Windows.Forms.PrintPreviewControl> al form; viene automaticamente incluso all'interno di <xref:System.Windows.Forms.PrintPreviewDialog> quando si aggiunge la finestra di dialogo al form.) Esempi di proprietà disponibili tramite il <xref:System.Windows.Forms.PrintPreviewControl> sono il <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> e <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A> che determinano il numero di pagine visualizzate orizzontalmente e verticalmente il controllo. È possibile accedere ai <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> proprietà come `PrintPreviewDialog1.PrintPreviewControl.Columns` in Visual Basic `printPreviewDialog1.PrintPreviewControl.Columns` in Visual c#, oppure `printPreviewDialog1->PrintPreviewControl->Columns` in [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)].  
  
## <a name="printpreviewdialog-performance"></a>Prestazioni PrintPreviewDialog

Le condizioni seguenti, il <xref:System.Windows.Forms.PrintPreviewDialog> controllo Inizializza molto lenta:

- Viene utilizzata una stampante di rete.
- Le preferenze dell'utente per la stampante, ad esempio impostazioni duplex, sono state modificate.
  
Per le App in esecuzione in .NET Framework 4.5.2, è possibile aggiungere la chiave seguente per il \<appSettings > della sezione del file di configurazione per migliorare le prestazioni di <xref:System.Windows.Forms.PrintPreviewDialog> controllano l'inizializzazione:

```xml
<appSettings>
   <add key="EnablePrintPreviewOptimization" value="true" />
</appSettings>
```
Se il `EnablePrintPreviewOptimization` chiave è impostata su qualsiasi altro valore, o se la chiave non è presente, l'ottimizzazione non viene applicato.

Le applicazioni in esecuzione in .NET Framework 4.6 o in versioni successive, è possibile aggiungere la seguente opzione per il [ \<AppContextSwitchOverrides >](../../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) elemento il [ \<runtime >](../../configure-apps/file-schema/runtime/index.md) sezione del file di configurazione dell'app:

```xml
<runtime >
   <!-- AppContextSwitchOverrides values are in the form of 'key1=true|false;key2=true|false -->
   <AppContextSwitchOverrides value = "Switch.System.Drawing.Printing.OptimizePrintPreview=true" />
</runtime >
``` 
Se l'opzione non è presente o se è impostato su qualsiasi altro valore, l'ottimizzazione non viene applicato. 

Se si utilizza il <xref:System.Drawing.Printing.PrintDocument.QueryPageSettings> evento per modificare le impostazioni della stampante, le prestazioni dei <xref:System.Windows.Forms.PrintPreviewDialog> controllo non migliorerà anche se è impostata un'opzione di configurazione di ottimizzazione.  

## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.PrintPreviewDialog>  
 [Panoramica sul controllo PrintPreviewControl](../../../../docs/framework/winforms/controls/printpreviewcontrol-control-overview-windows-forms.md)  
 [Controllo PrintPreviewDialog](../../../../docs/framework/winforms/controls/printpreviewdialog-control-windows-forms.md)  
 [Controlli e componenti della finestra di dialogo](../../../../docs/framework/winforms/controls/dialog-box-controls-and-components-windows-forms.md)
