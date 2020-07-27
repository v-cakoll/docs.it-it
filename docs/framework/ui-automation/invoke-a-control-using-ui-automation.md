---
title: Richiamare un controllo utilizzando automazione interfaccia utente
description: Usare automazione interfaccia utente per trovare un controllo che corrisponda a determinate condizioni di proprietà, creare un oggetto AutomationElement, ottenere un InvokePattern e usare Invoke sul controllo.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- invoking controls
- UI Automation, invoking controls
- controls, invoking
ms.assetid: 5ee2de3f-256c-43ec-b64c-62ace91f9983
ms.openlocfilehash: 2347a620aab848bf6bcc649a9780aa5a3a520822
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87168176"
---
# <a name="invoke-a-control-using-ui-automation"></a>Richiamare un controllo utilizzando automazione interfaccia utente
> [!NOTE]
> Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>. Per informazioni aggiornate su [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere [Windows Automation API: automazione interfaccia utente](/windows/win32/winauto/entry-uiauto-win32).  
  
 In questo argomento viene illustrato come eseguire le attività seguenti:  
  
- Trovare un controllo che corrisponda a condizioni di proprietà specifiche scorrendo la visualizzazione controlli dell'albero di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] per l'applicazione di destinazione.  
  
- Creare un <xref:System.Windows.Automation.AutomationElement> per ogni controllo.  
  
- Ottenere un oggetto <xref:System.Windows.Automation.InvokePattern> da qualsiasi elemento [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] trovato che supporta il pattern di controllo <xref:System.Windows.Automation.InvokePattern> .  
  
- Usare <xref:System.Windows.Automation.InvokePattern.Invoke%2A> per richiamare il controllo da un gestore eventi client.  
  
## <a name="example"></a>Esempio  
 Questo esempio usa il metodo <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> della classe <xref:System.Windows.Automation.AutomationElement> per generare un oggetto <xref:System.Windows.Automation.InvokePattern> e richiamare un controllo mediante il metodo <xref:System.Windows.Automation.InvokePattern.Invoke%2A> .  
  
 [!code-csharp[InvokePatternApp#1100](../../../samples/snippets/csharp/VS_Snippets_Wpf/InvokePatternApp/CSharp/InvokePatternApp.cs#1100)]
 [!code-vb[InvokePatternApp#1100](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InvokePatternApp/VisualBasic/Client.vb#1100)]  
[!code-csharp[InvokePatternApp#1102](../../../samples/snippets/csharp/VS_Snippets_Wpf/InvokePatternApp/CSharp/InvokePatternApp.cs#1102)]
[!code-vb[InvokePatternApp#1102](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InvokePatternApp/VisualBasic/Client.vb#1102)]  
  
## <a name="see-also"></a>Vedere anche

- [Esempio InvokePattern, ExpandCollapsePattern e TogglePattern](https://github.com/Microsoft/WPF-Samples/tree/master/Accessibility/InvokePattern)
