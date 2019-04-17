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
ms.openlocfilehash: 961b3c852f60a0917707bef07d4e26fc4215acca
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2019
ms.locfileid: "59611120"
---
# <a name="printpreviewdialog-control-overview-windows-forms"></a>Cenni preliminari sul controllo PrintPreviewDialog (Windows Form)

I moduli di Windows <xref:System.Windows.Forms.PrintPreviewDialog> controllo è una finestra di dialogo preconfigurata che consente di visualizzare come un [PrintDocument](printdocument-component-windows-forms.md) verrà stampato. Usarlo all'interno dell'applicazione basata su Windows come una soluzione semplice invece di configurare una propria finestra di dialogo. Il controllo contiene pulsanti per la stampa, l'ingrandimento, la visualizzazione di una o più pagine e la chiusura della finestra di dialogo.

## <a name="key-properties-and-methods"></a>I metodi e proprietà chiave

Proprietà chiave del controllo è <xref:System.Windows.Forms.PrintPreviewDialog.Document%2A>, che imposta il documento da visualizzare in anteprima. Il documento deve essere un <xref:System.Drawing.Printing.PrintDocument> oggetto. Per visualizzare la finestra di dialogo, è necessario chiamare relativo <xref:System.Windows.Forms.Form.ShowDialog%2A> (metodo). Anti-aliasing può rendere il testo vengono visualizzati più uniforme, ma può anche rendere la visualizzazione. per usarlo, impostare il <xref:System.Windows.Forms.PrintPreviewDialog.UseAntiAlias%2A> proprietà `true`.

Alcune proprietà sono disponibili tramite il <xref:System.Windows.Forms.PrintPreviewControl> che il <xref:System.Windows.Forms.PrintPreviewDialog> contiene. (Non è necessario aggiungere quanto segue <xref:System.Windows.Forms.PrintPreviewControl> al form; viene automaticamente incluso all'interno di <xref:System.Windows.Forms.PrintPreviewDialog> quando si aggiunge la finestra di dialogo al form.) Esempi di proprietà disponibili tramite il <xref:System.Windows.Forms.PrintPreviewControl> sono le <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> e <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A> che determinano il numero di pagine visualizzate orizzontalmente e verticalmente sul controllo. È possibile accedere la <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> la proprietà `PrintPreviewDialog1.PrintPreviewControl.Columns` in Visual Basic `printPreviewDialog1.PrintPreviewControl.Columns` in Visual C#, o `printPreviewDialog1->PrintPreviewControl->Columns` nelle [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)].

## <a name="printpreviewdialog-performance"></a>Prestazioni controllo PrintPreviewDialog

Nelle condizioni seguenti, il <xref:System.Windows.Forms.PrintPreviewDialog> controllo Inizializza molto lenta:

- Viene utilizzata una stampante di rete.
- Le preferenze dell'utente per la stampante, ad esempio impostazioni duplex, vengono modificate.

Per le App in esecuzione in .NET Framework 4.5.2, è possibile aggiungere la seguente chiave per la \<appSettings > sezione del file di configurazione per migliorare le prestazioni di <xref:System.Windows.Forms.PrintPreviewDialog> controllano l'inizializzazione:

```xml
<appSettings>
   <add key="EnablePrintPreviewOptimization" value="true" />
</appSettings>
```

Se il `EnablePrintPreviewOptimization` chiave è impostata su qualsiasi altro valore, o se la chiave non è presente, non viene applicato l'ottimizzazione.

Per le App in esecuzione in .NET Framework 4.6 o versioni successive, è possibile aggiungere la seguente opzione per il [ \<AppContextSwitchOverrides >](../../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) elemento il [ \<runtime >](../../configure-apps/file-schema/runtime/index.md) sezione del file di configurazione dell'app:

```xml
<runtime >
   <!-- AppContextSwitchOverrides values are in the form of 'key1=true|false;key2=true|false -->
   <AppContextSwitchOverrides value = "Switch.System.Drawing.Printing.OptimizePrintPreview=true" />
</runtime >
```

Se l'opzione non è presente o se è impostata su qualsiasi altro valore, non viene applicata l'ottimizzazione.

Se si usa la <xref:System.Drawing.Printing.PrintDocument.QueryPageSettings> eventi per modificare le impostazioni della stampante, le prestazioni dei <xref:System.Windows.Forms.PrintPreviewDialog> controllo non migliorerà anche se è impostata un'opzione di configurazione di ottimizzazione.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.PrintPreviewDialog>
- [Panoramica sul controllo PrintPreviewControl](printpreviewcontrol-control-overview-windows-forms.md)
- [Controllo PrintPreviewDialog](printpreviewdialog-control-windows-forms.md)
- [Controlli e componenti della finestra di dialogo](dialog-box-controls-and-components-windows-forms.md)
