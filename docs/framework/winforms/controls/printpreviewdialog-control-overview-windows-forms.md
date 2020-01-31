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
# <a name="printpreviewdialog-control-overview-windows-forms"></a><span data-ttu-id="212f5-102">Cenni preliminari sul controllo PrintPreviewDialog (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="212f5-102">PrintPreviewDialog control overview (Windows Forms)</span></span>

<span data-ttu-id="212f5-103">Il controllo <xref:System.Windows.Forms.PrintPreviewDialog> Windows Forms è una finestra di dialogo preconfigurata utilizzata per visualizzare la modalità di visualizzazione di un [PrintDocument](printdocument-component-windows-forms.md) quando viene stampato.</span><span class="sxs-lookup"><span data-stu-id="212f5-103">The Windows Forms <xref:System.Windows.Forms.PrintPreviewDialog> control is a pre-configured dialog box used to display how a [PrintDocument](printdocument-component-windows-forms.md) will appear when printed.</span></span> <span data-ttu-id="212f5-104">Utilizzarlo all'interno dell'applicazione basata su Windows come soluzione semplice anziché configurare la propria finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="212f5-104">Use it within your Windows-based application as a simple solution instead of configuring your own dialog box.</span></span> <span data-ttu-id="212f5-105">Il controllo contiene pulsanti per la stampa, l'ingrandimento, la visualizzazione di una o più pagine e la chiusura della finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="212f5-105">The control contains buttons for printing, zooming in, displaying one or multiple pages, and closing the dialog box.</span></span>

## <a name="key-properties-and-methods"></a><span data-ttu-id="212f5-106">Proprietà e metodi chiave</span><span class="sxs-lookup"><span data-stu-id="212f5-106">Key properties and methods</span></span>

<span data-ttu-id="212f5-107">La proprietà chiave del controllo è <xref:System.Windows.Forms.PrintPreviewDialog.Document%2A>, che imposta il documento da visualizzare in anteprima.</span><span class="sxs-lookup"><span data-stu-id="212f5-107">The control's key property is <xref:System.Windows.Forms.PrintPreviewDialog.Document%2A>, which sets the document to be previewed.</span></span> <span data-ttu-id="212f5-108">Il documento deve essere un oggetto <xref:System.Drawing.Printing.PrintDocument>.</span><span class="sxs-lookup"><span data-stu-id="212f5-108">The document must be a <xref:System.Drawing.Printing.PrintDocument> object.</span></span> <span data-ttu-id="212f5-109">Per visualizzare la finestra di dialogo, è necessario chiamare il relativo metodo <xref:System.Windows.Forms.Form.ShowDialog%2A>.</span><span class="sxs-lookup"><span data-stu-id="212f5-109">In order to display the dialog box, you must call its <xref:System.Windows.Forms.Form.ShowDialog%2A> method.</span></span> <span data-ttu-id="212f5-110">L'anti-aliasing può rendere il testo più semplice, ma può anche rendere più lenta la visualizzazione. per usarlo, impostare la proprietà <xref:System.Windows.Forms.PrintPreviewDialog.UseAntiAlias%2A> su `true`.</span><span class="sxs-lookup"><span data-stu-id="212f5-110">Anti-aliasing can make the text appear smoother, but it can also make the display slower; to use it, set the <xref:System.Windows.Forms.PrintPreviewDialog.UseAntiAlias%2A> property to `true`.</span></span>

<span data-ttu-id="212f5-111">Alcune proprietà sono disponibili tramite il <xref:System.Windows.Forms.PrintPreviewControl> contenuto nel <xref:System.Windows.Forms.PrintPreviewDialog>.</span><span class="sxs-lookup"><span data-stu-id="212f5-111">Certain properties are available through the <xref:System.Windows.Forms.PrintPreviewControl> that the <xref:System.Windows.Forms.PrintPreviewDialog> contains.</span></span> <span data-ttu-id="212f5-112">Non è necessario aggiungere questo <xref:System.Windows.Forms.PrintPreviewControl> al modulo. viene automaticamente contenuto all'interno del <xref:System.Windows.Forms.PrintPreviewDialog> quando si aggiunge la finestra di dialogo al form. Esempi di proprietà disponibili tramite il <xref:System.Windows.Forms.PrintPreviewControl> sono le proprietà <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> e <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A>, che determinano il numero di pagine visualizzate orizzontalmente e verticalmente sul controllo.</span><span class="sxs-lookup"><span data-stu-id="212f5-112">(You do not have to add this <xref:System.Windows.Forms.PrintPreviewControl> to the form; it is automatically contained within the <xref:System.Windows.Forms.PrintPreviewDialog> when you add the dialog to your form.) Examples of properties available through the <xref:System.Windows.Forms.PrintPreviewControl> are the <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> and <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A> properties, which determine the number of pages displayed horizontally and vertically on the control.</span></span> <span data-ttu-id="212f5-113">È possibile accedere alla proprietà <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> come `PrintPreviewDialog1.PrintPreviewControl.Columns` in Visual Basic, `printPreviewDialog1.PrintPreviewControl.Columns` in Visual C#o `printPreviewDialog1->PrintPreviewControl->Columns` in Visual C++.</span><span class="sxs-lookup"><span data-stu-id="212f5-113">You can access the <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> property as `PrintPreviewDialog1.PrintPreviewControl.Columns` in Visual Basic, `printPreviewDialog1.PrintPreviewControl.Columns` in Visual C#, or `printPreviewDialog1->PrintPreviewControl->Columns` in Visual C++.</span></span>

