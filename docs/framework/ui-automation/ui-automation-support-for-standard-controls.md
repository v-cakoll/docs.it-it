---
title: Supporto per automazione interfaccia utente dei controlli standard
ms.date: 03/30/2017
helpviewer_keywords:
- controls, UI Automation support for
- UI Automation, support for standard controls
ms.assetid: 3770ea8a-2655-4add-9c59-fe0610ad5084
ms.openlocfilehash: 49277073706444fd611ae41e762442388ac50b71
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789612"
---
# <a name="ui-automation-support-for-standard-controls"></a>Supporto per automazione interfaccia utente dei controlli standard
> [!NOTE]
> Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>. Per informazioni aggiornate su [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere [Windows Automation API: automazione interfaccia utente](/windows/win32/winauto/entry-uiauto-win32).  
  
 Questo argomento contiene informazioni sul supporto [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] per i controlli standard in applicazioni sviluppate per i Framework [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], Win32 e Windows Forms.  
  
<a name="Windows_Presentation_Foundation_Controls"></a>   
## <a name="windows-presentation-foundation-controls"></a>Controlli WPF (Windows Presentation Foundation)  
 Tutti gli elementi di controllo [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] che forniscono informazioni o supporto per l'interazione dell'utente dispongono di supporto nativo completo per [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]. Gli altri elementi, ad esempio i pannelli, non sono visibile per [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].  
  
<a name="Win32_Controls"></a>   
## <a name="win32-controls"></a>Controlli Win32  
 La maggior parte dei controlli Win32 viene esposta a [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] tramite provider lato client in UIAutomationClientsideProviders. dll. Questo assembly viene automaticamente registrato per l'uso con applicazioni client di automazione interfaccia utente.  
  
 Il supporto completo viene fornito solo per i controlli della versione 6 di *ComCtrl32. dll*.  
  
 I controlli seguenti sono supportati.  
  
|Nome della classe|Tipo di controllo|  
|----------------|------------------|  
|Button|Button|  
|Button|RadioButton|  
|Button|Gruppo|  
|Button|CheckBox|  
|Button|Collegamento ipertestuale|  
|Button|SplitButton|  
|Button|CheckBox|  
|ComboBoxEx32|ComboBox|  
|ComboBox|ComboBox|  
|Edit|Documento|  
|Edit|Edit|  
|SysLink|Collegamento ipertestuale|  
|Static|Testo|  
|Static|Immagine|  
|SysIPAddress32|Personalizzato|  
|SysHeader32|Header/HeaderItem|  
|SysListView32|DataGrid|  
|SysListView32|Contiene un elenco di oggetti|  
|ListBox|Contiene un elenco di oggetti|  
|ListBox|ListItem|  
|#32768|Menu|  
|#32768|MenuItem|  
|msctls_progress32|ProgressBar|  
|RichEdit|Document Vedere la nota.|  
|RichEdit20A|Documento|  
|RichEdit20W|Documento|  
|RichEdit50W|Documento|  
|ScrollBar|Slider|  
|msctls_trackbar32|Slider|  
|msctls_updown32|Spinner|  
|msctls_statusbar32|StatusBar|  
|SysTabControl32|Tab|  
|SysTabControl32|TabItem|  
|ToolbarWindow32|ToolBar|  
|ToolbarWindow32|MenuItem|  
|ToolbarWindow32|Button|  
|ToolbarWindow32|CheckBox|  
|ToolbarWindow32|RadioButton|  
|ToolbarWindow32|Separator|  
|tooltips_class32|Descrizione comando|  
|#32774|Descrizione comando|  
|ReBarWindow32|ToolBar|  
|SysTreeView32|Tree|  
|SysTreeView32|TreeItem|  
  
 **Nota** Il controllo RichEdit è supportato solo per le versioni fornite con Windows Vista (in RichEd20. dll versione 3,1 e successive e MsftEdit. dll versione 4,1 e successive).  
  
 I controlli seguenti non sono supportati.  
  
|Nome della classe|Tipo di controllo|  
|----------------|------------------|  
|SysAnimate32|Immagine|  
|SysPager|Spinner|  
|SysDateTimePick32|Personalizzato|  
|SysMonthCal32|Calendar|  
|MS_WINNOTE|ToolTip|  
|VBBubble|ToolTip|  
|ScrollBar (se usato come controllo autonomo)|Slider|  
|SuperGrid|Personalizzato|  
  
<a name="Windows_Forms_Controls"></a>   
## <a name="windows-forms-controls"></a>Controlli Windows Form  
 I controlli Windows Forms vengono esposti ai [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] tramite provider lato client in UIAutomationClientsideProviders. dll. Questo assembly viene automaticamente registrato per l'uso con applicazioni client di automazione interfaccia utente.  
  
 In genere, Windows Forms controlli che sono wrapper gestiti per i controlli comuni Win32 sono supportati da [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]. I controlli seguenti sono supportati.  
  
|Nome di classe|  
|----------------|  
|Button|  
|CheckBox|  
|CheckedListBox|  
|ColorDialog|  
|ComboBox|  
|FolderBrowser|  
|FontDialog|  
|GroupBox|  
|HscrollBar|  
|ImageList|  
|Label|  
|ListBox|  
|ListView|  
|MainMenu/ContextMenu|  
|MonthCalendar|  
|NotifyIcon|  
|OpenFileDialog|  
|PageSetupDialog|  
|PrintDialog|  
|ProgressBar|  
|RadioButton|  
|RichTextBox|  
|SaveFileDialog|  
|ScrollableControl|  
|SoundPlayer|  
|StatusBar|  
|TabControl/TabPage|  
|TextBox|  
|Timer|  
|ToolBar|  
|Descrizione comando|  
|Trackbar|  
|TreeView|  
|VscrollBar|  
|WebBrowser|  
  
 I controlli seguenti sono esposti a [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] solo tramite il supporto per Microsoft Active Accessibility. Alcune funzionalità potrebbero non essere disponibili.  
  
|Nome controllo|  
|------------------|  
|BindingSource|  
|DataGrid|  
|DataGridView|  
|DataNavigator|  
|DomainUpDown|  
|ErrorProvider|  
|FlowLayoutPanel|  
|Form|  
|LinkLabel|  
|HelpProvider|  
|MaskedTextBox|  
|MenuStrip/ContextMenuStrip|  
|NumericUpDown|  
|Panel|  
|PictureBox|  
|PrintDocument|  
|PrintPreviewControl|  
|PrintPreviewDialog|  
|PropertyGrid|  
|UserControl|  
|ToolStrip|  
|TableLayoutPanel|  
|SplitContainer/SplitterPanel|  
|Barra di divisione|  
|RaftingContainer|  
|StatusStrip|  
  
## <a name="see-also"></a>Vedere anche

- [UI Automation Control Types](ui-automation-control-types.md)
