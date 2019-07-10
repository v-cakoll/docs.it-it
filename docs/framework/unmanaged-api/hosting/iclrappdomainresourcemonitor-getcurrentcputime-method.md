---
title: Metodo ICLRAppDomainResourceMonitor::GetCurrentCpuTime
ms.date: 03/30/2017
api_name:
- ICLRAppDomainResourceMonitor.GetCurrentCpuTime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAppDomainResourceMonitor::GetCurrentCpuTime
helpviewer_keywords:
- ICLRAppDomainResourceMonitor::GetCurrentCpuTime method [.NET Framework hosting]
- GetCurrentCpuTime method [.NET Framework hosting]
ms.assetid: ebc9cc33-fcd6-4cae-9ecb-ea21c51874e6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4d5149c7e3430c5e7c59a47c4ab5dc98d878de39
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67766672"
---
# <a name="iclrappdomainresourcemonitorgetcurrentcputime-method"></a>Metodo ICLRAppDomainResourceMonitor::GetCurrentCpuTime
Ottiene il tempo processore totale che è stato usato da tutti i thread durante l'esecuzione nel dominio dell'applicazione corrente, poiché è stato creato il dominio dell'applicazione.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetCurrentCpuTime([in]  DWORD dwAppDomainId,  
                          [out] ULONGLONG* pMilliseconds);  
```  
  
## <a name="parameters"></a>Parametri  
 `dwAppDomainId`  
 [in] L'ID del dominio dell'applicazione richiesta.  
  
 `pMilliseconds`  
 [out] Un puntatore per il tempo processore totale che è stato usato da tutti i thread durante l'esecuzione nel dominio applicazione corrente poiché è stato creato il dominio dell'applicazione. Questo parametro può essere `null`.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|Metodo completato correttamente.|  
|COR_E_APPDOMAINUNLOADED|Il dominio dell'applicazione è stato scaricato o non esiste.|  
|E_FAIL|Monitoraggio delle risorse del dominio applicazione non è abilitato.<br /><br /> -oppure-<br /><br /> Tutti gli altri errori.|  
  
## <a name="remarks"></a>Note  
 Questo metodo è l'equivalente gestito di gestita <xref:System.AppDomain.MonitoringTotalProcessorTime%2A?displayProperty=nameWithType> proprietà.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MetaHost.h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRAppDomainResourceMonitor](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)
- [Interfacce di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [Monitoraggio delle risorse del dominio dell'applicazione](../../../../docs/standard/garbage-collection/app-domain-resource-monitoring.md)
- [Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md)
