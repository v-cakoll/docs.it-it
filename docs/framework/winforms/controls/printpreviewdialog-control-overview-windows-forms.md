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
ms.openlocfilehash: aad8673051b22db1df6d525094394dd2a43285ca
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57711278"
---
# <a name="printpreviewdialog-control-overview-windows-forms"></a><span data-ttu-id="12443-102">Cenni preliminari sul controllo PrintPreviewDialog (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="12443-102">PrintPreviewDialog control overview (Windows Forms)</span></span>
<span data-ttu-id="12443-103">I moduli di Windows <xref:System.Windows.Forms.PrintPreviewDialog> controllo è una finestra di dialogo preconfigurata che consente di visualizzare come un [PrintDocument](printdocument-component-windows-forms.md) verrà stampato.</span><span class="sxs-lookup"><span data-stu-id="12443-103">The Windows Forms <xref:System.Windows.Forms.PrintPreviewDialog> control is a pre-configured dialog box used to display how a [PrintDocument](printdocument-component-windows-forms.md) will appear when printed.</span></span> <span data-ttu-id="12443-104">Usarlo all'interno dell'applicazione basata su Windows come una soluzione semplice invece di configurare una propria finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="12443-104">Use it within your Windows-based application as a simple solution instead of configuring your own dialog box.</span></span> <span data-ttu-id="12443-105">Il controllo contiene pulsanti per la stampa, l'ingrandimento, la visualizzazione di una o più pagine e la chiusura della finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="12443-105">The control contains buttons for printing, zooming in, displaying one or multiple pages, and closing the dialog box.</span></span>  
  
