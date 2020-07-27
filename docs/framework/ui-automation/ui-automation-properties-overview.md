---
title: Cenni preliminari sulle proprietà di automazione interfaccia utente
description: Vedere un'ampia panoramica delle proprietà di automazione interfaccia utente Microsoft. Informazioni sugli identificatori di proprietà, sulle proprietà per categoria, localizzazione e proprietà ed eventi.
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, properties
- properties, UI Automation
ms.assetid: a6c31d7b-b33e-49b3-b5c1-31a345f9b7c8
ms.openlocfilehash: 17d780c059530be8c91890302ea4066de2d4aa73
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87163213"
---
# <a name="ui-automation-properties-overview"></a>Cenni preliminari sulle proprietà di automazione interfaccia utente
> [!NOTE]
> Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>. Per informazioni aggiornate su [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere [Windows Automation API: automazione interfaccia utente](/windows/win32/winauto/entry-uiauto-win32).  
  
 I provider di automazione interfaccia utente espongono le proprietà negli elementi di [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] . Queste proprietà consentono alle applicazioni client di automazione interfaccia utente di individuare informazioni su parti dell' [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)], soprattutto i controlli, inclusi i dati sia statici che dinamici.  
  
 Questa sezione offre un'ampia panoramica delle proprietà di [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] . Informazioni più specifiche sono disponibili negli argomenti seguenti:  
  
- [Proprietà di automazione interfaccia utente per i client](ui-automation-properties-for-clients.md)  
  
- [Implementazione del provider di automazione interfaccia utente lato server](server-side-ui-automation-provider-implementation.md)  
  
<a name="Property_Identifiers"></a>
## <a name="property-identifiers"></a>Identificatori di proprietà  
 Ogni proprietà è identificata da un numero e da un nome. I nomi delle proprietà vengono usati solo per il debug e la diagnosi. I provider utilizzano gli ID numerici per identificare le richieste di proprietà in ingresso. Le applicazioni client, tuttavia, usano solo <xref:System.Windows.Automation.AutomationProperty>, che incapsula il numero e il nome, per identificare le proprietà che vogliono recuperare.  
  
 Gli oggetti<xref:System.Windows.Automation.AutomationProperty> che rappresentano particolari proprietà sono disponibili come campi in diverse classi. Per motivi di sicurezza, i provider di automazione interfaccia utente ottengono questi oggetti da un set separato di classi contenute in Uiautomationtypes.dll.  
  
 La tabella seguente classifica le proprietà in base alle classi che contengono gli <xref:System.Windows.Automation.AutomationProperty> ID.  
  
|Tipologie di proprietà|I client ottengono gli ID da|I provider ottengono gli ID da|  
|-------------------------|--------------------------|----------------------------|  
|Proprietà comuni a tutti gli elementi (vedere le tabelle seguenti)|<xref:System.Windows.Automation.AutomationElement>|<xref:System.Windows.Automation.AutomationElementIdentifiers>|  
|Posizione di una finestra di ancoraggio|<xref:System.Windows.Automation.DockPattern>|<xref:System.Windows.Automation.DockPatternIdentifiers>|  
|Stato di un elemento che può essere espanso e compresso|<xref:System.Windows.Automation.ExpandCollapsePattern>|<xref:System.Windows.Automation.ExpandCollapsePatternIdentifiers>|  
|Proprietà di un elemento in una griglia|<xref:System.Windows.Automation.GridItemPattern>|<xref:System.Windows.Automation.GridItemPatternIdentifiers>|  
|Proprietà di una griglia|<xref:System.Windows.Automation.GridPattern>|<xref:System.Windows.Automation.GridPatternIdentifiers>|  
|Visualizzazione corrente e supportata di un elemento con più visualizzazioni|<xref:System.Windows.Automation.MultipleViewPattern>|<xref:System.Windows.Automation.MultipleViewPatternIdentifiers>|  
|Proprietà di un elemento che viene spostato su un intervallo di valori, ad esempio un dispositivo di scorrimento|<xref:System.Windows.Automation.RangeValuePattern>|<xref:System.Windows.Automation.RangeValuePatternIdentifiers>|  
|Proprietà di una finestra di scorrimento|<xref:System.Windows.Automation.ScrollPattern>|<xref:System.Windows.Automation.ScrollPatternIdentifiers>|  
|Stato e contenitore di un elemento che può essere selezionato, ad esempio in un elenco|<xref:System.Windows.Automation.SelectionItemPattern>|<xref:System.Windows.Automation.SelectionItemPatternIdentifiers>|  
|Proprietà di un controllo contenente gli elementi della selezione|<xref:System.Windows.Automation.SelectionPattern>|<xref:System.Windows.Automation.SelectionPatternIdentifiers>|  
|Intestazioni di colonna e di riga di un elemento in una tabella|<xref:System.Windows.Automation.TableItemPattern>|<xref:System.Windows.Automation.TableItemPatternIdentifiers>|  
|Intestazioni di colonna e di riga e orientamento di una tabella|<xref:System.Windows.Automation.TablePattern>|<xref:System.Windows.Automation.TablePatternIdentifiers>|  
|Stato di un controllo di attivazione/disattivazione|<xref:System.Windows.Automation.TogglePattern>|<xref:System.Windows.Automation.TogglePatternIdentifiers>|  
|Funzionalità di un elemento che può essere spostato, ruotato o ridimensionato|<xref:System.Windows.Automation.TransformPattern>|<xref:System.Windows.Automation.TransformPatternIdentifiers>|  
|Valore e funzionalità di lettura/scrittura di un elemento con un valore|<xref:System.Windows.Automation.ValuePattern>|<xref:System.Windows.Automation.ValuePatternIdentifiers>|  
|Funzionalità e stato di una finestra|<xref:System.Windows.Automation.WindowPattern>|<xref:System.Windows.Automation.WindowPatternIdentifiers>|  
  
<a name="Properties_by_Category"></a>
## <a name="properties-by-category"></a>Proprietà per categoria  
 Le tabelle seguenti classificano le proprietà i cui ID sono disponibili in <xref:System.Windows.Automation.AutomationElement> e <xref:System.Windows.Automation.AutomationElementIdentifiers> . Queste proprietà sono comuni a tutti i controlli. È probabile che quasi tutte siano statiche per tutto il ciclo di vita dell'applicazione del provider. Le proprietà più dinamiche sono associate ai pattern di controllo.  
  
 La colonna **Accesso a proprietà** elenca tutte le altre funzioni di accesso per ogni proprietà, oltre a <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A> e <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A>. Per altre informazioni su come ottenere le proprietà in un'applicazione client, vedere [UI Automation Properties for Clients](ui-automation-properties-for-clients.md).  
  
> [!NOTE]
> Per informazioni specifiche su ogni proprietà, seguire il collegamento nella colonna **Accesso a proprietà** .  
  
### <a name="display-characteristics"></a>Caratteristiche dello schermo  
  
|Identificatore proprietà|Accesso a proprietà|  
|-------------------------|---------------------|  
|<xref:System.Windows.Automation.AutomationElement.BoundingRectangleProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.BoundingRectangle%2A>|  
|<xref:System.Windows.Automation.AutomationElement.CultureProperty>|n/d|  
|<xref:System.Windows.Automation.AutomationElement.HelpTextProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.HelpText%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsOffscreenProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsOffscreen%2A>|  
|<xref:System.Windows.Automation.AutomationElement.OrientationProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Orientation%2A>|  
  
### <a name="element-type"></a>Tipo di elemento  
  
|Identificatore proprietà|Accesso a proprietà|  
|-------------------------|---------------------|  
|<xref:System.Windows.Automation.AutomationElement.ControlTypeProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ControlType%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsContentElementProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsContentElement%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsControlElementProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsControlElement%2A>|  
|<xref:System.Windows.Automation.AutomationElement.ItemTypeProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ItemType%2A>|  
|<xref:System.Windows.Automation.AutomationElement.LocalizedControlTypeProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.LocalizedControlType%2A>|  
  
### <a name="identification"></a>Identificazione  
  
|Identificatore proprietà|Accesso a proprietà|  
|-------------------------|---------------------|  
|<xref:System.Windows.Automation.AutomationElement.AutomationIdProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.AutomationId%2A>|  
|<xref:System.Windows.Automation.AutomationElement.ClassNameProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ClassName%2A>|  
|<xref:System.Windows.Automation.AutomationElement.FrameworkIdProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.FrameworkId%2A>|  
|<xref:System.Windows.Automation.AutomationElement.LabeledByProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.LabeledBy%2A>|  
|<xref:System.Windows.Automation.AutomationElement.NameProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name%2A>|  
|<xref:System.Windows.Automation.AutomationElement.ProcessIdProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ProcessId%2A>|  
|<xref:System.Windows.Automation.AutomationElement.RuntimeIdProperty>|<xref:System.Windows.Automation.AutomationElement.GetRuntimeId%2A>|  
|<xref:System.Windows.Automation.AutomationElement.NativeWindowHandleProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.NativeWindowHandle%2A>|  
  
### <a name="interaction"></a>Interazione  
  
|Identificatore proprietà|Accesso a proprietà|  
|-------------------------|---------------------|  
|<xref:System.Windows.Automation.AutomationElement.AcceleratorKeyProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.AcceleratorKey%2A>|  
|<xref:System.Windows.Automation.AutomationElement.AccessKeyProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.AccessKey%2A>|  
|<xref:System.Windows.Automation.AutomationElement.ClickablePointProperty>|<xref:System.Windows.Automation.AutomationElement.GetClickablePoint%2A>|  
|<xref:System.Windows.Automation.AutomationElement.HasKeyboardFocusProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.HasKeyboardFocus%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsEnabledProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsEnabled%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsKeyboardFocusableProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsKeyboardFocusable%2A>|  
  
### <a name="support-for-patterns"></a>Supporto per pattern  
  
|Identificatore proprietà|Accesso a proprietà|  
|-------------------------|---------------------|  
|<xref:System.Windows.Automation.AutomationElement.IsDockPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsExpandCollapsePatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsGridItemPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsGridPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsInvokePatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsMultipleViewPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsRangeValuePatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsScrollItemPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsScrollPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsSelectionItemPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsSelectionPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsTableItemPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsTablePatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsTextPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsTogglePatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsTransformPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsValuePatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsWindowPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
  
### <a name="miscellaneous"></a>Varie  
  
|Identificatore proprietà|Accesso a proprietà|  
|-------------------------|---------------------|  
|<xref:System.Windows.Automation.AutomationElement.IsRequiredForFormProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsRequiredForForm%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsPasswordProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsPassword%2A>|  
|<xref:System.Windows.Automation.AutomationElement.ItemStatusProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ItemStatus%2A>|  
  
<a name="Localization"></a>
## <a name="localization"></a>Localizzazione  
 I provider di[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] devono presentare le proprietà seguenti nella lingua del sistema operativo:  
  
- <xref:System.Windows.Automation.AutomationElementIdentifiers.AcceleratorKeyProperty>  
  
- <xref:System.Windows.Automation.AutomationElementIdentifiers.AccessKeyProperty>  
  
- <xref:System.Windows.Automation.AutomationElementIdentifiers.HelpTextProperty>  
  
- <xref:System.Windows.Automation.AutomationElementIdentifiers.LocalizedControlTypeProperty>  
  
- <xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>  
  
<a name="Properties_and_Events"></a>
## <a name="properties-and-events"></a>Proprietà ed eventi  
 In [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] il concetto di eventi di modifica di proprietà è strettamente collegato alle proprietà. Per le proprietà dinamiche, l'applicazione client deve venire a conoscenza del fatto che il valore di una proprietà è cambiato, per poter aggiornare la cache delle informazioni o rispondere in altro modo alle nuove informazioni.  
  
 I provider generano eventi quando vengono apportate modifiche all' [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] . Se, ad esempio, una casella di controllo viene selezionata o deselezionata, un evento di modificata di proprietà viene generato dall'implementazione del pattern Toggle da parte del provider. I provider possono generare gli eventi in modo selettivo, a seconda che i client siano in ascolto di eventi oppure di eventi specifici.  
  
 Non tutte le modifiche di proprietà generano eventi. Questo dipende totalmente dall'implementazione del provider di automazione interfaccia utente per l'elemento. Ad esempio, i provider di proxy standard per le caselle di riepilogo non generano un evento quando <xref:System.Windows.Automation.SelectionPattern.SelectionProperty> cambia. In questo caso, l'applicazione è invece in ascolto di un evento <xref:System.Windows.Automation.SelectionItemPattern.ElementSelectedEvent>.  
  
 I client restano in ascolto degli eventi sottoscrivendoli. Sottoscrivere gli eventi significa creare metodi delegati che possono gestire gli eventi e quindi passare i metodi ad [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] insieme agli eventi specifici che verranno gestiti da tali metodi. In particolare, per gli eventi di modifica di proprietà i client devono implementare <xref:System.Windows.Automation.AutomationPropertyChangedEventHandler>.  
  
## <a name="see-also"></a>Vedere anche

- [Memorizzazione nella cache dei client di automazione interfaccia utente](caching-in-ui-automation-clients.md)
- [Proprietà di automazione interfaccia utente per i client](ui-automation-properties-for-clients.md)
- [Implementazione del provider di automazione interfaccia utente lato server](server-side-ui-automation-provider-implementation.md)
- [Trovare un elemento di automazione interfaccia utente in base a una proprietà](find-a-ui-automation-element-based-on-a-property-condition.md)
- [Restituire proprietà da un provider di automazione interfaccia utente](return-properties-from-a-ui-automation-provider.md)
- [Generare eventi da un provider di automazione interfaccia utente](raise-events-from-a-ui-automation-provider.md)
