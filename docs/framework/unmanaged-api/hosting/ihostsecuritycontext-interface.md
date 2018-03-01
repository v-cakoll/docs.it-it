---
title: Interfaccia IHostSecurityContext
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IHostSecurityContext
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityContext
helpviewer_keywords:
- IHostSecurityContext interface [.NET Framework hosting]
ms.assetid: 88e2eac0-8ccb-404f-abbc-287d55159842
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 8ee464e47ad6e333b507c199e1857309f640a37b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ihostsecuritycontext-interface"></a>Interfaccia IHostSecurityContext
Consente a common language runtime (CLR) per gestire le informazioni di contesto di sicurezza implementate dall'host.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo Capture](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-capture-method.md)|Ottiene un clone di `IHostSecurityContext` istanza restituita da una chiamata a [IHostSecurityManager::](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md).|  
  
## <a name="remarks"></a>Note  
 Un host può controllare l'accesso di codice ai token di thread da codice CLR e utente. Può inoltre garantire che la sicurezza completa le informazioni di contesto viene passate attraverso operazioni asincrone o punti di codice con accesso di codice con restrizioni. `IHostSecurityContext`incapsula queste informazioni di contesto di sicurezza, che risulta opache al runtime. Il runtime acquisisce queste informazioni tramite `Capture`, e lo sposta in invio elemento di lavoro del pool di thread, esecuzione dei finalizzatori e i costruttori di modulo e la classe.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Mscoree. H  
  
 **Libreria:** inclusa come risorsa in MSCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICLRHostProtectionManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)  
 [Interfaccia IHostSecurityManager](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)  
 [Interfacce di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
