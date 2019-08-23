---
title: Implementare i provider di automazione interfaccia utente in un'applicazione client
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- client-side UI Automation provider, implementation within applications
- UI Automation, implementing client-side provider within application
ms.assetid: f325f0d8-1715-41ea-85ca-45b82ffea8bc
ms.openlocfilehash: ef3d03bee412b97ed88ec76e81ad2fd19a9595eb
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968956"
---
# <a name="implement-ui-automation-providers-in-a-client-application"></a>Implementare i provider di automazione interfaccia utente in un'applicazione client
> [!NOTE]
> Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>. Per informazioni aggiornate su, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]vedere [API di automazione di Windows: Automazione](https://go.microsoft.com/fwlink/?LinkID=156746)interfaccia utente.  
  
 Questo argomento contiene codice di esempio che illustra come implementare un provider di automazione interfaccia utente sul lato client all'interno di un'applicazione.  
  
 Si tratta di uno scenario comune. In genere, un'applicazione client di automazione interfaccia utente usa provider lato server oppure provider lato client che si trovano in una DLL.  
  
## <a name="example"></a>Esempio  
 L'esempio di codice seguente implementa un provider semplice per una finestra della console. Il codice non dispone di funzionalità utili, ma intende illustrare i passaggi di base dell'impostazione di un provider all'interno del codice client e della registrazione mediante <xref:System.Windows.Automation.ClientSettings.RegisterClientSideProviders%2A>.  
  
 [!code-csharp[UIAClientSideProvider_snip#201](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClientSideProvider_snip/CSharp/ClientImplementationProgram.cs#201)]
 [!code-vb[UIAClientSideProvider_snip#201](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClientSideProvider_snip/visualbasic/clientimplementationprogram.vb#201)]  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica dei provider di automazione interfaccia utente](../../../docs/framework/ui-automation/ui-automation-providers-overview.md)
- [Registrare un assembly di provider lato client](../../../docs/framework/ui-automation/register-a-client-side-provider-assembly.md)
- [Creare un provider di automazione interfaccia utente lato client](../../../docs/framework/ui-automation/create-a-client-side-ui-automation-provider.md)
- [Implementazione dei provider di automazione interfaccia utente lato client](../../../docs/framework/ui-automation/client-side-ui-automation-provider-implementation.md)
