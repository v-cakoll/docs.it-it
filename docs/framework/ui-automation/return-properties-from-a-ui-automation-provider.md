---
title: Restituire proprietà da un provider di automazione interfaccia utente
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- providers, UI Automation, returning properties
- properties, returned by UI Automation providers
- UI Automation, providers returning properties
ms.assetid: 5eba950e-b9e1-48eb-ab8e-b69db76bf589
author: Xansky
ms.author: mhopkins
ms.openlocfilehash: ac5d539f99fe4f7a20d9030986120318840801bb
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2018
ms.locfileid: "47107948"
---
# <a name="return-properties-from-a-ui-automation-provider"></a>Restituire proprietà da un provider di automazione interfaccia utente
> [!NOTE]
>  Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>. Per informazioni aggiornate sulle [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere [Windows Automation API: automazione dell'interfaccia utente](https://go.microsoft.com/fwlink/?LinkID=156746).  
  
 Questo argomento contiene codice di esempio che illustra come un provider di automazione interfaccia utente può restituire le proprietà di un elemento alle applicazioni client.  
  
 Per qualsiasi proprietà non supportata in modo esplicito, il provider deve restituire `null` (`Nothing` in Visual Basic). In questo modo [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tenta di ottenere la proprietà da un'altra origine, ad esempio il provider della finestra host.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[UIAFragmentProvider_snip#117](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAFragmentProvider_snip/CSharp/ListFragment.cs#117)]
 [!code-vb[UIAFragmentProvider_snip#117](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAFragmentProvider_snip/VisualBasic/ListFragment.vb#117)]  
  
## <a name="see-also"></a>Vedere anche  
 [Panoramica dei provider di automazione interfaccia utente](../../../docs/framework/ui-automation/ui-automation-providers-overview.md)  
 [Implementazione del provider di automazione interfaccia utente lato server](../../../docs/framework/ui-automation/server-side-ui-automation-provider-implementation.md)
