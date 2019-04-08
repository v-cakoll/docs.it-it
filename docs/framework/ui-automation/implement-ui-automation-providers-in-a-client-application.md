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
ms.openlocfilehash: b368ab3bc842fda5a99a64e0220093ebd60698b0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59105924"
---
# <a name="implement-ui-automation-providers-in-a-client-application"></a>Implementare i provider di automazione interfaccia utente in un'applicazione client
> [!NOTE]
>  Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>. Per informazioni aggiornate sulle [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere [Windows Automation API: Automazione interfaccia utente](https://go.microsoft.com/fwlink/?LinkID=156746).  
  
 Questo argomento contiene codice di esempio che illustra come implementare un provider di automazione interfaccia utente sul lato client all'interno di un'applicazione.  
  
 Si tratta di uno scenario comune. In genere, un'applicazione client di automazione interfaccia utente usa provider lato server oppure provider lato client che si trovano in una DLL.  
  
## <a name="example"></a>Esempio  
 L'esempio di codice seguente implementa un provider semplice per una finestra della console. Il codice non dispone di funzionalità utili, ma intende illustrare i passaggi di base dell'impostazione di un provider all'interno del codice client e della registrazione mediante <xref:System.Windows.Automation.ClientSettings.RegisterClientSideProviders%2A>.  
  
 [!code-csharp[UIAClientSideProvider_snip#201](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClientSideProvider_snip/CSharp/ClientImplementationProgram.cs#201)]
 [!code-vb[UIAClientSideProvider_snip#201](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClientSideProvider_snip/visualbasic/clientimplementationprogram.vb#201)]  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sui provider di automazione interfaccia utente](../../../docs/framework/ui-automation/ui-automation-providers-overview.md)
- [Registrare un assembly di provider lato client](../../../docs/framework/ui-automation/register-a-client-side-provider-assembly.md)
- [Creare un provider di automazione interfaccia utente lato client](../../../docs/framework/ui-automation/create-a-client-side-ui-automation-provider.md)
- [Implementazione dei provider di automazione interfaccia utente sul lato client](../../../docs/framework/ui-automation/client-side-ui-automation-provider-implementation.md)
