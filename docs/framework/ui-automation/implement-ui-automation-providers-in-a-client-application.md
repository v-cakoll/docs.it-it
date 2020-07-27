---
title: Implementare i provider di automazione interfaccia utente in un'applicazione client
description: Vedere un esempio di come implementare un provider di automazione interfaccia utente lato client in un'applicazione. Si noti che si tratta di uno scenario non comune.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- client-side UI Automation provider, implementation within applications
- UI Automation, implementing client-side provider within application
ms.assetid: f325f0d8-1715-41ea-85ca-45b82ffea8bc
ms.openlocfilehash: c604b68021886abdf06360bfb8afefe3640c12fe
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87164115"
---
# <a name="implement-ui-automation-providers-in-a-client-application"></a>Implementare i provider di automazione interfaccia utente in un'applicazione client
> [!NOTE]
> Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>. Per informazioni aggiornate su [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere [Windows Automation API: automazione interfaccia utente](/windows/win32/winauto/entry-uiauto-win32).  
  
 Questo argomento contiene codice di esempio che illustra come implementare un provider di automazione interfaccia utente sul lato client all'interno di un'applicazione.  
  
 Si tratta di uno scenario comune. In genere, un'applicazione client di automazione interfaccia utente usa provider lato server oppure provider lato client che si trovano in una DLL.  
  
## <a name="example"></a>Esempio  
 L'esempio di codice seguente implementa un provider semplice per una finestra della console. Il codice non dispone di funzionalità utili, ma intende illustrare i passaggi di base dell'impostazione di un provider all'interno del codice client e della registrazione mediante <xref:System.Windows.Automation.ClientSettings.RegisterClientSideProviders%2A>.  
  
 [!code-csharp[UIAClientSideProvider_snip#201](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClientSideProvider_snip/CSharp/ClientImplementationProgram.cs#201)]
 [!code-vb[UIAClientSideProvider_snip#201](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClientSideProvider_snip/visualbasic/clientimplementationprogram.vb#201)]  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sui provider di automazione interfaccia utente](ui-automation-providers-overview.md)
- [Registrare un assembly di provider lato client](register-a-client-side-provider-assembly.md)
- [Creare un provider di automazione interfaccia utente lato client](create-a-client-side-ui-automation-provider.md)
- [Implementazione dei provider di automazione interfaccia utente sul lato client](client-side-ui-automation-provider-implementation.md)
