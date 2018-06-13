---
title: Ottenere le proprietà degli elementi di automazione dell'interfaccia utente
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- properties, retrieving
- UI Automation, retrieving properties of elements
ms.assetid: 09576b1a-291f-435c-980e-dee32d899ae1
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 73678433692f5532f712f0d2c7a3c5bf138a87b5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33405577"
---
# <a name="get-ui-automation-element-properties"></a>Ottenere le proprietà degli elementi di automazione dell'interfaccia utente
> [!NOTE]
>  Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>. Per informazioni aggiornate su [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere l'argomento sull' [API Automazione interfaccia utente di Windows](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 In questo argomento viene illustrato come recuperare le proprietà di un [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] elemento.  
  
### <a name="get-a-current-property-value"></a>Ottenere un valore della proprietà corrente  
  
1.  Ottenere il <xref:System.Windows.Automation.AutomationElement> la cui proprietà si desidera ottenere.  
  
2.  Chiamare <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A>, o recuperare il <xref:System.Windows.Automation.AutomationElement.Current%2A> struttura di proprietà e ottenere il valore da uno dei relativi membri.  
  
### <a name="get-a-cached-property-value"></a>Ottiene un valore di proprietà memorizzate nella cache  
  
1.  Ottenere il <xref:System.Windows.Automation.AutomationElement> la cui proprietà si desidera ottenere. La proprietà deve specificata nel <xref:System.Windows.Automation.CacheRequest>.  
  
2.  Chiamare <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A>, o recuperare il <xref:System.Windows.Automation.AutomationElement.Cached%2A> struttura di proprietà e ottenere il valore da uno dei relativi membri.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente illustra vari modi per recuperare le proprietà correnti di un <xref:System.Windows.Automation.AutomationElement>.  
  
 [!code-csharp[UIAClient_snip#170](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#170)]
 [!code-vb[UIAClient_snip#170](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#170)]  
  
## <a name="see-also"></a>Vedere anche  
 [Proprietà di automazione interfaccia utente per i client](../../../docs/framework/ui-automation/ui-automation-properties-for-clients.md)  
 [Usare la memorizzazione nella cache in automazione interfaccia utente](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)  
 [Memorizzazione nella cache di client di automazione interfaccia utente](../../../docs/framework/ui-automation/caching-in-ui-automation-clients.md)
