---
title: Creare un provider di automazione interfaccia utente lato client
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UI Automation, creating client-side provider
- client-side UI Automation provider, creating
ms.assetid: d91edaf2-be28-41ec-a508-af421cb43c3d
caps.latest.revision: "11"
author: Xansky
ms.author: mhopkins
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 6b788d679d29a9af838b91c7b4468e10a1a8411e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="create-a-client-side-ui-automation-provider"></a>Creare un provider di automazione interfaccia utente lato client
> [!NOTE]
>  Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>. Per informazioni aggiornate su [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere l'argomento sull' [API Automazione interfaccia utente di Windows](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 Questo argomento contiene codice di esempio che illustra come implementare un provider di automazione interfaccia utente sul lato client.  
  
## <a name="example"></a>Esempio  
 L'esempio di codice seguente può essere compilato in una [!INCLUDE[TLA#tla_dll](../../../includes/tlasharptla-dll-md.md)] che implementa un provider lato client molto semplice per una finestra della console. Il codice non dispone di funzionalità utili, ma intende illustrare i passaggi di base dell'impostazione di un assembly di provider che può essere registrato da un'applicazione client di automazione interfaccia utente.  
  
 [!code-csharp[UIAClientSideProvider_snip#101](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClientSideProvider_snip/CSharp/CSProviderProgram.cs#101)]
 [!code-vb[UIAClientSideProvider_snip#101](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClientSideProvider_snip/visualbasic/csproviderprogram.vb#101)]  
  
## <a name="see-also"></a>Vedere anche  
 [Panoramica dei provider di automazione interfaccia utente](../../../docs/framework/ui-automation/ui-automation-providers-overview.md)  
 [Registrare un assembly di provider lato client](../../../docs/framework/ui-automation/register-a-client-side-provider-assembly.md)
