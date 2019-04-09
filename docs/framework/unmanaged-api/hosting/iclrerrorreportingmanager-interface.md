---
title: Interfaccia ICLRErrorReportingManager
ms.date: 03/30/2017
api_name:
- ICLRErrorReportingManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRErrorReportingManager
helpviewer_keywords:
- ICLRErrorReportingManager interface [.NET Framework hosting]
ms.assetid: ea8af0d5-4133-4472-8a1f-50570d7e85fa
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a20b79dd5eda9c431511cc49e7e3adaa9486b2aa
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59155987"
---
# <a name="iclrerrorreportingmanager-interface"></a>Interfaccia ICLRErrorReportingManager
Fornisce metodi che consentono all'host configurare i dump dello stack personalizzati per segnalazione errori.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md)|Specifica la configurazione di dump dello stack personalizzati per la segnalazione errori.|  
|[Metodo EndCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-endcustomdump-method.md)|Cancella la configurazione dump dello stack personalizzati che è stata impostata da una precedente chiamata a `BeginCustomDump`.|  
|[Metodo GetBucketParametersForCurrentException](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-getbucketparametersforcurrentexception-method.md)|Ottiene il bucket Watson per l'eccezione corrente nel thread chiamante.|  
  
## <a name="remarks"></a>Note  
 Il `BeginCustomDump` metodo imposta la configurazione dump dello stack personalizzati. Il `EndCustomDump` metodo cancella la configurazione dump dello stack personalizzati e rilascia qualsiasi stato associato. Deve essere chiamato dopo che il dump personalizzato è stato completato.  
  
> [!IMPORTANT]
>  Errore durante la chiamata `EndCustomDump` provoca perdita di memoria.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE.h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazione ECustomDumpItemKind](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md)
- [Interfacce di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
