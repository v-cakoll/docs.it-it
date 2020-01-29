---
title: Controlli Windows Form e controlli WPF equivalenti
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms [WPF], interoperability with
- Windows Forms [WPF], WPF interoperation
- interoperability [WPF], Windows Forms
ms.assetid: 8a157e6b-8054-46db-a5cf-a78966acc7a1
ms.openlocfilehash: 7f531b60d8b31181688f3d0a6753b234ffc6c7dd
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76735214"
---
# <a name="windows-forms-controls-and-equivalent-wpf-controls"></a><span data-ttu-id="f74d7-102">Controlli Windows Form e controlli WPF equivalenti</span><span class="sxs-lookup"><span data-stu-id="f74d7-102">Windows Forms Controls and Equivalent WPF Controls</span></span>
<span data-ttu-id="f74d7-103">Molti controlli [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] hanno controlli [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] equivalenti, ma alcuni controlli [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] non hanno equivalenti in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f74d7-103">Many [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls have equivalent [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] controls, but some [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls have no equivalents in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span></span> <span data-ttu-id="f74d7-104">In questo argomento vengono confrontati i tipi di controllo forniti dalle due tecnologie.</span><span class="sxs-lookup"><span data-stu-id="f74d7-104">This topic compares control types provided by the two technologies.</span></span>  
  
 <span data-ttu-id="f74d7-105">È sempre possibile usare l'interoperatività per ospitare [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controlli che non hanno equivalenti nelle applicazioni basate su [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f74d7-105">You can always use interoperation to host [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls that do not have equivalents in your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based applications.</span></span>  
  
 <span data-ttu-id="f74d7-106">Nella tabella seguente vengono illustrati i controlli [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] e i componenti con funzionalità di controllo [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] equivalenti.</span><span class="sxs-lookup"><span data-stu-id="f74d7-106">The following table shows which [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls and components have equivalent [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] control functionality.</span></span>  
  
|<span data-ttu-id="f74d7-107">controllo Windows Form</span><span class="sxs-lookup"><span data-stu-id="f74d7-107">Windows Forms control</span></span>|<span data-ttu-id="f74d7-108">Controllo equivalente WPF</span><span class="sxs-lookup"><span data-stu-id="f74d7-108">WPF equivalent control</span></span>|<span data-ttu-id="f74d7-109">Note</span><span class="sxs-lookup"><span data-stu-id="f74d7-109">Remarks</span></span>|  
|---------------------------|----------------------------|-------------|  
|<xref:System.Windows.Forms.BindingNavigator>|<span data-ttu-id="f74d7-110">Nessun controllo equivalente.</span><span class="sxs-lookup"><span data-stu-id="f74d7-110">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.BindingSource>|<xref:System.Windows.Data.CollectionViewSource>||  
|<xref:System.Windows.Forms.Button>|<xref:System.Windows.Controls.Button>||  
|<xref:System.Windows.Forms.CheckBox>|<xref:System.Windows.Controls.CheckBox>||  
|<xref:System.Windows.Forms.CheckedListBox>|<span data-ttu-id="f74d7-111"><xref:System.Windows.Controls.ListBox> con Composition.</span><span class="sxs-lookup"><span data-stu-id="f74d7-111"><xref:System.Windows.Controls.ListBox> with composition.</span></span>||  
|<xref:System.Windows.Forms.ColorDialog>|<span data-ttu-id="f74d7-112">Nessun controllo equivalente.</span><span class="sxs-lookup"><span data-stu-id="f74d7-112">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.ComboBox>|<xref:System.Windows.Controls.ComboBox>|<span data-ttu-id="f74d7-113"><xref:System.Windows.Controls.ComboBox> non supporta il completamento automatico.</span><span class="sxs-lookup"><span data-stu-id="f74d7-113"><xref:System.Windows.Controls.ComboBox> does not support auto-complete.</span></span>|  
|<xref:System.Windows.Forms.ContextMenuStrip>|<xref:System.Windows.Controls.ContextMenu>||  
|<xref:System.Windows.Forms.DataGridView>|<xref:System.Windows.Controls.DataGrid>||  
|<xref:System.Windows.Forms.DateTimePicker>|<xref:System.Windows.Controls.DatePicker>||  
|<xref:System.Windows.Forms.DomainUpDown>|<span data-ttu-id="f74d7-114"><xref:System.Windows.Controls.TextBox> e due controlli <xref:System.Windows.Controls.Primitives.RepeatButton>.</span><span class="sxs-lookup"><span data-stu-id="f74d7-114"><xref:System.Windows.Controls.TextBox> and two <xref:System.Windows.Controls.Primitives.RepeatButton> controls.</span></span>||  
|<xref:System.Windows.Forms.ErrorProvider>|<span data-ttu-id="f74d7-115">Nessun controllo equivalente.</span><span class="sxs-lookup"><span data-stu-id="f74d7-115">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.FlowLayoutPanel>|<span data-ttu-id="f74d7-116"><xref:System.Windows.Controls.WrapPanel> o <xref:System.Windows.Controls.StackPanel></span><span class="sxs-lookup"><span data-stu-id="f74d7-116"><xref:System.Windows.Controls.WrapPanel> or <xref:System.Windows.Controls.StackPanel></span></span>||  
|<xref:System.Windows.Forms.FolderBrowserDialog>|<span data-ttu-id="f74d7-117">Nessun controllo equivalente.</span><span class="sxs-lookup"><span data-stu-id="f74d7-117">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.FontDialog>|<span data-ttu-id="f74d7-118">Nessun controllo equivalente.</span><span class="sxs-lookup"><span data-stu-id="f74d7-118">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.Form>|<xref:System.Windows.Window>|<span data-ttu-id="f74d7-119"><xref:System.Windows.Window> non supporta le finestre figlio.</span><span class="sxs-lookup"><span data-stu-id="f74d7-119"><xref:System.Windows.Window> does not support child windows.</span></span>|  
|<xref:System.Windows.Forms.GroupBox>|<xref:System.Windows.Controls.GroupBox>||  
|<xref:System.Windows.Forms.HelpProvider>|<span data-ttu-id="f74d7-120">Nessun controllo equivalente.</span><span class="sxs-lookup"><span data-stu-id="f74d7-120">No equivalent control.</span></span>|<span data-ttu-id="f74d7-121">Nessuna Guida sensibile al contesto.</span><span class="sxs-lookup"><span data-stu-id="f74d7-121">No F1 Help.</span></span> <span data-ttu-id="f74d7-122">La guida "cosa è questo" è stata sostituita dalle descrizioni comandi.</span><span class="sxs-lookup"><span data-stu-id="f74d7-122">"What's This" Help is replaced by ToolTips.</span></span>|  
|<xref:System.Windows.Forms.HScrollBar>|<xref:System.Windows.Controls.Primitives.ScrollBar>|<span data-ttu-id="f74d7-123">Lo scorrimento è incorporato nei controlli contenitore.</span><span class="sxs-lookup"><span data-stu-id="f74d7-123">Scrolling is built into container controls.</span></span>|  
|<xref:System.Windows.Forms.ImageList>|<span data-ttu-id="f74d7-124">Nessun controllo equivalente.</span><span class="sxs-lookup"><span data-stu-id="f74d7-124">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.Label>|<xref:System.Windows.Controls.Label>||  
|<xref:System.Windows.Forms.LinkLabel>|<span data-ttu-id="f74d7-125">Nessun controllo equivalente.</span><span class="sxs-lookup"><span data-stu-id="f74d7-125">No equivalent control.</span></span>|<span data-ttu-id="f74d7-126">È possibile usare la classe <xref:System.Windows.Documents.Hyperlink> per ospitare collegamenti ipertestuali all'interno del contenuto del flusso.</span><span class="sxs-lookup"><span data-stu-id="f74d7-126">You can use the <xref:System.Windows.Documents.Hyperlink> class to host hyperlinks within flow content.</span></span>|  
|<xref:System.Windows.Forms.ListBox>|<xref:System.Windows.Controls.ListBox>||  
|<xref:System.Windows.Forms.ListView>|<xref:System.Windows.Controls.ListView>|<span data-ttu-id="f74d7-127">Il controllo <xref:System.Windows.Controls.ListView> fornisce una visualizzazione dettagli di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="f74d7-127">The <xref:System.Windows.Controls.ListView> control provides a read-only details view.</span></span>|  
|<xref:System.Windows.Forms.MaskedTextBox>|<span data-ttu-id="f74d7-128">Nessun controllo equivalente.</span><span class="sxs-lookup"><span data-stu-id="f74d7-128">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.MenuStrip>|<xref:System.Windows.Controls.Menu>|<span data-ttu-id="f74d7-129"><xref:System.Windows.Controls.Menu> stile del controllo può approssimare il comportamento e l'aspetto della classe <xref:System.Windows.Forms.ToolStripProfessionalRenderer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f74d7-129"><xref:System.Windows.Controls.Menu> control styling can approximate the behavior and appearance of the <xref:System.Windows.Forms.ToolStripProfessionalRenderer?displayProperty=nameWithType> class.</span></span>|  
|<xref:System.Windows.Forms.MonthCalendar>|<xref:System.Windows.Controls.Calendar>||  
|<xref:System.Windows.Forms.NotifyIcon>|<span data-ttu-id="f74d7-130">Nessun controllo equivalente.</span><span class="sxs-lookup"><span data-stu-id="f74d7-130">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.NumericUpDown>|<span data-ttu-id="f74d7-131"><xref:System.Windows.Controls.TextBox> e due controlli <xref:System.Windows.Controls.Primitives.RepeatButton>.</span><span class="sxs-lookup"><span data-stu-id="f74d7-131"><xref:System.Windows.Controls.TextBox> and two <xref:System.Windows.Controls.Primitives.RepeatButton> controls.</span></span>||  
|<xref:System.Windows.Forms.OpenFileDialog>|<xref:Microsoft.Win32.OpenFileDialog>|<span data-ttu-id="f74d7-132">La classe <xref:Microsoft.Win32.OpenFileDialog> è un wrapper [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] intorno al controllo Win32.</span><span class="sxs-lookup"><span data-stu-id="f74d7-132">The <xref:Microsoft.Win32.OpenFileDialog> class is a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] wrapper around the Win32 control.</span></span>|  
|<xref:System.Windows.Forms.PageSetupDialog>|<span data-ttu-id="f74d7-133">Nessun controllo equivalente.</span><span class="sxs-lookup"><span data-stu-id="f74d7-133">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.Panel>|<xref:System.Windows.Controls.Canvas>||  
|<xref:System.Windows.Forms.PictureBox>|<xref:System.Windows.Controls.Image>||  
|<xref:System.Windows.Forms.PrintDialog>|<xref:System.Windows.Controls.PrintDialog>||  
|<xref:System.Drawing.Printing.PrintDocument>|<span data-ttu-id="f74d7-134">Nessun controllo equivalente.</span><span class="sxs-lookup"><span data-stu-id="f74d7-134">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.PrintPreviewControl>|<xref:System.Windows.Controls.DocumentViewer>||  
|<xref:System.Windows.Forms.PrintPreviewDialog>|<span data-ttu-id="f74d7-135">Nessun controllo equivalente.</span><span class="sxs-lookup"><span data-stu-id="f74d7-135">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.ProgressBar>|<xref:System.Windows.Controls.ProgressBar>||  
|<xref:System.Windows.Forms.PropertyGrid>|<span data-ttu-id="f74d7-136">Nessun controllo equivalente.</span><span class="sxs-lookup"><span data-stu-id="f74d7-136">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.RadioButton>|<xref:System.Windows.Controls.RadioButton>||  
|<xref:System.Windows.Forms.RichTextBox>|<xref:System.Windows.Controls.RichTextBox>||  
|<xref:System.Windows.Forms.SaveFileDialog>|<xref:Microsoft.Win32.SaveFileDialog>|<span data-ttu-id="f74d7-137">La classe <xref:Microsoft.Win32.SaveFileDialog> è un wrapper [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] intorno al controllo Win32.</span><span class="sxs-lookup"><span data-stu-id="f74d7-137">The <xref:Microsoft.Win32.SaveFileDialog> class is a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] wrapper around the Win32 control.</span></span>|  
|<xref:System.Windows.Forms.ScrollableControl>|<xref:System.Windows.Controls.ScrollViewer>||  
|<xref:System.Media.SoundPlayer>|<xref:System.Windows.Media.MediaPlayer>||  
|<xref:System.Windows.Forms.SplitContainer>|<xref:System.Windows.Controls.GridSplitter>||  
|<xref:System.Windows.Forms.StatusStrip>|<xref:System.Windows.Controls.Primitives.StatusBar>||  
|<xref:System.Windows.Forms.TabControl>|<xref:System.Windows.Controls.TabControl>||  
|<xref:System.Windows.Forms.TableLayoutPanel>|<xref:System.Windows.Controls.Grid>||  
|<xref:System.Windows.Forms.TextBox>|<xref:System.Windows.Controls.TextBox>||  
|<xref:System.Windows.Forms.Timer>|<xref:System.Windows.Threading.DispatcherTimer>||  
|<xref:System.Windows.Forms.ToolStrip>|<xref:System.Windows.Controls.ToolBar>||  
|<xref:System.Windows.Forms.ToolStripContainer>|<span data-ttu-id="f74d7-138"><xref:System.Windows.Controls.ToolBar> con Composition.</span><span class="sxs-lookup"><span data-stu-id="f74d7-138"><xref:System.Windows.Controls.ToolBar> with composition.</span></span>||  
|<xref:System.Windows.Forms.ToolStripDropDown>|<span data-ttu-id="f74d7-139"><xref:System.Windows.Controls.ToolBar> con Composition.</span><span class="sxs-lookup"><span data-stu-id="f74d7-139"><xref:System.Windows.Controls.ToolBar> with composition.</span></span>||  
|<xref:System.Windows.Forms.ToolStripDropDownMenu>|<span data-ttu-id="f74d7-140"><xref:System.Windows.Controls.ToolBar> con Composition.</span><span class="sxs-lookup"><span data-stu-id="f74d7-140"><xref:System.Windows.Controls.ToolBar> with composition.</span></span>||  
|<xref:System.Windows.Forms.ToolStripPanel>|<span data-ttu-id="f74d7-141"><xref:System.Windows.Controls.ToolBar> con Composition.</span><span class="sxs-lookup"><span data-stu-id="f74d7-141"><xref:System.Windows.Controls.ToolBar> with composition.</span></span>||  
|<xref:System.Windows.Forms.ToolTip>|<xref:System.Windows.Controls.ToolTip>||  
|<xref:System.Windows.Forms.TrackBar>|<xref:System.Windows.Controls.Slider>||  
|<xref:System.Windows.Forms.TreeView>|<xref:System.Windows.Controls.TreeView>||  
|<xref:System.Windows.Forms.UserControl>|<xref:System.Windows.Controls.UserControl>||  
|<xref:System.Windows.Forms.VScrollBar>|<xref:System.Windows.Controls.Primitives.ScrollBar>|<span data-ttu-id="f74d7-142">Lo scorrimento è incorporato nei controlli contenitore.</span><span class="sxs-lookup"><span data-stu-id="f74d7-142">Scrolling is built into container controls.</span></span>|  
|<xref:System.Windows.Forms.WebBrowser>|<span data-ttu-id="f74d7-143"><xref:System.Windows.Controls.Frame>, <xref:System.Windows.Controls.WebBrowser?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="f74d7-143"><xref:System.Windows.Controls.Frame>, <xref:System.Windows.Controls.WebBrowser?displayProperty=nameWithType></span></span>|<span data-ttu-id="f74d7-144">Il controllo <xref:System.Windows.Controls.Frame> può ospitare pagine HTML.</span><span class="sxs-lookup"><span data-stu-id="f74d7-144">The <xref:System.Windows.Controls.Frame> control can host HTML pages.</span></span><br /><br /> <span data-ttu-id="f74d7-145">A partire da .NET Framework 3,5 SP1, il controllo <xref:System.Windows.Controls.WebBrowser?displayProperty=nameWithType> può ospitare pagine HTML ed eseguire il backup anche del controllo <xref:System.Windows.Controls.Frame>.</span><span class="sxs-lookup"><span data-stu-id="f74d7-145">Starting in the .NET Framework 3.5 SP1, the <xref:System.Windows.Controls.WebBrowser?displayProperty=nameWithType> control can host HTML pages and also backs the <xref:System.Windows.Controls.Frame> control.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f74d7-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f74d7-146">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- <span data-ttu-id="f74d7-147">[Progettazione WPF per sviluppatori Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/cc165605(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="f74d7-147">[WPF Designer for Windows Forms Developers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/cc165605(v=vs.100))</span></span>
- [<span data-ttu-id="f74d7-148">Procedura dettagliata: hosting di controlli Windows Form in WPF</span><span class="sxs-lookup"><span data-stu-id="f74d7-148">Walkthrough: Hosting a Windows Forms Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
- [<span data-ttu-id="f74d7-149">Procedura dettaglia: hosting di un controllo WPF composito in Windows Form</span><span class="sxs-lookup"><span data-stu-id="f74d7-149">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [<span data-ttu-id="f74d7-150">Migrazione e interoperabilità</span><span class="sxs-lookup"><span data-stu-id="f74d7-150">Migration and Interoperability</span></span>](migration-and-interoperability.md)
