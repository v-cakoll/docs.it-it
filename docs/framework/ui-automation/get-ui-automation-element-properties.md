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
ms.openlocfilehash: 158ebf29bb504dd11f9e8416011226fc5846873e
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2019
ms.locfileid: "71043609"
---
# <a name="get-ui-automation-element-properties"></a>Ottenere le proprietà degli elementi di automazione dell'interfaccia utente
> [!NOTE]
> Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>. Per informazioni aggiornate su, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]vedere [API di automazione di Windows: Automazione](https://go.microsoft.com/fwlink/?LinkID=156746)interfaccia utente.  
  
 In questo argomento viene illustrato come recuperare le proprietà [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] di un elemento.  
  
### <a name="get-a-current-property-value"></a>Ottenere un valore della proprietà corrente  
  
1. Ottenere l' <xref:System.Windows.Automation.AutomationElement> oggetto di cui si desidera ottenere la proprietà.  
  
2. Chiamare <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A>o recuperare la <xref:System.Windows.Automation.AutomationElement.Current%2A> struttura di proprietà e ottenere il valore da uno dei relativi membri.  
  
### <a name="get-a-cached-property-value"></a>Ottenere un valore della proprietà memorizzato nella cache  
  
1. Ottenere l' <xref:System.Windows.Automation.AutomationElement> oggetto di cui si desidera ottenere la proprietà. È necessario specificare la proprietà in <xref:System.Windows.Automation.CacheRequest>.  
  
2. Chiamare <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A>o recuperare la <xref:System.Windows.Automation.AutomationElement.Cached%2A> struttura di proprietà e ottenere il valore da uno dei relativi membri.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente vengono illustrati vari modi per recuperare le proprietà <xref:System.Windows.Automation.AutomationElement>correnti di un oggetto.  
  
 [!code-csharp[UIAClient_snip#170](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#170)]
 [!code-vb[UIAClient_snip#170](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#170)]  
  
## <a name="see-also"></a>Vedere anche

- [Proprietà di automazione interfaccia utente per i client](ui-automation-properties-for-clients.md)
- [Usare la memorizzazione nella cache in automazione interfaccia utente](use-caching-in-ui-automation.md)
- [Memorizzazione nella cache di client di automazione interfaccia utente](caching-in-ui-automation-clients.md)