## <a name="printpreviewdialog-performance"></a><span data-ttu-id="212f5-114">Prestazioni di PrintPreviewDialog</span><span class="sxs-lookup"><span data-stu-id="212f5-114">PrintPreviewDialog performance</span></span>

<span data-ttu-id="212f5-115">Nelle condizioni seguenti, il controllo <xref:System.Windows.Forms.PrintPreviewDialog> viene inizializzato molto lentamente:</span><span class="sxs-lookup"><span data-stu-id="212f5-115">Under the following conditions, the <xref:System.Windows.Forms.PrintPreviewDialog> control initializes very slowly:</span></span>

- <span data-ttu-id="212f5-116">Viene utilizzata una stampante di rete.</span><span class="sxs-lookup"><span data-stu-id="212f5-116">A network printer is used.</span></span>
- <span data-ttu-id="212f5-117">Vengono modificate le preferenze utente per questa stampante, ad esempio le impostazioni duplex.</span><span class="sxs-lookup"><span data-stu-id="212f5-117">User preferences for this printer, such as duplex settings, are modified.</span></span>

<span data-ttu-id="212f5-118">Per le app in esecuzione nel .NET Framework 4.5.2, è possibile aggiungere la chiave seguente alla sezione \<appSettings > del file di configurazione per migliorare le prestazioni dell'inizializzazione del controllo <xref:System.Windows.Forms.PrintPreviewDialog>:</span><span class="sxs-lookup"><span data-stu-id="212f5-118">For apps running on the .NET Framework 4.5.2, you can add the following key to the \<appSettings> section of your configuration file to improve the performance of <xref:System.Windows.Forms.PrintPreviewDialog> control initialization:</span></span>

```xml
<appSettings>
   <add key="EnablePrintPreviewOptimization" value="true" />
</appSettings>
```

<span data-ttu-id="212f5-119">Se la chiave di `EnablePrintPreviewOptimization` è impostata su qualsiasi altro valore o se la chiave non è presente, l'ottimizzazione non viene applicata.</span><span class="sxs-lookup"><span data-stu-id="212f5-119">If the `EnablePrintPreviewOptimization` key is set to any other value, or if the key is not present, the optimization is not applied.</span></span>

<span data-ttu-id="212f5-120">Per le app in esecuzione in .NET Framework 4,6 o versioni successive, è possibile aggiungere l'opzione seguente all'elemento [\<AppContextSwitchOverrides](../../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) nella sezione [\<Runtime >](../../configure-apps/file-schema/runtime/index.md) del file di configurazione dell'app:</span><span class="sxs-lookup"><span data-stu-id="212f5-120">For apps running on the .NET Framework 4.6 or later versions, you can add the following switch to the [\<AppContextSwitchOverrides>](../../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element in the [\<runtime>](../../configure-apps/file-schema/runtime/index.md) section of your app config file:</span></span>

```xml
<runtime >
   <!-- AppContextSwitchOverrides values are in the form of 'key1=true|false;key2=true|false -->
   <AppContextSwitchOverrides value = "Switch.System.Drawing.Printing.OptimizePrintPreview=true" />
</runtime >
```

<span data-ttu-id="212f5-121">Se l'opzione non è presente o è impostata su un altro valore, l'ottimizzazione non viene applicata.</span><span class="sxs-lookup"><span data-stu-id="212f5-121">If the switch is not present or if it is set to any other value, the optimization is not applied.</span></span>

<span data-ttu-id="212f5-122">Se si utilizza l'evento <xref:System.Drawing.Printing.PrintDocument.QueryPageSettings> per modificare le impostazioni della stampante, le prestazioni del controllo <xref:System.Windows.Forms.PrintPreviewDialog> non miglioreranno anche se è impostata un'opzione di configurazione dell'ottimizzazione.</span><span class="sxs-lookup"><span data-stu-id="212f5-122">If you use the <xref:System.Drawing.Printing.PrintDocument.QueryPageSettings> event to modify printer settings, the performance of the <xref:System.Windows.Forms.PrintPreviewDialog> control will not improve even if an optimization configuration switch is set.</span></span>

## <a name="see-also"></a><span data-ttu-id="212f5-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="212f5-123">See also</span></span>

- <xref:System.Windows.Forms.PrintPreviewDialog>
- [<span data-ttu-id="212f5-124">Panoramica sul controllo PrintPreviewControl</span><span class="sxs-lookup"><span data-stu-id="212f5-124">PrintPreviewControl Control Overview</span></span>](printpreviewcontrol-control-overview-windows-forms.md)
- [<span data-ttu-id="212f5-125">Controllo PrintPreviewDialog</span><span class="sxs-lookup"><span data-stu-id="212f5-125">PrintPreviewDialog Control</span></span>](printpreviewdialog-control-windows-forms.md)
- [<span data-ttu-id="212f5-126">Controlli e componenti della finestra di dialogo</span><span class="sxs-lookup"><span data-stu-id="212f5-126">Dialog-Box Controls and Components</span></span>](dialog-box-controls-and-components-windows-forms.md)
