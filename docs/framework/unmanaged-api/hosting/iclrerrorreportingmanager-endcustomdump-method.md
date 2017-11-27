---
title: Metodo ICLRErrorReportingManager::EndCustomDump
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRErrorReportingManager.EndCustomDump
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRErrorReportingManager::EndCustomDump
helpviewer_keywords:
- ICLRErrorReportingManager::EndCustomDump method [.NET Framework hosting]
- EndCustomDump method [.NET Framework hosting]
ms.assetid: 88a5da04-8729-4108-82c4-af206a7d483e
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 059ab01d3cc05bac84bb1a4cd8fffc7fc259ed60
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="iclrerrorreportingmanagerendcustomdump-method"></a>Metodo ICLRErrorReportingManager::EndCustomDump
Rimuove la configurazione di dump dello stack personalizzati che è stata specificata in una chiamata precedente al [ICLRErrorReportingManager:: BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) metodo.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT EndCustomDump ();  
```  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|`EndCustomDump`stato restituito correttamente.|  
|HOST_E_CLRNOTAVAILABLE|Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non dispone del blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Se un metodo restituisce E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Note  
 Il `EndCustomDump` metodo cancella la configurazione di dump dello stack personalizzati impostata da una precedente chiamata al `BeginCustomDump` metodo e rilascia qualsiasi stato associato. Deve essere chiamato dopo il dump dello stack personalizzati è stato completato.  
  
> [!IMPORTANT]
>  Errore durante la chiamata `EndCustomDump` provoca perdita di memoria.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Mscoree. H  
  
 **Libreria:** inclusa come risorsa in MSCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [CustomDumpItem (struttura)](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md)  
 [ECustomDumpFlavor (enumerazione)](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpflavor-enumeration.md)  
 [ICLRErrorReportingManager (interfaccia)](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
