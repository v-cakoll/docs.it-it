---
title: Supporto per automazione interfaccia utente dei controlli standard
description: Ottenere informazioni sul supporto di automazione interfaccia utente per i controlli standard in applicazioni sviluppate per Windows Presentation Foundation (WPF), Win32 e Windows Forms.
ms.date: 03/30/2017
helpviewer_keywords:
- controls, UI Automation support for
- UI Automation, support for standard controls
ms.assetid: 3770ea8a-2655-4add-9c59-fe0610ad5084
ms.openlocfilehash: 17916a6978008439e91caae00d8b6f26045f9018
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87166125"
---
# <a name="ui-automation-support-for-standard-controls"></a>Supporto per automazione interfaccia utente dei controlli standard
> [!NOTE]
> Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>. Per informazioni aggiornate su [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere [Windows Automation API: automazione interfaccia utente](/windows/win32/winauto/entry-uiauto-win32).  
  
 Questo argomento contiene informazioni sul [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] supporto di per i controlli standard in applicazioni sviluppate per i [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] Framework, Win32 e Windows Forms.  
  
<a name="Windows_Presentation_Foundation_Controls"></a>
## <a name="windows-presentation-foundation-controls"></a>Controlli WPF (Windows Presentation Foundation)  
 Tutti gli elementi di controllo [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] che forniscono informazioni o supporto per l'interazione dell'utente dispongono di supporto nativo completo per [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]. Gli altri elementi, ad esempio i pannelli, non sono visibile per [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].  
  
<a name="Win32_Controls"></a>
## <a name="win32-controls"></a>Controlli Win32  
 La maggior parte dei controlli Win32 viene esposta a [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] tramite provider lato client in UIAutomationClientsideProviders.dll. Questo assembly viene automaticamente registrato per l'uso con applicazioni client di automazione interfaccia utente.  
  
 Il supporto completo viene fornito solo per i controlli della versione 6 del *ComCtrl32.dll*.  
  
 I controlli seguenti sono supportati.  
  
|Nome di classe|Tipo di controllo|  
|----------------|------------------|  
|Button|Button|  
|Button|RadioButton|  
|Pulsante|Group|  
|Pulsante|CheckBox|  
|Pulsante|Hyperlink|  
|Pulsante|SplitButton|  
|Pulsante|CheckBox|  
|ComboBoxEx32|ComboBox|  
|ComboBox|ComboBox|  
|Modifica|Document|  
|Modifica|Modifica|  
|SysLink|Hyperlink|  
|Statico|Testo|  
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
|tooltips_class32|Descrizione comando|  
|#32774|Descrizione comando|  
|ReBarWindow32|Barra degli strumenti|  
|SysTreeView32|Albero|  
|SysTreeView32|TreeItem|  
  
 **Nota** Il controllo RichEdit è supportato solo per le versioni fornite con Windows Vista (in RichEd20.dll versione 3,1 e successive e MsftEdit.dll versione 4,1 e successive).  
  
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
 Windows Forms controlli sono esposti a [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] tramite provider lato client in UIAutomationClientsideProviders.dll. Questo assembly viene automaticamente registrato per l'uso con applicazioni client di automazione interfaccia utente.  
  
 In genere, Windows Forms controlli che sono wrapper gestiti per i controlli comuni Win32 sono supportati da [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] . I controlli seguenti sono supportati.  
  
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
|Barra degli strumenti|  
|Descrizione comando|  
|Trackbar|  
|TreeView|  
|VscrollBar|  
|WebBrowser|  
  
 I controlli seguenti sono esposti a [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] solo tramite il supporto di Microsoft Active Accessibility. Alcune funzionalità potrebbero non essere disponibili.  
  
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
