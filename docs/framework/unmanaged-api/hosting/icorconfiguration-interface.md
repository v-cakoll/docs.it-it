---
title: Interfaccia ICorConfiguration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorConfiguration
api_location: mscoree.dll
api_type: COM
f1_keywords: ICorConfiguration
helpviewer_keywords: ICorConfiguration interface [.NET Framework hosting]
ms.assetid: aaf96116-372b-4538-afb1-9e0fcdac1f98
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6bc66abf28e90d858d993bd62e9c67f840af137b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icorconfiguration-interface"></a>Interfaccia ICorConfiguration
Fornisce metodi per la configurazione di common language runtime (CLR).  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[AddDebuggerSpecialThread (metodo)](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-adddebuggerspecialthread-method.md)|Indica che un determinato thread dovrebbe poter continuare l'esecuzione mentre il debugger ha un'applicazione è stata arrestata durante gli scenari di debug gestiti o ai servizi di debug.|  
|[SetDebuggerThreadControl (metodo)](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-setdebuggerthreadcontrol-method.md)|Imposta l'interfaccia di callback che i servizi di debug verranno chiamato quando i thread CLR sono bloccati e non bloccato per il debug.|  
|[SetGCHostControl (metodo)](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-setgchostcontrol-method.md)|Imposta l'interfaccia di callback per essere utilizzata dal garbage collector per richiedere all'host di modificare i limiti di memoria virtuale.|  
|[SetGCThreadControl (metodo)](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-setgcthreadcontrol-method.md)|Imposta l'interfaccia di callback per la pianificazione di thread per l'attività non è una fase di esecuzione che altrimenti sarebbero bloccati per una garbage collection.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Mscoree. H  
  
 **Libreria:** inclusa come risorsa in MSCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfacce di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [Coclasse CorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
