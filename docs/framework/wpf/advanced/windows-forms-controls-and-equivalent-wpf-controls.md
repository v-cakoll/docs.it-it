---
title: Controlli Windows Form e controlli WPF equivalenti
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms [WPF], interoperability with
- Windows Forms [WPF], WPF interoperation
- interoperability [WPF], Windows Forms
ms.assetid: 8a157e6b-8054-46db-a5cf-a78966acc7a1
ms.openlocfilehash: 0bf1d646b8efc0d350be13dffc6136f6f1d7495a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33547310"
---
# <a name="windows-forms-controls-and-equivalent-wpf-controls"></a>Controlli Windows Form e controlli WPF equivalenti
Molti [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controlli hanno un equivalente [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] controlli, ma alcuni [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controlli non dispongono di equivalenti [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. In questo argomento Confronta i tipi di controllo per le due tecnologie.  
  
 È possibile utilizzare sempre l'interoperabilità all'host [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] i controlli che non dispongono di equivalenti nel [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-applicazioni basate su.  
  
 Nella tabella seguente viene illustrato che [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controlli e componenti hanno un equivalente [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] controllo della funzionalità.  
  
|controllo Windows Form|Controlli WPF equivalenti|Note|  
|---------------------------|----------------------------|-------------|  
|<xref:System.Windows.Forms.BindingNavigator>|Nessun controllo equivalente.||  
|<xref:System.Windows.Forms.BindingSource>|<xref:System.Windows.Data.CollectionViewSource>||  
|<xref:System.Windows.Forms.Button>|<xref:System.Windows.Controls.Button>||  
|<xref:System.Windows.Forms.CheckBox>|<xref:System.Windows.Controls.CheckBox>||  
|<xref:System.Windows.Forms.CheckedListBox>|<xref:System.Windows.Controls.ListBox> con composizione.||  
|<xref:System.Windows.Forms.ColorDialog>|Nessun controllo equivalente.||  
|<xref:System.Windows.Forms.ComboBox>|<xref:System.Windows.Controls.ComboBox>|<xref:System.Windows.Controls.ComboBox> non supporta il completamento automatico.|  
|<xref:System.Windows.Forms.ContextMenuStrip>|<xref:System.Windows.Controls.ContextMenu>||  
|<xref:System.Windows.Forms.DataGridView>|<xref:System.Windows.Controls.DataGrid>||  
|<xref:System.Windows.Forms.DateTimePicker>|<xref:System.Windows.Controls.DatePicker>||  
|<xref:System.Windows.Forms.DomainUpDown>|<xref:System.Windows.Controls.TextBox> e due <xref:System.Windows.Controls.Primitives.RepeatButton> controlli.||  
|<xref:System.Windows.Forms.ErrorProvider>|Nessun controllo equivalente.||  
|<xref:System.Windows.Forms.FlowLayoutPanel>|<xref:System.Windows.Controls.WrapPanel> o <xref:System.Windows.Controls.StackPanel>||  
|<xref:System.Windows.Forms.FolderBrowserDialog>|Nessun controllo equivalente.||  
|<xref:System.Windows.Forms.FontDialog>|Nessun controllo equivalente.||  
|<xref:System.Windows.Forms.Form>|<xref:System.Windows.Window>|<xref:System.Windows.Window> non supporta finestre figlio.|  
|<xref:System.Windows.Forms.GroupBox>|<xref:System.Windows.Controls.GroupBox>||  
|<xref:System.Windows.Forms.HelpProvider>|Nessun controllo equivalente.|Nessuna Guida F1. "Che cos'è questa" della Guida viene sostituita dalle descrizioni comandi.|  
|<xref:System.Windows.Forms.HScrollBar>|<xref:System.Windows.Controls.Primitives.ScrollBar>|Lo scorrimento è incorporato nei controlli contenitore.|  
|<xref:System.Windows.Forms.ImageList>|Nessun controllo equivalente.||  
|<xref:System.Windows.Forms.Label>|<xref:System.Windows.Controls.Label>||  
|<xref:System.Windows.Forms.LinkLabel>|Nessun controllo equivalente.|È possibile utilizzare la <xref:System.Windows.Documents.Hyperlink> classe per ospitare collegamenti ipertestuali all'interno del contenuto di flusso.|  
|<xref:System.Windows.Forms.ListBox>|<xref:System.Windows.Controls.ListBox>||  
|<xref:System.Windows.Forms.ListView>|<xref:System.Windows.Controls.ListView>|Il <xref:System.Windows.Controls.ListView> controllo fornisce una visualizzazione dettagli di sola lettura.|  
|<xref:System.Windows.Forms.MaskedTextBox>|Nessun controllo equivalente.||  
|<xref:System.Windows.Forms.MenuStrip>|<xref:System.Windows.Controls.Menu>|<xref:System.Windows.Controls.Menu> lo stile di controllo è simile al comportamento e l'aspetto del <xref:System.Windows.Forms.ToolStripProfessionalRenderer?displayProperty=nameWithType> classe.|  
|<xref:System.Windows.Forms.MonthCalendar>|<xref:System.Windows.Controls.Calendar>||  
|<xref:System.Windows.Forms.NotifyIcon>|Nessun controllo equivalente.||  
|<xref:System.Windows.Forms.NumericUpDown>|<xref:System.Windows.Controls.TextBox> e due <xref:System.Windows.Controls.Primitives.RepeatButton> controlli.||  
|<xref:System.Windows.Forms.OpenFileDialog>|<xref:Microsoft.Win32.OpenFileDialog>|Il <xref:Microsoft.Win32.OpenFileDialog> classe è un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] wrapper di [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] controllo.|  
|<xref:System.Windows.Forms.PageSetupDialog>|Nessun controllo equivalente.||  
|<xref:System.Windows.Forms.Panel>|<xref:System.Windows.Controls.Canvas>||  
|<xref:System.Windows.Forms.PictureBox>|<xref:System.Windows.Controls.Image>||  
|<xref:System.Windows.Forms.PrintDialog>|<xref:System.Windows.Controls.PrintDialog>||  
|<xref:System.Drawing.Printing.PrintDocument>|Nessun controllo equivalente.||  
|<xref:System.Windows.Forms.PrintPreviewControl>|<xref:System.Windows.Controls.DocumentViewer>||  
|<xref:System.Windows.Forms.PrintPreviewDialog>|Nessun controllo equivalente.||  
|<xref:System.Windows.Forms.ProgressBar>|<xref:System.Windows.Controls.ProgressBar>||  
|<xref:System.Windows.Forms.PropertyGrid>|Nessun controllo equivalente.||  
|<xref:System.Windows.Forms.RadioButton>|<xref:System.Windows.Controls.RadioButton>||  
|<xref:System.Windows.Forms.RichTextBox>|<xref:System.Windows.Controls.RichTextBox>||  
|<xref:System.Windows.Forms.SaveFileDialog>|<xref:Microsoft.Win32.SaveFileDialog>|Il <xref:Microsoft.Win32.SaveFileDialog> classe è un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] wrapper di [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] controllo.|  
|<xref:System.Windows.Forms.ScrollableControl>|<xref:System.Windows.Controls.ScrollViewer>||  
|<xref:System.Media.SoundPlayer>|<xref:System.Windows.Media.MediaPlayer>||  
|<xref:System.Windows.Forms.SplitContainer>|<xref:System.Windows.Controls.GridSplitter>||  
|<xref:System.Windows.Forms.StatusStrip>|<xref:System.Windows.Controls.Primitives.StatusBar>||  
|<xref:System.Windows.Forms.TabControl>|<xref:System.Windows.Controls.TabControl>||  
|<xref:System.Windows.Forms.TableLayoutPanel>|<xref:System.Windows.Controls.Grid>||  
|<xref:System.Windows.Forms.TextBox>|<xref:System.Windows.Controls.TextBox>||  
|<xref:System.Windows.Forms.Timer>|<xref:System.Windows.Threading.DispatcherTimer>||  
|<xref:System.Windows.Forms.ToolStrip>|<xref:System.Windows.Controls.ToolBar>||  
|<xref:System.Windows.Forms.ToolStripContainer>|<xref:System.Windows.Controls.ToolBar> con composizione.||  
|<xref:System.Windows.Forms.ToolStripDropDown>|<xref:System.Windows.Controls.ToolBar> con composizione.||  
|<xref:System.Windows.Forms.ToolStripDropDownMenu>|<xref:System.Windows.Controls.ToolBar> con composizione.||  
|<xref:System.Windows.Forms.ToolStripPanel>|<xref:System.Windows.Controls.ToolBar> con composizione.||  
|<xref:System.Windows.Forms.ToolTip>|<xref:System.Windows.Controls.ToolTip>||  
|<xref:System.Windows.Forms.TrackBar>|<xref:System.Windows.Controls.Slider>||  
|<xref:System.Windows.Forms.TreeView>|<xref:System.Windows.Controls.TreeView>||  
|<xref:System.Windows.Forms.UserControl>|<xref:System.Windows.Controls.UserControl>||  
|<xref:System.Windows.Forms.VScrollBar>|<xref:System.Windows.Controls.Primitives.ScrollBar>|Lo scorrimento è incorporato nei controlli contenitore.|  
|<xref:System.Windows.Forms.WebBrowser>|<xref:System.Windows.Controls.Frame>, <xref:System.Windows.Controls.WebBrowser?displayProperty=nameWithType>|Il <xref:System.Windows.Controls.Frame> controllo può ospitare pagine HTML.<br /><br /> A partire dal [!INCLUDE[net_v35SP1_short](../../../../includes/net-v35sp1-short-md.md)], <xref:System.Windows.Controls.WebBrowser?displayProperty=nameWithType> controllo può ospitare pagine HTML e supporta inoltre la <xref:System.Windows.Controls.Frame> controllo.|  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [Gli sviluppatori di WPF Designer per Windows Form](http://msdn.microsoft.com/library/47ad0909-e89b-4996-b4ac-874d929f94ca)  
 [Procedura dettagliata: hosting di controlli Windows Form in WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md)  
 [Procedura dettaglia: hosting di un controllo WPF composito in Windows Form](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)  
 [Migrazione e interoperabilità](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)
