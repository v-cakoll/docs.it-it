---
title: Interfaccia IHostControl
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostControl
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostControl
helpviewer_keywords: IHostControl interface [.NET Framework hosting]
ms.assetid: a4ae0d1f-ade9-4b0a-a122-93ed11a5e6b3
topic_type: apiref
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7e72ad562a73faf5682204c2ae2583b71cb3c05e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ihostcontrol-interface"></a>Interfaccia IHostControl
Fornisce metodi per la configurazione del caricamento degli assembly e per determinare quali hosting interfacce host supporta.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[GetHostManager (metodo)](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md)|Ottiene un puntatore a interfaccia per l'implementazione dell'host dell'interfaccia con l'oggetto specificato `IID`.|  
|[SetAppDomainManager (metodo)](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-setappdomainmanager-method.md)|Notifica all'host che è stato creato un dominio applicazione.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Mscoree. H  
  
 **Libreria:** inclusa come risorsa in MSCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.AppDomainManager>  
 [ICLRRuntimeHost (interfaccia)](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)  
 [ICLRControl (interfaccia)](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [Interfacce di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
