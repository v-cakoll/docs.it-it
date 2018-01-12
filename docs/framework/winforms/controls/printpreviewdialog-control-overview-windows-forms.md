---
title: Cenni preliminari sul controllo PrintPreviewDialog (Windows Form)
ms.custom: 
ms.date: 01/08/2018
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: PrintPreviewDialog
helpviewer_keywords: PrintPreviewDialog control (using designer), about PrintPreviewDialog
ms.assetid: efd4ee8d-6edd-47ec-88e4-4a4759bd2384
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1228a3cf39ea412cde341c4c4b8b83e0ab2f0299
ms.sourcegitcommit: 91691981897cf8451033cb01071d8f5d94017f97
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2018
---
# <a name="printpreviewdialog-control-overview-windows-forms"></a><span data-ttu-id="f702f-102">Cenni preliminari sul controllo PrintPreviewDialog (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="f702f-102">PrintPreviewDialog control overview (Windows Forms)</span></span>
<span data-ttu-id="f702f-103">Windows Form <xref:System.Windows.Forms.PrintPreviewDialog> controllo è una finestra di dialogo preconfigurata che consente di visualizzare come un [PrintDocument](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md) verrà stampato.</span><span class="sxs-lookup"><span data-stu-id="f702f-103">The Windows Forms <xref:System.Windows.Forms.PrintPreviewDialog> control is a pre-configured dialog box used to display how a [PrintDocument](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md) will appear when printed.</span></span> <span data-ttu-id="f702f-104">Utilizzato all'interno dell'applicazione basate su Windows come semplice soluzione anziché configurare la propria finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="f702f-104">Use it within your Windows-based application as a simple solution instead of configuring your own dialog box.</span></span> <span data-ttu-id="f702f-105">Il controllo contiene pulsanti per la stampa, l'ingrandimento, la visualizzazione di una o più pagine e la chiusura della finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="f702f-105">The control contains buttons for printing, zooming in, displaying one or multiple pages, and closing the dialog box.</span></span>  
  
