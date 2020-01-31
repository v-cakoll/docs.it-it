---
title: Cenni preliminari sul controllo PrintPreviewDialog
ms.date: 01/08/2018
f1_keywords:
- PrintPreviewDialog
helpviewer_keywords:
- PrintPreviewDialog control (using designer), about PrintPreviewDialog
ms.assetid: efd4ee8d-6edd-47ec-88e4-4a4759bd2384
ms.openlocfilehash: 6fb971493336cda1e04c720dd09147e650918c3a
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741417"
---
# <a name="printpreviewdialog-control-overview-windows-forms"></a>Cenni preliminari sul controllo PrintPreviewDialog (Windows Forms)

Il controllo <xref:System.Windows.Forms.PrintPreviewDialog> Windows Forms è una finestra di dialogo preconfigurata utilizzata per visualizzare la modalità di visualizzazione di un [PrintDocument](printdocument-component-windows-forms.md) quando viene stampato. Utilizzarlo all'interno dell'applicazione basata su Windows come soluzione semplice anziché configurare la propria finestra di dialogo. Il controllo contiene pulsanti per la stampa, l'ingrandimento, la visualizzazione di una o più pagine e la chiusura della finestra di dialogo.

## <a name="key-properties-and-methods"></a>Proprietà e metodi chiave

La proprietà chiave del controllo è <xref:System.Windows.Forms.PrintPreviewDialog.Document%2A>, che imposta il documento da visualizzare in anteprima. Il documento deve essere un oggetto <xref:System.Drawing.Printing.PrintDocument>. Per visualizzare la finestra di dialogo, è necessario chiamare il relativo metodo <xref:System.Windows.Forms.Form.ShowDialog%2A>. L'anti-aliasing può rendere il testo più semplice, ma può anche rendere più lenta la visualizzazione. per usarlo, impostare la proprietà <xref:System.Windows.Forms.PrintPreviewDialog.UseAntiAlias%2A> su `true`.

Alcune proprietà sono disponibili tramite il <xref:System.Windows.Forms.PrintPreviewControl> contenuto nel <xref:System.Windows.Forms.PrintPreviewDialog>. Non è necessario aggiungere questo <xref:System.Windows.Forms.PrintPreviewControl> al modulo. viene automaticamente contenuto all'interno del <xref:System.Windows.Forms.PrintPreviewDialog> quando si aggiunge la finestra di dialogo al form. Esempi di proprietà disponibili tramite il <xref:System.Windows.Forms.PrintPreviewControl> sono le proprietà <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> e <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A>, che determinano il numero di pagine visualizzate orizzontalmente e verticalmente sul controllo. È possibile accedere alla proprietà <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> come `PrintPreviewDialog1.PrintPreviewControl.Columns` in Visual Basic, `printPreviewDialog1.PrintPreviewControl.Columns` in Visual C#o `printPreviewDialog1->PrintPreviewControl->Columns` in Visual C++.

## <a name="printpreviewdialog-performance"></a>Prestazioni di PrintPreviewDialog

Nelle condizioni seguenti, il controllo <xref:System.Windows.Forms.PrintPreviewDialog> viene inizializzato molto lentamente:

- Viene utilizzata una stampante di rete.
- Vengono modificate le preferenze utente per questa stampante, ad esempio le impostazioni duplex.

Per le app in esecuzione nel .NET Framework 4.5.2, è possibile aggiungere la chiave seguente alla sezione \<appSettings > del file di configurazione per migliorare le prestazioni dell'inizializzazione del controllo <xref:System.Windows.Forms.PrintPreviewDialog>:

```xml
<appSettings>
   <add key="EnablePrintPreviewOptimization" value="true" />
</appSettings>
```

Se la chiave di `EnablePrintPreviewOptimization` è impostata su qualsiasi altro valore o se la chiave non è presente, l'ottimizzazione non viene applicata.

Per le app in esecuzione in .NET Framework 4,6 o versioni successive, è possibile aggiungere l'opzione seguente all'elemento [\<AppContextSwitchOverrides](../../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) nella sezione [\<Runtime >](../../configure-apps/file-schema/runtime/index.md) del file di configurazione dell'app:

```xml
<runtime >
   <!-- AppContextSwitchOverrides values are in the form of 'key1=true|false;key2=true|false -->
   <AppContextSwitchOverrides value = "Switch.System.Drawing.Printing.OptimizePrintPreview=true" />
</runtime >
```

Se l'opzione non è presente o è impostata su un altro valore, l'ottimizzazione non viene applicata.

Se si utilizza l'evento <xref:System.Drawing.Printing.PrintDocument.QueryPageSettings> per modificare le impostazioni della stampante, le prestazioni del controllo <xref:System.Windows.Forms.PrintPreviewDialog> non miglioreranno anche se è impostata un'opzione di configurazione dell'ottimizzazione.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.PrintPreviewDialog>
- [Panoramica sul controllo PrintPreviewControl](printpreviewcontrol-control-overview-windows-forms.md)
- [Controllo PrintPreviewDialog](printpreviewdialog-control-windows-forms.md)
- [Controlli e componenti della finestra di dialogo](dialog-box-controls-and-components-windows-forms.md)
