---
title: Interfaccia IDebuggerThreadControl
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IDebuggerThreadControl
api_location: mscoree.dll
api_type: COM
f1_keywords: IDebuggerThreadControl
helpviewer_keywords: IDebuggerThreadControl interface [.NET Framework hosting]
ms.assetid: 0a270c42-a7d1-45f1-a64d-fa3e84d14532
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7e3f8d04a47607958ff5d439b501a6de9bbc5b02
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="idebuggerthreadcontrol-interface"></a>Interfaccia IDebuggerThreadControl
Fornisce metodi per notificare all'host di blocco e sblocco dei thread per i servizi di debug.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[ThreadIsBlockingForDebugger (metodo)](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-threadisblockingfordebugger-method.md)|Notifica all'host che il thread che ha inviato questo callback sta per bloccare nei servizi di debug.|  
|[ReleaseAllRuntimeThreads (metodo)](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-releaseallruntimethreads-method.md)|Notifica all'host che i servizi di debug stanno per rilasciare tutti i thread sono bloccati.|  
|[StartBlockingForDebugger (metodo)](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-startblockingfordebugger-method.md)|Notifica all'host che i servizi di debug stanno per avviare il blocco di tutti i thread.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Mscoree. H  
  
 **Libreria:** inclusa come risorsa in MSCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfacce di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