## <a name="key-properties-and-methods"></a><span data-ttu-id="12443-106">I metodi e proprietà chiave</span><span class="sxs-lookup"><span data-stu-id="12443-106">Key properties and methods</span></span>  
 <span data-ttu-id="12443-107">Proprietà chiave del controllo è <xref:System.Windows.Forms.PrintPreviewDialog.Document%2A>, che imposta il documento da visualizzare in anteprima.</span><span class="sxs-lookup"><span data-stu-id="12443-107">The control's key property is <xref:System.Windows.Forms.PrintPreviewDialog.Document%2A>, which sets the document to be previewed.</span></span> <span data-ttu-id="12443-108">Il documento deve essere un <xref:System.Drawing.Printing.PrintDocument> oggetto.</span><span class="sxs-lookup"><span data-stu-id="12443-108">The document must be a <xref:System.Drawing.Printing.PrintDocument> object.</span></span> <span data-ttu-id="12443-109">Per visualizzare la finestra di dialogo, è necessario chiamare relativo <xref:System.Windows.Forms.Form.ShowDialog%2A> (metodo).</span><span class="sxs-lookup"><span data-stu-id="12443-109">In order to display the dialog box, you must call its <xref:System.Windows.Forms.Form.ShowDialog%2A> method.</span></span> <span data-ttu-id="12443-110">Anti-aliasing può rendere il testo vengono visualizzati più uniforme, ma può anche rendere la visualizzazione. per usarlo, impostare il <xref:System.Windows.Forms.PrintPreviewDialog.UseAntiAlias%2A> proprietà `true`.</span><span class="sxs-lookup"><span data-stu-id="12443-110">Anti-aliasing can make the text appear smoother, but it can also make the display slower; to use it, set the <xref:System.Windows.Forms.PrintPreviewDialog.UseAntiAlias%2A> property to `true`.</span></span>  
  
 <span data-ttu-id="12443-111">Alcune proprietà sono disponibili tramite il <xref:System.Windows.Forms.PrintPreviewControl> che il <xref:System.Windows.Forms.PrintPreviewDialog> contiene.</span><span class="sxs-lookup"><span data-stu-id="12443-111">Certain properties are available through the <xref:System.Windows.Forms.PrintPreviewControl> that the <xref:System.Windows.Forms.PrintPreviewDialog> contains.</span></span> <span data-ttu-id="12443-112">(Non è necessario aggiungere quanto segue <xref:System.Windows.Forms.PrintPreviewControl> al form; viene automaticamente incluso all'interno di <xref:System.Windows.Forms.PrintPreviewDialog> quando si aggiunge la finestra di dialogo al form.) Esempi di proprietà disponibili tramite il <xref:System.Windows.Forms.PrintPreviewControl> sono le <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> e <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A> che determinano il numero di pagine visualizzate orizzontalmente e verticalmente sul controllo.</span><span class="sxs-lookup"><span data-stu-id="12443-112">(You do not have to add this <xref:System.Windows.Forms.PrintPreviewControl> to the form; it is automatically contained within the <xref:System.Windows.Forms.PrintPreviewDialog> when you add the dialog to your form.) Examples of properties available through the <xref:System.Windows.Forms.PrintPreviewControl> are the <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> and <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A> properties, which determine the number of pages displayed horizontally and vertically on the control.</span></span> <span data-ttu-id="12443-113">È possibile accedere la <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> la proprietà `PrintPreviewDialog1.PrintPreviewControl.Columns` in Visual Basic `printPreviewDialog1.PrintPreviewControl.Columns` in Visual C#, o `printPreviewDialog1->PrintPreviewControl->Columns` nelle [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)].</span><span class="sxs-lookup"><span data-stu-id="12443-113">You can access the <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> property as `PrintPreviewDialog1.PrintPreviewControl.Columns` in Visual Basic, `printPreviewDialog1.PrintPreviewControl.Columns` in Visual C#, or `printPreviewDialog1->PrintPreviewControl->Columns` in [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)].</span></span>  
  
## <a name="printpreviewdialog-performance"></a><span data-ttu-id="12443-114">Prestazioni controllo PrintPreviewDialog</span><span class="sxs-lookup"><span data-stu-id="12443-114">PrintPreviewDialog performance</span></span>

<span data-ttu-id="12443-115">Nelle condizioni seguenti, il <xref:System.Windows.Forms.PrintPreviewDialog> controllo Inizializza molto lenta:</span><span class="sxs-lookup"><span data-stu-id="12443-115">Under the following conditions, the <xref:System.Windows.Forms.PrintPreviewDialog> control initializes very slowly:</span></span>

- <span data-ttu-id="12443-116">Viene utilizzata una stampante di rete.</span><span class="sxs-lookup"><span data-stu-id="12443-116">A network printer is used.</span></span>
- <span data-ttu-id="12443-117">Le preferenze dell'utente per la stampante, ad esempio impostazioni duplex, vengono modificate.</span><span class="sxs-lookup"><span data-stu-id="12443-117">User preferences for this printer, such as duplex settings, are modified.</span></span>
  
<span data-ttu-id="12443-118">Per le App in esecuzione in .NET Framework 4.5.2, è possibile aggiungere la seguente chiave per la \<appSettings > sezione del file di configurazione per migliorare le prestazioni di <xref:System.Windows.Forms.PrintPreviewDialog> controllano l'inizializzazione:</span><span class="sxs-lookup"><span data-stu-id="12443-118">For apps running on the .NET Framework 4.5.2, you can add the following key to the \<appSettings> section of your configuration file to improve the performance of <xref:System.Windows.Forms.PrintPreviewDialog> control initialization:</span></span>

```xml
<appSettings>
   <add key="EnablePrintPreviewOptimization" value="true" />
</appSettings>
```
<span data-ttu-id="12443-119">Se il `EnablePrintPreviewOptimization` chiave è impostata su qualsiasi altro valore, o se la chiave non è presente, non viene applicato l'ottimizzazione.</span><span class="sxs-lookup"><span data-stu-id="12443-119">If the `EnablePrintPreviewOptimization` key is set to any other value, or if the key is not present, the optimization is not applied.</span></span>

<span data-ttu-id="12443-120">Per le App in esecuzione in .NET Framework 4.6 o versioni successive, è possibile aggiungere la seguente opzione per il [ \<AppContextSwitchOverrides >](../../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) elemento il [ \<runtime >](../../configure-apps/file-schema/runtime/index.md) sezione del file di configurazione dell'app:</span><span class="sxs-lookup"><span data-stu-id="12443-120">For apps running on the .NET Framework 4.6 or later versions, you can add the following switch to the [\<AppContextSwitchOverrides>](../../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element in the [\<runtime>](../../configure-apps/file-schema/runtime/index.md) section of your app config file:</span></span>

```xml
<runtime >
   <!-- AppContextSwitchOverrides values are in the form of 'key1=true|false;key2=true|false -->
   <AppContextSwitchOverrides value = "Switch.System.Drawing.Printing.OptimizePrintPreview=true" />
</runtime >
``` 
<span data-ttu-id="12443-121">Se l'opzione non è presente o se è impostata su qualsiasi altro valore, non viene applicata l'ottimizzazione.</span><span class="sxs-lookup"><span data-stu-id="12443-121">If the switch is not present or if it is set to any other value, the optimization is not applied.</span></span> 

<span data-ttu-id="12443-122">Se si usa la <xref:System.Drawing.Printing.PrintDocument.QueryPageSettings> eventi per modificare le impostazioni della stampante, le prestazioni dei <xref:System.Windows.Forms.PrintPreviewDialog> controllo non migliorerà anche se è impostata un'opzione di configurazione di ottimizzazione.</span><span class="sxs-lookup"><span data-stu-id="12443-122">If you use the <xref:System.Drawing.Printing.PrintDocument.QueryPageSettings> event to modify printer settings, the performance of the <xref:System.Windows.Forms.PrintPreviewDialog> control will not improve even if an optimization configuration switch is set.</span></span>  

## <a name="see-also"></a><span data-ttu-id="12443-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="12443-123">See also</span></span>
- <xref:System.Windows.Forms.PrintPreviewDialog>
- [<span data-ttu-id="12443-124">Panoramica sul controllo PrintPreviewControl</span><span class="sxs-lookup"><span data-stu-id="12443-124">PrintPreviewControl Control Overview</span></span>](printpreviewcontrol-control-overview-windows-forms.md)
- [<span data-ttu-id="12443-125">Controllo PrintPreviewDialog</span><span class="sxs-lookup"><span data-stu-id="12443-125">PrintPreviewDialog Control</span></span>](printpreviewdialog-control-windows-forms.md)
- [<span data-ttu-id="12443-126">Controlli e componenti della finestra di dialogo</span><span class="sxs-lookup"><span data-stu-id="12443-126">Dialog-Box Controls and Components</span></span>](dialog-box-controls-and-components-windows-forms.md)
