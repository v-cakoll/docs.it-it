---
title: Supporto per automazione interfaccia utente dei controlli standard
ms.date: 03/30/2017
helpviewer_keywords:
- controls, UI Automation support for
- UI Automation, support for standard controls
ms.assetid: 3770ea8a-2655-4add-9c59-fe0610ad5084
ms.openlocfilehash: 36028d589e98177f6a0e83092edd656860b1a8d4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179859"
---
# <a name="ui-automation-support-for-standard-controls"></a>Supporto per automazione interfaccia utente dei controlli standard
> [!NOTE]
> Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>. Per informazioni aggiornate su [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere [Windows Automation API: automazione interfaccia utente](/windows/win32/winauto/entry-uiauto-win32).  
  
 In questo argomento [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] sono contenute informazioni sul [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]supporto per i controlli standard nelle applicazioni sviluppate per i framework Win32 e Windows Form.  
  
<a name="Windows_Presentation_Foundation_Controls"></a>
## <a name="windows-presentation-foundation-controls"></a>Controlli WPF (Windows Presentation Foundation)  
 Tutti gli elementi di controllo [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] che forniscono informazioni o supporto per l'interazione dell'utente dispongono di supporto nativo completo per [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]. Gli altri elementi, ad esempio i pannelli, non sono visibile per [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].  
  
<a name="Win32_Controls"></a>
## <a name="win32-controls"></a>Controlli Win32  
 La maggior parte dei [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] controlli Win32 sono esposti a tramite provider sul lato client in UIAutomationClientsideProviders.dll. Questo assembly viene automaticamente registrato per l'uso con applicazioni client di automazione interfaccia utente.  
  
 Il supporto completo viene fornito solo per i controlli della versione 6 di *ComCtrl32.dll*.  
  
 I controlli seguenti sono supportati.  
  
|Nome di classe|Tipo di controllo|  
|----------------|------------------|  
|Pulsante|Pulsante|  
|Pulsante|RadioButton|  
|Pulsante|Gruppo|  
|Pulsante|CheckBox|  
|Pulsante|Hyperlink|  
|Pulsante|SplitButton|  
|Pulsante|CheckBox|  
|ComboBoxEx32|ComboBox|  
|ComboBox|ComboBox|  
|Modifica|Document|  
|Modifica|Modifica|  
|SysLink|Hyperlink|  
|Statico|Text|  
|Statico|Immagine|  
|SysIPAddress32|Personalizzato|  
|SysHeader32|Header/HeaderItem|  
|SysListView32|DataGrid|  
|SysListView32|Elenco|  
|ListBox|Elenco|  
|ListBox|ListItem|  
|#32768|Menu|  
|#32768|MenuItem|  
|msctls_progress32|ProgressBar|  
|RichEdit|Documento. Vedere la nota.|  
|RichEdit20A|Document|  
|RichEdit20W|Document|  
|RichEdit50W|Document|  
|ScrollBar|Dispositivo di scorrimento|  
|msctls_trackbar32|Dispositivo di scorrimento|  
|msctls_updown32|Spinner|  
|msctls_statusbar32|StatusBar|  
|SysTabControl32|Scheda|  
|SysTabControl32|TabItem|  
|ToolbarWindow32|ToolBar|  
|ToolbarWindow32|MenuItem|  
|ToolbarWindow32|Pulsante|  
|ToolbarWindow32|CheckBox|  
|ToolbarWindow32|RadioButton|  
|ToolbarWindow32|Separatore|  
|tooltips_class32|ToolTip|  
|#32774|ToolTip|  
|ReBarWindow32|Barra degli strumenti|  
|SysTreeView32|Albero|  
|SysTreeView32|TreeItem|  
  
 **Nota:** Il controllo RichEdit è supportato solo per le versioni fornite con Windows Vista (in RichEd20.dll versione 3.1 e successive e MsftEdit.dll versione 4.1 e successive).  
  
 I controlli seguenti non sono supportati.  
  
|Nome di classe|Tipo di controllo|  
|----------------|------------------|  
|SysAnimate32|Immagine|  
|SysPager|Spinner|  
|SysDateTimePick32|Personalizzato|  
|SysMonthCal32|Calendario|  
|MS_WINNOTE|Descrizione comando|  
|VBBubble|Descrizione comando|  
|ScrollBar (se usato come controllo autonomo)|Dispositivo di scorrimento|  
|SuperGrid|Personalizzato|  
  
<a name="Windows_Forms_Controls"></a>
## <a name="windows-forms-controls"></a>Controlli per Windows Form  
 I controlli Windows [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] Form vengono esposti tramite provider sul lato client in UIAutomationClientsideProviders.dll.Windows Forms controls are exposed to through client-side providers in UIAutomationClientsideProviders.dll. Questo assembly viene automaticamente registrato per l'uso con applicazioni client di automazione interfaccia utente.  
  
 In genere, i controlli Windows Form che sono wrapper [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]gestiti per i controlli comuni Win32 sono supportati da . I controlli seguenti sono supportati.  
  
|Nome della classe|  
|----------------|  
|Pulsante|  
|CheckBox|  
|CheckedListBox|  
|ColorDialog|  
|ComboBox|  
|FolderBrowser|  
|FontDialog|  
|GroupBox|  
|HscrollBar|  
|ImageList|  
|Etichetta|  
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
|Barra degli strumenti|  
|ToolTip|  
|Trackbar|  
|TreeView|  
|VscrollBar|  
|WebBrowser|  
  
 I controlli seguenti [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] vengono esposti solo tramite il supporto per Microsoft Active Accessibility. Alcune funzionalità potrebbero non essere disponibili.  
  
|Nome del controllo|  
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

- [Tipi di controllo per l'automazione dell'interfaccia utente](ui-automation-control-types.md)