## <a name="key-properties-and-methods"></a><span data-ttu-id="f702f-106">Metodi e proprietà chiave</span><span class="sxs-lookup"><span data-stu-id="f702f-106">Key properties and methods</span></span>  
 <span data-ttu-id="f702f-107">Proprietà chiave del controllo è <xref:System.Windows.Forms.PrintPreviewDialog.Document%2A>, che imposta il documento da visualizzare in anteprima.</span><span class="sxs-lookup"><span data-stu-id="f702f-107">The control's key property is <xref:System.Windows.Forms.PrintPreviewDialog.Document%2A>, which sets the document to be previewed.</span></span> <span data-ttu-id="f702f-108">Il documento deve essere un <xref:System.Drawing.Printing.PrintDocument> oggetto.</span><span class="sxs-lookup"><span data-stu-id="f702f-108">The document must be a <xref:System.Drawing.Printing.PrintDocument> object.</span></span> <span data-ttu-id="f702f-109">Per visualizzare la finestra di dialogo, è necessario chiamare il relativo <xref:System.Windows.Forms.Form.ShowDialog%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="f702f-109">In order to display the dialog box, you must call its <xref:System.Windows.Forms.Form.ShowDialog%2A> method.</span></span> <span data-ttu-id="f702f-110">Anti-aliasing può visualizzare il testo più uniforme, ma può inoltre consentire la visualizzazione. Per utilizzarla, impostare il <xref:System.Windows.Forms.PrintPreviewDialog.UseAntiAlias%2A> proprietà `true`.</span><span class="sxs-lookup"><span data-stu-id="f702f-110">Anti-aliasing can make the text appear smoother, but it can also make the display slower; to use it, set the <xref:System.Windows.Forms.PrintPreviewDialog.UseAntiAlias%2A> property to `true`.</span></span>  
  
 <span data-ttu-id="f702f-111">Alcune proprietà sono disponibili tramite il <xref:System.Windows.Forms.PrintPreviewControl> che il <xref:System.Windows.Forms.PrintPreviewDialog> contiene.</span><span class="sxs-lookup"><span data-stu-id="f702f-111">Certain properties are available through the <xref:System.Windows.Forms.PrintPreviewControl> that the <xref:System.Windows.Forms.PrintPreviewDialog> contains.</span></span> <span data-ttu-id="f702f-112">(Non è necessario aggiungere questo <xref:System.Windows.Forms.PrintPreviewControl> al form; viene automaticamente incluso all'interno di <xref:System.Windows.Forms.PrintPreviewDialog> quando si aggiunge la finestra di dialogo al form.) Esempi di proprietà disponibili tramite il <xref:System.Windows.Forms.PrintPreviewControl> sono il <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> e <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A> che determinano il numero di pagine visualizzate orizzontalmente e verticalmente il controllo.</span><span class="sxs-lookup"><span data-stu-id="f702f-112">(You do not have to add this <xref:System.Windows.Forms.PrintPreviewControl> to the form; it is automatically contained within the <xref:System.Windows.Forms.PrintPreviewDialog> when you add the dialog to your form.) Examples of properties available through the <xref:System.Windows.Forms.PrintPreviewControl> are the <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> and <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A> properties, which determine the number of pages displayed horizontally and vertically on the control.</span></span> <span data-ttu-id="f702f-113">È possibile accedere il <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> proprietà come `PrintPreviewDialog1.PrintPreviewControl.Columns` in [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)], `printPreviewDialog1.PrintPreviewControl.Columns` in [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], o `printPreviewDialog1->PrintPreviewControl->Columns` in [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f702f-113">You can access the <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> property as `PrintPreviewDialog1.PrintPreviewControl.Columns` in [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)], `printPreviewDialog1.PrintPreviewControl.Columns` in [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], or `printPreviewDialog1->PrintPreviewControl->Columns` in [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)].</span></span>  
  
## <a name="printpreviewdialog-performance"></a><span data-ttu-id="f702f-114">Prestazioni PrintPreviewDialog</span><span class="sxs-lookup"><span data-stu-id="f702f-114">PrintPreviewDialog performance</span></span>

<span data-ttu-id="f702f-115">Le condizioni seguenti, il <xref:System.Windows.Forms.PrintPreviewDialog> controllo Inizializza molto lenta:</span><span class="sxs-lookup"><span data-stu-id="f702f-115">Under the following conditions, the <xref:System.Windows.Forms.PrintPreviewDialog> control initializes very slowly:</span></span>

- <span data-ttu-id="f702f-116">Viene utilizzata una stampante di rete.</span><span class="sxs-lookup"><span data-stu-id="f702f-116">A network printer is used.</span></span>
- <span data-ttu-id="f702f-117">Le preferenze dell'utente per la stampante, ad esempio impostazioni duplex, sono state modificate.</span><span class="sxs-lookup"><span data-stu-id="f702f-117">User preferences for this printer, such as duplex settings, are modified.</span></span>
  
<span data-ttu-id="f702f-118">Per le App in esecuzione in .NET Framework 4.5.2, è possibile aggiungere la chiave seguente per il \<appSettings > della sezione del file di configurazione per migliorare le prestazioni di <xref:System.Windows.Forms.PrintPreviewDialog> controllano l'inizializzazione:</span><span class="sxs-lookup"><span data-stu-id="f702f-118">For apps running on the .NET Framework 4.5.2, you can add the following key to the \<appSettings> section of your configuration file to improve the performance of <xref:System.Windows.Forms.PrintPreviewDialog> control initialization:</span></span>

```xml
<appSettings>
   <add key="EnablePrintPreviewOptimization" value="true" />
</appSettings>
```
<span data-ttu-id="f702f-119">Se il `EnablePrintPreviewOptimization` chiave è impostata su qualsiasi altro valore, o se la chiave non è presente, l'ottimizzazione non viene applicato.</span><span class="sxs-lookup"><span data-stu-id="f702f-119">If the `EnablePrintPreviewOptimization` key is set to any other value, or if the key is not present, the optimization is not applied.</span></span>

<span data-ttu-id="f702f-120">Le applicazioni in esecuzione in .NET Framework 4.6 o in versioni successive, è possibile aggiungere la seguente opzione per il [ \<AppContextSwitchOverrides >](../../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) elemento il [ \<runtime >](../../configure-apps/file-schema/runtime/index.md) sezione del file di configurazione dell'app:</span><span class="sxs-lookup"><span data-stu-id="f702f-120">For apps running on the .NET Framework 4.6 or later versions, you can add the following switch to the [\<AppContextSwitchOverrides>](../../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element in the [\<runtime>](../../configure-apps/file-schema/runtime/index.md) section of your app config file:</span></span>

```xml
<runtime >
   <!-- AppContextSwitchOverrides values are in the form of 'key1=true|false;key2=true|false -->
   <AppContextSwitchOverrides value = "Switch.System.Drawing.Printing.OptimizePrintPreview=true" />
</runtime >
``` 
<span data-ttu-id="f702f-121">Se l'opzione non è presente o se è impostato su qualsiasi altro valore, l'ottimizzazione non viene applicato.</span><span class="sxs-lookup"><span data-stu-id="f702f-121">If the switch is not present or if it is set to any other value, the optimization is not applied.</span></span> 

<span data-ttu-id="f702f-122">Se si utilizza il <xref:System.Drawing.Printing.PrintDocument.QueryPageSettings> evento per modificare le impostazioni della stampante, le prestazioni dei <xref:System.Windows.Forms.PrintPreviewDialog> controllo non migliorerà anche se è impostata un'opzione di configurazione di ottimizzazione.</span><span class="sxs-lookup"><span data-stu-id="f702f-122">If you use the <xref:System.Drawing.Printing.PrintDocument.QueryPageSettings> event to modify printer settings, the performance of the <xref:System.Windows.Forms.PrintPreviewDialog> control will not improve even if an optimization configuration switch is set.</span></span>  

## <a name="see-also"></a><span data-ttu-id="f702f-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f702f-123">See also</span></span>  
 <xref:System.Windows.Forms.PrintPreviewDialog>  
 [<span data-ttu-id="f702f-124">Panoramica sul controllo PrintPreviewControl</span><span class="sxs-lookup"><span data-stu-id="f702f-124">PrintPreviewControl Control Overview</span></span>](../../../../docs/framework/winforms/controls/printpreviewcontrol-control-overview-windows-forms.md)  
 [<span data-ttu-id="f702f-125">Controllo PrintPreviewDialog</span><span class="sxs-lookup"><span data-stu-id="f702f-125">PrintPreviewDialog Control</span></span>](../../../../docs/framework/winforms/controls/printpreviewdialog-control-windows-forms.md)  
 [<span data-ttu-id="f702f-126">Controlli e componenti della finestra di dialogo</span><span class="sxs-lookup"><span data-stu-id="f702f-126">Dialog-Box Controls and Components</span></span>](../../../../docs/framework/winforms/controls/dialog-box-controls-and-components-windows-forms.md)
