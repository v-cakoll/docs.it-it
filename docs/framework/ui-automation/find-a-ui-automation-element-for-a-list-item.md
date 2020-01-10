---
title: Trovare un elemento di automazione interfaccia utente per l'elemento di un elenco
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- list items, finding elements for
- elements, finding for list items
- UI Automation, finding elements for List items
ms.assetid: c326ad2b-2144-4f64-ae4c-d850c74f95c5
ms.openlocfilehash: 2474edf95bf598ba9284b5f6ac36a9e0af1317a1
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "75741750"
---
# <a name="find-a-ui-automation-element-for-a-list-item"></a>Trovare un elemento di automazione interfaccia utente per l'elemento di un elenco
> [!NOTE]
> Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>. Per informazioni aggiornate su [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere [Windows Automation API: automazione interfaccia utente](/windows/win32/winauto/entry-uiauto-win32).  
  
 In questo argomento viene illustrato come recuperare una <xref:System.Windows.Automation.AutomationElement> per un elemento all'interno di un elenco quando l'indice dell'elemento è noto.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente vengono illustrate due modalità di recupero di un elemento specificato da un elenco, una utilizzando <xref:System.Windows.Automation.TreeWalker> e l'altra utilizzando <xref:System.Windows.Automation.AutomationElement.FindAll%2A>.  
  
 La prima tecnica tende a essere più veloce per i controlli Win32, ma la seconda è più veloce per i controlli Windows Presentation Foundation (WPF).  
  
 [!code-csharp[UIAClient_snip#184](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#184)]
 [!code-vb[UIAClient_snip#184](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#184)]  
  
## <a name="see-also"></a>Vedere anche

- [Ottenere elementi di automazione interfaccia utente](obtaining-ui-automation-elements.md)
