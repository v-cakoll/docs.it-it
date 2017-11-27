---
title: Coclasse CorRuntimeHost
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorRuntimeHost Coclass
api_location: mscoree.dll
api_type: COM
f1_keywords: CorRuntimeHost
helpviewer_keywords: CoRuntimeHost coclass [.NET Framework hosting]
ms.assetid: 5833740b-7d67-44b4-865c-b5bf45e291e3
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3d7a272aff3a3c7d32042b76d37fdb15c9dcad4d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="corruntimehost-coclass"></a>Coclasse CorRuntimeHost
Fornisce interfacce per la gestione delle applicazioni che vengono eseguite da common language runtime.  
  
## <a name="syntax"></a>Sintassi  
  
```  
coclass CorRuntimeHost {  
    [default] interface ICorRuntimeHost;  
    interface IGCHost;  
    interface ICorConfiguration;  
    interface IValidator;  
    interface IDebuggerInfo;  
};  
```  
  
## <a name="interfaces"></a>Interfacce  
  
|Interfaccia|Descrizione|  
|---------------|-----------------|  
|[ICorConfiguration (interfaccia)](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)|Fornisce metodi per la configurazione di common language runtime (CLR).|  
|[ICorRuntimeHost (interfaccia)](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)|Fornisce metodi che consentono all'host avviare e arrestare in modo esplicito, common language runtime per creare e configurare i domini applicazione, per accedere al dominio predefinito e per enumerare tutti i domini in esecuzione nel processo.|  
|[IDebuggerInfo (interfaccia)](../../../../docs/framework/unmanaged-api/hosting/idebuggerinfo-interface.md)|Fornisce metodi per ottenere informazioni sullo stato dei servizi di debug.|  
|[IGCHost (interfaccia)](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)|Fornisce metodi per ottenere informazioni sul sistema di garbage collection e per controllare alcuni aspetti dell'operazione di garbage collection.|  
|"IValidator"|Fornisce metodi per la convalida delle immagini di tipo PE e la creazione di report dettagliati di errori di convalida.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Mscoree  
  
 **Libreria:** inclusa come risorsa in MSCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Coclassi di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)
