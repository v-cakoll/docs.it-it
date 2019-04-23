---
title: Controlli Windows Form e controlli WPF equivalenti
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms [WPF], interoperability with
- Windows Forms [WPF], WPF interoperation
- interoperability [WPF], Windows Forms
ms.assetid: 8a157e6b-8054-46db-a5cf-a78966acc7a1
ms.openlocfilehash: abfcb9f5398a6a8d264985543df585bea93a0446
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59075275"
---
# <a name="windows-forms-controls-and-equivalent-wpf-controls"></a><span data-ttu-id="cd1fe-102">Controlli Windows Form e controlli WPF equivalenti</span><span class="sxs-lookup"><span data-stu-id="cd1fe-102">Windows Forms Controls and Equivalent WPF Controls</span></span>
<span data-ttu-id="cd1fe-103">Molte [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controlli dispongono di equivalenti [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] controlli, ma alcuni [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controlli non dispongono di equivalenti [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cd1fe-103">Many [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls have equivalent [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] controls, but some [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls have no equivalents in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span></span> <span data-ttu-id="cd1fe-104">In questo argomento Confronta i tipi di controllo forniti da due tecnologie.</span><span class="sxs-lookup"><span data-stu-id="cd1fe-104">This topic compares control types provided by the two technologies.</span></span>  
  
 <span data-ttu-id="cd1fe-105">È sempre possibile usare l'interoperatività per ospitare [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] i controlli che non dispongono di equivalenti nel [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-applicazioni basate su.</span><span class="sxs-lookup"><span data-stu-id="cd1fe-105">You can always use interoperation to host [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls that do not have equivalents in your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based applications.</span></span>  
  
 <span data-ttu-id="cd1fe-106">Nella tabella seguente viene illustrato quale [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] componenti e controlli dispongono di equivalenti [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] controllano le funzionalità.</span><span class="sxs-lookup"><span data-stu-id="cd1fe-106">The following table shows which [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls and components have equivalent [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] control functionality.</span></span>  
  
|<span data-ttu-id="cd1fe-107">controllo Windows Form</span><span class="sxs-lookup"><span data-stu-id="cd1fe-107">Windows Forms control</span></span>|<span data-ttu-id="cd1fe-108">Controlli equivalenti di WPF</span><span class="sxs-lookup"><span data-stu-id="cd1fe-108">WPF equivalent control</span></span>|<span data-ttu-id="cd1fe-109">Note</span><span class="sxs-lookup"><span data-stu-id="cd1fe-109">Remarks</span></span>|  
|---------------------------|----------------------------|-------------|  
|<xref:System.Windows.Forms.BindingNavigator>|<span data-ttu-id="cd1fe-110">Nessun controllo equivalente.</span><span class="sxs-lookup"><span data-stu-id="cd1fe-110">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.BindingSource>|<xref:System.Windows.Data.CollectionViewSource>||  
|<xref:System.Windows.Forms.Button>|<xref:System.Windows.Controls.Button>||  
|<xref:System.Windows.Forms.CheckBox>|<xref:System.Windows.Controls.CheckBox>||  
|<xref:System.Windows.Forms.CheckedListBox>|<span data-ttu-id="cd1fe-111"><xref:System.Windows.Controls.ListBox> con composizione.</span><span class="sxs-lookup"><span data-stu-id="cd1fe-111"><xref:System.Windows.Controls.ListBox> with composition.</span></span>||  
|<xref:System.Windows.Forms.ColorDialog>|<span data-ttu-id="cd1fe-112">Nessun controllo equivalente.</span><span class="sxs-lookup"><span data-stu-id="cd1fe-112">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.ComboBox>|<xref:System.Windows.Controls.ComboBox>|<span data-ttu-id="cd1fe-113"><xref:System.Windows.Controls.ComboBox> non supporta il completamento automatico.</span><span class="sxs-lookup"><span data-stu-id="cd1fe-113"><xref:System.Windows.Controls.ComboBox> does not support auto-complete.</span></span>|  
|<xref:System.Windows.Forms.ContextMenuStrip>|<xref:System.Windows.Controls.ContextMenu>||  
|<xref:System.Windows.Forms.DataGridView>|<xref:System.Windows.Controls.DataGrid>||  
|<xref:System.Windows.Forms.DateTimePicker>|<xref:System.Windows.Controls.DatePicker>||  
|<xref:System.Windows.Forms.DomainUpDown>|<span data-ttu-id="cd1fe-114"><xref:System.Windows.Controls.TextBox> e due <xref:System.Windows.Controls.Primitives.RepeatButton> controlli.</span><span class="sxs-lookup"><span data-stu-id="cd1fe-114"><xref:System.Windows.Controls.TextBox> and two <xref:System.Windows.Controls.Primitives.RepeatButton> controls.</span></span>||  
|<xref:System.Windows.Forms.ErrorProvider>|<span data-ttu-id="cd1fe-115">Nessun controllo equivalente.</span><span class="sxs-lookup"><span data-stu-id="cd1fe-115">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.FlowLayoutPanel>|<span data-ttu-id="cd1fe-116"><xref:System.Windows.Controls.WrapPanel> o <xref:System.Windows.Controls.StackPanel></span><span class="sxs-lookup"><span data-stu-id="cd1fe-116"><xref:System.Windows.Controls.WrapPanel> or <xref:System.Windows.Controls.StackPanel></span></span>||  
|<xref:System.Windows.Forms.FolderBrowserDialog>|<span data-ttu-id="cd1fe-117">Nessun controllo equivalente.</span><span class="sxs-lookup"><span data-stu-id="cd1fe-117">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.FontDialog>|<span data-ttu-id="cd1fe-118">Nessun controllo equivalente.</span><span class="sxs-lookup"><span data-stu-id="cd1fe-118">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.Form>|<xref:System.Windows.Window>|<span data-ttu-id="cd1fe-119"><xref:System.Windows.Window> non supporta le finestre figlio.</span><span class="sxs-lookup"><span data-stu-id="cd1fe-119"><xref:System.Windows.Window> does not support child windows.</span></span>|  
|<xref:System.Windows.Forms.GroupBox>|<xref:System.Windows.Controls.GroupBox>||  
|<xref:System.Windows.Forms.HelpProvider>|<span data-ttu-id="cd1fe-120">Nessun controllo equivalente.</span><span class="sxs-lookup"><span data-stu-id="cd1fe-120">No equivalent control.</span></span>|<span data-ttu-id="cd1fe-121">Nessuna Guida F1.</span><span class="sxs-lookup"><span data-stu-id="cd1fe-121">No F1 Help.</span></span> <span data-ttu-id="cd1fe-122">"Che cos'è questa" della Guida in linea viene sostituito dalle descrizioni comandi.</span><span class="sxs-lookup"><span data-stu-id="cd1fe-122">"What's This" Help is replaced by ToolTips.</span></span>|  
|<xref:System.Windows.Forms.HScrollBar>|<xref:System.Windows.Controls.Primitives.ScrollBar>|<span data-ttu-id="cd1fe-123">Lo scorrimento è incorporato in controlli contenitore.</span><span class="sxs-lookup"><span data-stu-id="cd1fe-123">Scrolling is built into container controls.</span></span>|  
|<xref:System.Windows.Forms.ImageList>|<span data-ttu-id="cd1fe-124">Nessun controllo equivalente.</span><span class="sxs-lookup"><span data-stu-id="cd1fe-124">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.Label>|<xref:System.Windows.Controls.Label>||  
|<xref:System.Windows.Forms.LinkLabel>|<span data-ttu-id="cd1fe-125">Nessun controllo equivalente.</span><span class="sxs-lookup"><span data-stu-id="cd1fe-125">No equivalent control.</span></span>|<span data-ttu-id="cd1fe-126">È possibile usare il <xref:System.Windows.Documents.Hyperlink> classe ospitare collegamenti ipertestuali all'interno del contenuto del flusso.</span><span class="sxs-lookup"><span data-stu-id="cd1fe-126">You can use the <xref:System.Windows.Documents.Hyperlink> class to host hyperlinks within flow content.</span></span>|  
|<xref:System.Windows.Forms.ListBox>|<xref:System.Windows.Controls.ListBox>||  
|<xref:System.Windows.Forms.ListView>|<xref:System.Windows.Controls.ListView>|<span data-ttu-id="cd1fe-127">Il <xref:System.Windows.Controls.ListView> controllo fornisce una visualizzazione dei dettagli di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="cd1fe-127">The <xref:System.Windows.Controls.ListView> control provides a read-only details view.</span></span>|  
|<xref:System.Windows.Forms.MaskedTextBox>|<span data-ttu-id="cd1fe-128">Nessun controllo equivalente.</span><span class="sxs-lookup"><span data-stu-id="cd1fe-128">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.MenuStrip>|<xref:System.Windows.Controls.Menu>|<span data-ttu-id="cd1fe-129"><xref:System.Windows.Controls.Menu> applicazione di stili di controllo è simile al comportamento e aspetto del <xref:System.Windows.Forms.ToolStripProfessionalRenderer?displayProperty=nameWithType> classe.</span><span class="sxs-lookup"><span data-stu-id="cd1fe-129"><xref:System.Windows.Controls.Menu> control styling can approximate the behavior and appearance of the <xref:System.Windows.Forms.ToolStripProfessionalRenderer?displayProperty=nameWithType> class.</span></span>|  
|<xref:System.Windows.Forms.MonthCalendar>|<xref:System.Windows.Controls.Calendar>||  
|<xref:System.Windows.Forms.NotifyIcon>|<span data-ttu-id="cd1fe-130">Nessun controllo equivalente.</span><span class="sxs-lookup"><span data-stu-id="cd1fe-130">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.NumericUpDown>|<span data-ttu-id="cd1fe-131"><xref:System.Windows.Controls.TextBox> e due <xref:System.Windows.Controls.Primitives.RepeatButton> controlli.</span><span class="sxs-lookup"><span data-stu-id="cd1fe-131"><xref:System.Windows.Controls.TextBox> and two <xref:System.Windows.Controls.Primitives.RepeatButton> controls.</span></span>||  
|<xref:System.Windows.Forms.OpenFileDialog>|<xref:Microsoft.Win32.OpenFileDialog>|<span data-ttu-id="cd1fe-132">Il <xref:Microsoft.Win32.OpenFileDialog> classe è una [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] wrapper per il [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] controllo.</span><span class="sxs-lookup"><span data-stu-id="cd1fe-132">The <xref:Microsoft.Win32.OpenFileDialog> class is a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] wrapper around the [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] control.</span></span>|  
|<xref:System.Windows.Forms.PageSetupDialog>|<span data-ttu-id="cd1fe-133">Nessun controllo equivalente.</span><span class="sxs-lookup"><span data-stu-id="cd1fe-133">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.Panel>|<xref:System.Windows.Controls.Canvas>||  
|<xref:System.Windows.Forms.PictureBox>|<xref:System.Windows.Controls.Image>||  
|<xref:System.Windows.Forms.PrintDialog>|<xref:System.Windows.Controls.PrintDialog>||  
|<xref:System.Drawing.Printing.PrintDocument>|<span data-ttu-id="cd1fe-134">Nessun controllo equivalente.</span><span class="sxs-lookup"><span data-stu-id="cd1fe-134">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.PrintPreviewControl>|<xref:System.Windows.Controls.DocumentViewer>||  
|<xref:System.Windows.Forms.PrintPreviewDialog>|<span data-ttu-id="cd1fe-135">Nessun controllo equivalente.</span><span class="sxs-lookup"><span data-stu-id="cd1fe-135">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.ProgressBar>|<xref:System.Windows.Controls.ProgressBar>||  
|<xref:System.Windows.Forms.PropertyGrid>|<span data-ttu-id="cd1fe-136">Nessun controllo equivalente.</span><span class="sxs-lookup"><span data-stu-id="cd1fe-136">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.RadioButton>|<xref:System.Windows.Controls.RadioButton>||  
|<xref:System.Windows.Forms.RichTextBox>|<xref:System.Windows.Controls.RichTextBox>||  
|<xref:System.Windows.Forms.SaveFileDialog>|<xref:Microsoft.Win32.SaveFileDialog>|<span data-ttu-id="cd1fe-137">Il <xref:Microsoft.Win32.SaveFileDialog> classe è una [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] wrapper per il [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] controllo.</span><span class="sxs-lookup"><span data-stu-id="cd1fe-137">The <xref:Microsoft.Win32.SaveFileDialog> class is a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] wrapper around the [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] control.</span></span>|  
|<xref:System.Windows.Forms.ScrollableControl>|<xref:System.Windows.Controls.ScrollViewer>||  
|<xref:System.Media.SoundPlayer>|<xref:System.Windows.Media.MediaPlayer>||  
|<xref:System.Windows.Forms.SplitContainer>|<xref:System.Windows.Controls.GridSplitter>||  
|<xref:System.Windows.Forms.StatusStrip>|<xref:System.Windows.Controls.Primitives.StatusBar>||  
|<xref:System.Windows.Forms.TabControl>|<xref:System.Windows.Controls.TabControl>||  
|<xref:System.Windows.Forms.TableLayoutPanel>|<xref:System.Windows.Controls.Grid>||  
|<xref:System.Windows.Forms.TextBox>|<xref:System.Windows.Controls.TextBox>||  
|<xref:System.Windows.Forms.Timer>|<xref:System.Windows.Threading.DispatcherTimer>||  
|<xref:System.Windows.Forms.ToolStrip>|<xref:System.Windows.Controls.ToolBar>||  
|<xref:System.Windows.Forms.ToolStripContainer>|<span data-ttu-id="cd1fe-138"><xref:System.Windows.Controls.ToolBar> con composizione.</span><span class="sxs-lookup"><span data-stu-id="cd1fe-138"><xref:System.Windows.Controls.ToolBar> with composition.</span></span>||  
|<xref:System.Windows.Forms.ToolStripDropDown>|<span data-ttu-id="cd1fe-139"><xref:System.Windows.Controls.ToolBar> con composizione.</span><span class="sxs-lookup"><span data-stu-id="cd1fe-139"><xref:System.Windows.Controls.ToolBar> with composition.</span></span>||  
|<xref:System.Windows.Forms.ToolStripDropDownMenu>|<span data-ttu-id="cd1fe-140"><xref:System.Windows.Controls.ToolBar> con composizione.</span><span class="sxs-lookup"><span data-stu-id="cd1fe-140"><xref:System.Windows.Controls.ToolBar> with composition.</span></span>||  
|<xref:System.Windows.Forms.ToolStripPanel>|<span data-ttu-id="cd1fe-141"><xref:System.Windows.Controls.ToolBar> con composizione.</span><span class="sxs-lookup"><span data-stu-id="cd1fe-141"><xref:System.Windows.Controls.ToolBar> with composition.</span></span>||  
|<xref:System.Windows.Forms.ToolTip>|<xref:System.Windows.Controls.ToolTip>||  
|<xref:System.Windows.Forms.TrackBar>|<xref:System.Windows.Controls.Slider>||  
|<xref:System.Windows.Forms.TreeView>|<xref:System.Windows.Controls.TreeView>||  
|<xref:System.Windows.Forms.UserControl>|<xref:System.Windows.Controls.UserControl>||  
|<xref:System.Windows.Forms.VScrollBar>|<xref:System.Windows.Controls.Primitives.ScrollBar>|<span data-ttu-id="cd1fe-142">Lo scorrimento è incorporato in controlli contenitore.</span><span class="sxs-lookup"><span data-stu-id="cd1fe-142">Scrolling is built into container controls.</span></span>|  
|<xref:System.Windows.Forms.WebBrowser>|<span data-ttu-id="cd1fe-143"><xref:System.Windows.Controls.Frame>, <xref:System.Windows.Controls.WebBrowser?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="cd1fe-143"><xref:System.Windows.Controls.Frame>, <xref:System.Windows.Controls.WebBrowser?displayProperty=nameWithType></span></span>|<span data-ttu-id="cd1fe-144">Il <xref:System.Windows.Controls.Frame> controllo può ospitare pagine HTML.</span><span class="sxs-lookup"><span data-stu-id="cd1fe-144">The <xref:System.Windows.Controls.Frame> control can host HTML pages.</span></span><br /><br /> <span data-ttu-id="cd1fe-145">A partire dal [!INCLUDE[net_v35SP1_short](../../../../includes/net-v35sp1-short-md.md)], il <xref:System.Windows.Controls.WebBrowser?displayProperty=nameWithType> controllo può ospitare pagine HTML e supporta inoltre la <xref:System.Windows.Controls.Frame> controllo.</span><span class="sxs-lookup"><span data-stu-id="cd1fe-145">Starting in the [!INCLUDE[net_v35SP1_short](../../../../includes/net-v35sp1-short-md.md)], the <xref:System.Windows.Controls.WebBrowser?displayProperty=nameWithType> control can host HTML pages and also backs the <xref:System.Windows.Controls.Frame> control.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cd1fe-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cd1fe-146">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- <span data-ttu-id="cd1fe-147">[Gli sviluppatori di WPF Designer per Windows Form](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/cc165605(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="cd1fe-147">[WPF Designer for Windows Forms Developers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/cc165605(v=vs.100))</span></span>
- [<span data-ttu-id="cd1fe-148">Procedura dettagliata: Hosting di controlli Windows Form in WPF</span><span class="sxs-lookup"><span data-stu-id="cd1fe-148">Walkthrough: Hosting a Windows Forms Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
- [<span data-ttu-id="cd1fe-149">Procedura dettagliata: Hosting di un controllo composito WPF in Windows Form</span><span class="sxs-lookup"><span data-stu-id="cd1fe-149">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [<span data-ttu-id="cd1fe-150">Migrazione e interoperabilità</span><span class="sxs-lookup"><span data-stu-id="cd1fe-150">Migration and Interoperability</span></span>](migration-and-interoperability.md)
