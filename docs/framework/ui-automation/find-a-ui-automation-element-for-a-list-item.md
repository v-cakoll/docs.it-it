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
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: b569b43d83e8a7f1b0fa82b79bc1fc40977b72ba
ms.sourcegitcommit: 3ab9254890a52a50762995fa6d7d77a00348db7e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2018
ms.locfileid: "46479440"
---
# <a name="find-a-ui-automation-element-for-a-list-item"></a>Trovare un elemento di automazione interfaccia utente per l'elemento di un elenco
> [!NOTE]
>  Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>. Per informazioni aggiornate sulle [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere [Windows Automation API: automazione dell'interfaccia utente](https://go.microsoft.com/fwlink/?LinkID=156746).  
  
 Questo argomento viene illustrato come recuperare un <xref:System.Windows.Automation.AutomationElement> per un elemento all'interno di un elenco quando si conosce l'indice dell'elemento.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente illustra due modalità di recupero di un elemento specificato da un elenco, uno usando <xref:System.Windows.Automation.TreeWalker> e l'altro uso <xref:System.Windows.Automation.AutomationElement.FindAll%2A>.  
  
 La prima tecnica tende a essere più veloce per [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] controlli, mentre la seconda è più veloce per i controlli Windows Presentation Foundation (WPF).  
  
 [!code-csharp[UIAClient_snip#184](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#184)]
 [!code-vb[UIAClient_snip#184](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#184)]  
  
## <a name="see-also"></a>Vedere anche  
 [Ottenere elementi di automazione interfaccia utente](../../../docs/framework/ui-automation/obtaining-ui-automation-elements.md)
