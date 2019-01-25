---
title: Interfaccia IHostSecurityContext
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 29499301260313ab796eee2be06a168f2ae48e4e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54712116"
---
# <a name="ihostsecuritycontext-interface"></a>Interfaccia IHostSecurityContext
Consente a common language runtime (CLR) per gestire le informazioni di contesto di sicurezza implementate dall'host.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo Capture](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-capture-method.md)|Ottiene un clone del `IHostSecurityContext` istanza restituita da una chiamata a [IHostSecurityManager](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md).|  
  
## <a name="remarks"></a>Note  
 Un host può controllare tutti gli accessi di codice ai token di thread da codice CLR e utente. Inoltre possibile garantire che la sicurezza completa le informazioni di contesto viene passate attraverso operazioni asincrone o punti di codice con l'accesso al codice con restrizioni. `IHostSecurityContext` incapsula questo informazioni sul contesto di sicurezza, che risulta opachi al runtime. Il runtime consente di acquisire queste informazioni usando `Capture`, e lo sposta in invio elemento di lavoro del pool di thread, l'esecuzione del finalizzatore e costruttori di classe e modulo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE.h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia ICLRHostProtectionManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)
- [Interfaccia IHostSecurityManager](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
- [Interfacce di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
