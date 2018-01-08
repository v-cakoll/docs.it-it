---
title: 'Mitigazione: Implementazioni IMessageFilter.PreFilterMessage personalizzate'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9cf47c5b-0bb2-45df-9437-61cd7e7c2f4d
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 38a8c3556d78431672ebeab16a3fa65e2debc0e1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="mitigation-custom-imessagefilterprefiltermessage-implementations"></a>Mitigazione: Implementazioni IMessageFilter.PreFilterMessage personalizzate
Nelle app di Windows Form destinate a versioni di .NET Framework a partire da [!INCLUDE[net_v461](../../../includes/net-v461-md.md)], un'implementazione <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType> personalizzata può filtrare in modo sicuro i messaggi quando il metodo <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> viene chiamato se l'implementazione <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType>:  
  
-   Esegue una o entrambe le opzioni seguenti:  
  
    -   Aggiunge un filtro messaggio chiamando il metodo <xref:System.Windows.Forms.Application.AddMessageFilter%2A>.  
  
    -   Rimuove un filtro messaggio chiamando il metodo <xref:System.Windows.Forms.Application.RemoveMessageFilter%2A>. ProcessOnStatus.  
  
-   **E** immette i messaggi chiamando il metodo <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=nameWithType>.  
  
## <a name="impact"></a>Impatto  
 Questa modifica riguarda solo app Windows Form destinate a versioni di .NET Framework che iniziano con [!INCLUDE[net_v461](../../../includes/net-v461-md.md)].  
  
 Per le app Windows Form destinate a versioni precedenti di .NET Framework, questo tipo di implementazioni in alcuni casi genera un'eccezione <xref:System.IndexOutOfRangeException> quando viene chiamato il metodo <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType>  
  
## <a name="mitigation"></a>Mitigazione  
 Se la modifica è indesiderata, le app destinate a [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] o versione successiva la possono rifiutare esplicitamente aggiungendo l'impostazione di configurazione seguente alla sezione [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) del file di configurazione dell'app:  
  
```xml  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.Windows.Forms.DontSupportReentrantFilterMessage=true" />   
</runtime>  
```  
  
 Le app destinate a versioni precedenti di .NET Framework ma in esecuzione su [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] o versione successiva possono optare per questo comportamento aggiungendo l'impostazione di configurazione seguente alla sezione [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) del file di configurazione dell'app:  
  
```xml  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.Windows.Forms.DontSupportReentrantFilterMessage=false" />   
</runtime>  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Modifiche di reindirizzamento](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-1.md)
