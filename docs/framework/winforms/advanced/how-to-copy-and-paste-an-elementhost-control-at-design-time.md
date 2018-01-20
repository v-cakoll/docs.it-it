---
title: 'Procedura: copiare e incollare un controllo ElementHost in fase di progettazione'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms, content copying and pasting
- interoperability [WPF]
- ElementHost control [Windows Forms], copying and pasting at design time
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: e570375d-2a68-44ba-b4f7-c781af2d20e8
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2ab87761167c19ee0fe78d33edcfe8662d90e36a
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-copy-and-paste-an-elementhost-control-at-design-time"></a><span data-ttu-id="8c31d-102">Procedura: copiare e incollare un controllo ElementHost in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="8c31d-102">How to: Copy and Paste an ElementHost Control at Design Time</span></span>
<span data-ttu-id="8c31d-103">Questa procedura viene illustrato come copiare un controllo Windows Presentation Foundation (WPF) in un Windows Form.</span><span class="sxs-lookup"><span data-stu-id="8c31d-103">This procedure shows you how to copy a Windows Presentation Foundation (WPF) control on a Windows Form.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8c31d-104">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="8c31d-104">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="8c31d-105">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="8c31d-105">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="8c31d-106">Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="8c31d-106">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-copy-and-paste-an-elementhost-control-at-design-time"></a><span data-ttu-id="8c31d-107">Copiare e incollare un controllo ElementHost in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="8c31d-107">To copy and paste an ElementHost control at design time</span></span>  
  
1.  <span data-ttu-id="8c31d-108">Aggiungere un nuovo controllo WPF <xref:System.Windows.Controls.UserControl> al progetto Windows Form.</span><span class="sxs-lookup"><span data-stu-id="8c31d-108">Add a new WPF <xref:System.Windows.Controls.UserControl> to your Windows Forms project.</span></span> <span data-ttu-id="8c31d-109">Usare il nome predefinito per il tipo di controllo, `UserControl1.xaml`.</span><span class="sxs-lookup"><span data-stu-id="8c31d-109">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="8c31d-110">Per ulteriori informazioni, vedere [procedura dettagliata: creazione di nuovo contenuto WPF in Windows Form in fase di progettazione](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span><span class="sxs-lookup"><span data-stu-id="8c31d-110">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>  
  
2.  <span data-ttu-id="8c31d-111">Nel **proprietà** finestra, impostare il valore della <xref:System.Windows.FrameworkElement.Width%2A> e <xref:System.Windows.FrameworkElement.Height%2A> le proprietà di `UserControl1` a `200`.</span><span class="sxs-lookup"><span data-stu-id="8c31d-111">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties of `UserControl1` to `200`.</span></span>  
  
3.  <span data-ttu-id="8c31d-112">Impostare il valore della proprietà <xref:System.Windows.Controls.Control.Background%2A> su `Blue`.</span><span class="sxs-lookup"><span data-stu-id="8c31d-112">Set the value of the <xref:System.Windows.Controls.Control.Background%2A> property to `Blue`.</span></span>  
  
4.  <span data-ttu-id="8c31d-113">Compilare il progetto.</span><span class="sxs-lookup"><span data-stu-id="8c31d-113">Build the project.</span></span>  
  
5.  <span data-ttu-id="8c31d-114">Aprire `Form1` in Progettazione Windows Form.</span><span class="sxs-lookup"><span data-stu-id="8c31d-114">Open `Form1` in the Windows Forms Designer.</span></span>  
  
6.  <span data-ttu-id="8c31d-115">Dal **della casella degli strumenti**, trascinare un'istanza di `UserControl1` nel form.</span><span class="sxs-lookup"><span data-stu-id="8c31d-115">From the **Toolbox**, drag an instance of `UserControl1` onto the form.</span></span>  
  
     <span data-ttu-id="8c31d-116">L'istanza di `UserControl1` viene inclusa in un nuovo controllo <xref:System.Windows.Forms.Integration.ElementHost> denominato `elementHost1`.</span><span class="sxs-lookup"><span data-stu-id="8c31d-116">An instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>  
  
7.  <span data-ttu-id="8c31d-117">Con `elementHost1` selezionato, premere CTRL+C per copiarlo negli Appunti.</span><span class="sxs-lookup"><span data-stu-id="8c31d-117">With `elementHost1` selected, press CTRL+C to copy it to the clipboard.</span></span>  
  
8.  <span data-ttu-id="8c31d-118">Premere CTRL + V per incollare il controllo copiato nel form.</span><span class="sxs-lookup"><span data-stu-id="8c31d-118">Press CTRL+V to paste the copied control onto the form.</span></span>  
  
     <span data-ttu-id="8c31d-119">Un nuovo <xref:System.Windows.Forms.Integration.ElementHost> controllo denominato `elementHost2` viene creata nel form.</span><span class="sxs-lookup"><span data-stu-id="8c31d-119">A new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost2` is created on the form.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c31d-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8c31d-120">See Also</span></span>  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [<span data-ttu-id="8c31d-121">Procedura dettagliata: Copiare e incollare un controllo ElementHost in Windows Form separati</span><span class="sxs-lookup"><span data-stu-id="8c31d-121">Walkthrough: Copying and Pasting an ElementHost Control into Separate Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/copy--paste-an-elementhost-control-into-forms.md)  
 [<span data-ttu-id="8c31d-122">Migrazione e interoperabilità</span><span class="sxs-lookup"><span data-stu-id="8c31d-122">Migration and Interoperability</span></span>](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)  
 [<span data-ttu-id="8c31d-123">Uso di controlli WPF</span><span class="sxs-lookup"><span data-stu-id="8c31d-123">Using WPF Controls</span></span>](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)  
 [<span data-ttu-id="8c31d-124">WPF Designer</span><span class="sxs-lookup"><span data-stu-id="8c31d-124">WPF Designer</span></span>](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)
