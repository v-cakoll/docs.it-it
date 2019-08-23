---
title: Supporto per automazione interfaccia utente dei controlli standard
ms.date: 03/30/2017
helpviewer_keywords:
- controls, UI Automation support for
- UI Automation, support for standard controls
ms.assetid: 3770ea8a-2655-4add-9c59-fe0610ad5084
ms.openlocfilehash: d83713a81e7675a68482890c2401f1a0a6803abc
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69914224"
---
# <a name="ui-automation-support-for-standard-controls"></a>Supporto per automazione interfaccia utente dei controlli standard
> [!NOTE]
> Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>. Per informazioni aggiornate su, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]vedere [API di automazione di Windows: Automazione](https://go.microsoft.com/fwlink/?LinkID=156746)interfaccia utente.  
  
 Questo argomento contiene informazioni sul supporto di [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] per i controlli standard in applicazioni sviluppate per i framework [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)]e [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] .  
  
<a name="Windows_Presentation_Foundation_Controls"></a>   
## <a name="windows-presentation-foundation-controls"></a>Controlli WPF (Windows Presentation Foundation)  
 Tutti gli elementi di controllo [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] che forniscono informazioni o supporto per l'interazione dell'utente dispongono di supporto nativo completo per [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]. Gli altri elementi, ad esempio i pannelli, non sono visibile per [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].  
  
<a name="Win32_Controls"></a>   
## <a name="win32-controls"></a>Controlli Win32  
 La maggior parte dei controlli [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] è esposta a [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] tramite provider lato client in UIAutomationClientsideProviders.dll. Questo assembly viene automaticamente registrato per l'uso con applicazioni client di automazione interfaccia utente.  
  
 Il supporto completo viene fornito solo per i controlli a partire dalla versione 6 di ComCtrl32.dll (disponibile con [!INCLUDE[TLA#tla_winxp](../../../includes/tlasharptla-winxp-md.md)] e versioni successive).  
  
 I controlli seguenti sono supportati.  
  
|Nome di classe|Tipo di controllo|  
|----------------|------------------|  
|Button|Button|  
|Button|RadioButton|  
|Button|Group|  
|Button|CheckBox|  
|Button|Hyperlink|  
|Button|SplitButton|  
|Button|CheckBox|  
|ComboBoxEx32|ComboBox|  
|ComboBox|ComboBox|  
|Edit|Documento|  
|Edit|Edit|  
|SysLink|Hyperlink|  
|statico|Text|  
|statico|Image|  
|SysIPAddress32|Custom|  
|SysHeader32|Header/HeaderItem|  
|SysListView32|DataGrid|  
|SysListView32|List|  
|ListBox|List|  
|ListBox|ListItem|  
|#32768|Menu|  
|#32768|MenuItem|  
|msctls_progress32|ProgressBar|  
|RichEdit|Document Vedere la nota.|  
|RichEdit20A|Documento|  
|RichEdit20W|Document|  
|RichEdit50W|Documento|  
|ScrollBar|Slider|  
|msctls_trackbar32|Slider|  
|msctls_updown32|Spinner|  
|msctls_statusbar32|StatusBar|  
|SysTabControl32|TAB|  
|SysTabControl32|TabItem|  
|ToolbarWindow32|ToolBar|  
|ToolbarWindow32|MenuItem|  
|ToolbarWindow32|Button|  
|ToolbarWindow32|CheckBox|  
|ToolbarWindow32|RadioButton|  
|ToolbarWindow32|Separatore|  
|tooltips_class32|Descrizione comando|  
|#32774|Descrizione comando|  
|ReBarWindow32|ToolBar|  
|SysTreeView32|Struttura ad albero|  
|SysTreeView32|TreeItem|  
  
 **Nota** Il controllo RichEdit è supportato solo per le versioni fornite con [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)] (in Riched20.dll versione 3.1 e successive e MsftEdit.dll versione 4.1 e successive).  
  
 I controlli seguenti non sono supportati.  
  
|Nome di classe|Tipo di controllo|  
|----------------|------------------|  
|SysAnimate32|Image|  
|SysPager|Spinner|  
|SysDateTimePick32|Personalizzato|  
|SysMonthCal32|Calendar|  
|MS_WINNOTE|ToolTip|  
|VBBubble|ToolTip|  
|ScrollBar (se usato come controllo autonomo)|Slider|  
|SuperGrid|Personalizzato|  
  
<a name="Windows_Forms_Controls"></a>   
## <a name="windows-forms-controls"></a>Controlli per Windows Form  
 Windows Forms controlli sono esposti a [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] tramite provider lato client in UIAutomationClientsideProviders. dll. Questo assembly viene automaticamente registrato per l'uso con applicazioni client di automazione interfaccia utente.  
  
 In genere, Windows Forms controlli che sono wrapper gestiti per [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] i controlli comuni sono supportati [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]da. I controlli seguenti sono supportati.  
  
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
  
 I controlli seguenti sono esposti a [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] solo tramite il supporto di Microsoft Active Accessibility. Alcune funzionalità potrebbero non essere disponibili.  
  
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
|Splitter|  
|RaftingContainer|  
|StatusStrip|  
  
## <a name="see-also"></a>Vedere anche

- [Tipi di controllo per l'automazione interfaccia utente](../../../docs/framework/ui-automation/ui-automation-control-types.md)
