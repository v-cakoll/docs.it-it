---
title: Cenni preliminari sui tipi di controllo per l'automazione interfaccia utente
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, control types
- control types, UI Automation
ms.assetid: 75159ef8-bd43-4d13-acb7-1f1fe9253160
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: c8ca0934e724c4035fb24b9cb246b0b2f41eea3d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="ui-automation-control-types-overview"></a>Cenni preliminari sui tipi di controllo per l'automazione interfaccia utente
> [!NOTE]
>  Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>. Per informazioni aggiornate su [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere l'argomento sull' [API Automazione interfaccia utente di Windows](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 I tipi di controllo di[!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] sono identificatori noti che possono essere usati per indicare quale tipo di controllo è rappresentato da un particolare elemento, ad esempio una casella combinata o un pulsante.  
  
 Un identificatore noto rende più semplice per i dispositivi di assistive technology determinare quali tipi di controlli sono disponibili nell' [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] e come interagire con i controlli.  
  
<a name="UI_Automation_Control_Type_Requisites"></a>   
## <a name="ui-automation-control-type-requisites"></a>Requisiti per i tipi di controllo per l'automazione dell'interfaccia utente  
 I tipi di controllo per l'[!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] forniscono una serie di condizioni che i provider devono soddisfare. Se queste condizioni sono soddisfatte, il controllo può usare il nome del tipo di controllo specifico. Per tutti i tipi di controllo esistono condizioni relative agli aspetti seguenti:  
  
-   Pattern di controllo dell'[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] : i pattern di controllo devono essere supportati, i pattern facoltativi e quelli che non devono essere supportati dal controllo.  
  
-   Valori di proprietà dell'[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] : valori delle proprietà supportati.  
  
-   Struttura ad albero dell'[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]: la struttura ad albero [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] necessaria per il controllo.  
  
 Se un controllo soddisfa le condizioni per un particolare tipo di controllo, il valore della proprietà <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ControlType%2A> corrisponderà a tale tipo.  
  
<a name="Current_UI_Automation_Control_Types"></a>   
## <a name="current-ui-automation-control-types"></a>Tipi di controllo correnti per l'automazione dell'interfaccia utente  
 Nell'elenco seguente è riportato il set corrente di tipi di controllo per l' [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] :  
  
-   [Supporto per automazione interfaccia utente del tipo di controllo Button](../../../docs/framework/ui-automation/ui-automation-support-for-the-button-control-type.md)  
  
-   [Supporto per automazione interfaccia utente del tipo di controllo Calendar](../../../docs/framework/ui-automation/ui-automation-support-for-the-calendar-control-type.md)  
  
-   [Supporto per automazione interfaccia utente del tipo di controllo CheckBox](../../../docs/framework/ui-automation/ui-automation-support-for-the-checkbox-control-type.md)  
  
-   [Supporto per automazione interfaccia utente del tipo di controllo ComboBox](../../../docs/framework/ui-automation/ui-automation-support-for-the-combobox-control-type.md)  
  
-   [Supporto per automazione interfaccia utente del tipo di controllo DataGrid](../../../docs/framework/ui-automation/ui-automation-support-for-the-datagrid-control-type.md)  
  
-   [Supporto per automazione interfaccia utente del tipo di controllo DataItem](../../../docs/framework/ui-automation/ui-automation-support-for-the-dataitem-control-type.md)  
  
-   [Supporto per automazione interfaccia utente del tipo di controllo Document](../../../docs/framework/ui-automation/ui-automation-support-for-the-document-control-type.md)  
  
-   [Supporto per automazione interfaccia utente del tipo di controllo Edit](../../../docs/framework/ui-automation/ui-automation-support-for-the-edit-control-type.md)  
  
-   [Supporto per automazione interfaccia utente del tipo di controllo Group](../../../docs/framework/ui-automation/ui-automation-support-for-the-group-control-type.md)  
  
-   [Supporto per automazione interfaccia utente del tipo di controllo Header](../../../docs/framework/ui-automation/ui-automation-support-for-the-header-control-type.md)  
  
-   [Supporto per automazione interfaccia utente del tipo di controllo HeaderItem](../../../docs/framework/ui-automation/ui-automation-support-for-the-headeritem-control-type.md)  
  
-   [Supporto per automazione interfaccia utente del tipo di controllo Hyperlink](../../../docs/framework/ui-automation/ui-automation-support-for-the-hyperlink-control-type.md)  
  
-   [Supporto per automazione interfaccia utente del tipo di controllo Image](../../../docs/framework/ui-automation/ui-automation-support-for-the-image-control-type.md)  
  
-   [Supporto per automazione interfaccia utente del tipo di controllo List](../../../docs/framework/ui-automation/ui-automation-support-for-the-list-control-type.md)  
  
-   [Supporto per automazione interfaccia utente del tipo di controllo ListItem](../../../docs/framework/ui-automation/ui-automation-support-for-the-listitem-control-type.md)  
  
-   [Supporto per automazione dell'interfaccia utente del tipo di controllo Menu](../../../docs/framework/ui-automation/ui-automation-support-for-the-menu-control-type.md)  
  
-   [Supporto per automazione interfaccia utente del tipo di controllo MenuBar](../../../docs/framework/ui-automation/ui-automation-support-for-the-menubar-control-type.md)  
  
-   [Supporto per automazione interfaccia utente del tipo di controllo MenuItem](../../../docs/framework/ui-automation/ui-automation-support-for-the-menuitem-control-type.md)  
  
-   [Supporto per automazione interfaccia utente del tipo di controllo Pane](../../../docs/framework/ui-automation/ui-automation-support-for-the-pane-control-type.md)  
  
-   [Supporto per automazione interfaccia utente del tipo di controllo ProgressBar](../../../docs/framework/ui-automation/ui-automation-support-for-the-progressbar-control-type.md)  
  
-   [Supporto per automazione interfaccia utente del tipo di controllo RadioButton](../../../docs/framework/ui-automation/ui-automation-support-for-the-radiobutton-control-type.md)  
  
-   [Supporto per automazione interfaccia utente del tipo di controllo ScrollBar](../../../docs/framework/ui-automation/ui-automation-support-for-the-scrollbar-control-type.md)  
  
-   [Supporto per automazione interfaccia utente del tipo di controllo Separator](../../../docs/framework/ui-automation/ui-automation-support-for-the-separator-control-type.md)  
  
-   [Supporto per automazione interfaccia utente del tipo di controllo Slider](../../../docs/framework/ui-automation/ui-automation-support-for-the-slider-control-type.md)  
  
-   [Supporto per automazione interfaccia utente del tipo di controllo Spinner](../../../docs/framework/ui-automation/ui-automation-support-for-the-spinner-control-type.md)  
  
-   [Supporto per automazione interfaccia utente del tipo di controllo SplitButton](../../../docs/framework/ui-automation/ui-automation-support-for-the-splitbutton-control-type.md)  
  
-   [Supporto per automazione interfaccia utente del tipo di controllo StatusBar](../../../docs/framework/ui-automation/ui-automation-support-for-the-statusbar-control-type.md)  
  
-   [Supporto di automazione interfaccia utente per il tipo di controllo Tab](../../../docs/framework/ui-automation/ui-automation-support-for-the-tab-control-type.md)  
  
-   [Supporto di automazione interfaccia utente per il tipo di controllo TabItem](../../../docs/framework/ui-automation/ui-automation-support-for-the-tabitem-control-type.md)  
  
-   [Supporto per automazione interfaccia utente del tipo di controllo Table](../../../docs/framework/ui-automation/ui-automation-support-for-the-table-control-type.md)  
  
-   [Supporto per automazione interfaccia utente del tipo di controllo Text](../../../docs/framework/ui-automation/ui-automation-support-for-the-text-control-type.md)  
  
-   [Supporto per automazione interfaccia utente del tipo di controllo Thumb](../../../docs/framework/ui-automation/ui-automation-support-for-the-thumb-control-type.md)  
  
-   [Supporto per automazione interfaccia utente del tipo di controllo TitleBar](../../../docs/framework/ui-automation/ui-automation-support-for-the-titlebar-control-type.md)  
  
-   [Supporto per automazione interfaccia utente del tipo di controllo ToolBar](../../../docs/framework/ui-automation/ui-automation-support-for-the-toolbar-control-type.md)  
  
-   [Supporto per automazione dell'interfaccia utente del tipo di controllo ToolTip](../../../docs/framework/ui-automation/ui-automation-support-for-the-tooltip-control-type.md)  
  
-   [Supporto per automazione interfaccia utente del tipo di controllo Tree](../../../docs/framework/ui-automation/ui-automation-support-for-the-tree-control-type.md)  
  
-   [Supporto per automazione interfaccia utente del tipo di controllo TreeItem](../../../docs/framework/ui-automation/ui-automation-support-for-the-treeitem-control-type.md)  
  
-   [Supporto per automazione interfaccia utente del tipo di controllo Window](../../../docs/framework/ui-automation/ui-automation-support-for-the-window-control-type.md)  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Automation.ControlType>
