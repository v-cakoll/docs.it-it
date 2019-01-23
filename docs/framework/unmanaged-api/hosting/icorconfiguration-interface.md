---
title: Interfaccia ICorConfiguration
ms.date: 03/30/2017
api_name:
- ICorConfiguration
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorConfiguration
helpviewer_keywords:
- ICorConfiguration interface [.NET Framework hosting]
ms.assetid: aaf96116-372b-4538-afb1-9e0fcdac1f98
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2d7abd6b4ca97173cfecbabf1a8b90afcf3c48a1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54554179"
---
# <a name="icorconfiguration-interface"></a>Interfaccia ICorConfiguration
Fornisce metodi per la configurazione di common language runtime (CLR).  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo AddDebuggerSpecialThread](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-adddebuggerspecialthread-method.md)|Indica che un thread specifico deve essere consentito di continuare l'esecuzione mentre il debugger ha un'applicazione arrestata durante gli scenari di debug gestiti o per i servizi di debug.|  
|[Metodo SetDebuggerThreadControl](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-setdebuggerthreadcontrol-method.md)|Imposta l'interfaccia di callback che i servizi di debug verranno chiamato come thread del CLR viene bloccato e sbloccato per eseguire il debug.|  
|[Metodo SetGCHostControl](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-setgchostcontrol-method.md)|Imposta l'interfaccia di callback per essere utilizzata dal garbage collector per richiedere l'host per modificare i limiti di memoria virtuale.|  
|[Metodo SetGCThreadControl](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-setgcthreadcontrol-method.md)|Imposta l'interfaccia di callback per la pianificazione dei thread per le attività non di runtime che verrebbe bloccate in caso contrario, per una garbage collection.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE.h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Interfacce di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [Coclasse CorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
