---
title: Generare eventi da un provider di automazione interfaccia utente
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, raising events
- raising UI Automation events
ms.assetid: 9fe2f01b-f7d8-49a8-a185-d4472b9976c0
ms.openlocfilehash: ac351678607be824558506f7d65a5a8f6bda5a12
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/08/2019
ms.locfileid: "57674738"
---
# <a name="raise-events-from-a-ui-automation-provider"></a>Generare eventi da un provider di automazione interfaccia utente
> [!NOTE]
>  Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>. Per informazioni aggiornate sulle [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere [Windows Automation API: Automazione interfaccia utente](https://go.microsoft.com/fwlink/?LinkID=156746).  
  
 Questo argomento contiene il codice di esempio che mostra come generare un evento da un provider di automazione interfaccia utente.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene generato un evento [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] durante l'implementazione di un pulsante personalizzato. L'implementazione consente a un'applicazione client di automazione interfaccia utente di simulare il clic di un pulsante.  
  
 Per evitare un'elaborazione non necessaria, l'esempio controlla <xref:System.Windows.Automation.Provider.AutomationInteropProvider.ClientsAreListening%2A> per verificare se devono essere generati eventi.  
  
 [!code-csharp[UIAProvider_snip#150](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAProvider_snip/CSharp/FragmentRoot.cs#150)]  
  
## <a name="see-also"></a>Vedere anche
- [Panoramica dei provider di automazione interfaccia utente](../../../docs/framework/ui-automation/ui-automation-providers-overview.md)
