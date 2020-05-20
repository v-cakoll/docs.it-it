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
ms.openlocfilehash: b411190ff36410c1d293f1e48b31975be8a13aee
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616034"
---
# <a name="iclrappdomainresourcemonitorgetcurrentcputime-method"></a>Metodo ICLRAppDomainResourceMonitor::GetCurrentCpuTime
Ottiene il tempo totale del processore utilizzato da tutti i thread durante l'esecuzione nel dominio dell'applicazione corrente, dal momento in cui è stato creato il dominio dell'applicazione.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetCurrentCpuTime([in]  DWORD dwAppDomainId,  
                          [out] ULONGLONG* pMilliseconds);  
```  
  
## <a name="parameters"></a>Parametri  
 `dwAppDomainId`  
 in ID del dominio applicazione richiesto.  
  
 `pMilliseconds`  
 out Puntatore al tempo totale del processore utilizzato da tutti i thread durante l'esecuzione nel dominio dell'applicazione corrente dopo la creazione del dominio dell'applicazione. Questo parametro può essere `null`.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Description|  
|-------------|-----------------|  
|S_OK|Metodo completato correttamente.|  
|COR_E_APPDOMAINUNLOADED|Il dominio applicazione è stato scaricato o non esiste.|  
|E_FAIL|Il monitoraggio delle risorse del dominio applicazione non è abilitato.<br /><br /> -oppure-<br /><br /> Tutti gli altri errori.|  
  
## <a name="remarks"></a>Osservazioni  
 Questo metodo è l'equivalente non gestito della <xref:System.AppDomain.MonitoringTotalProcessorTime%2A?displayProperty=nameWithType> proprietà gestita.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Metahost. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRAppDomainResourceMonitor](iclrappdomainresourcemonitor-interface.md)
- [Interfacce di hosting](hosting-interfaces.md)
- [Monitoraggio delle risorse del dominio applicazione](../../../standard/garbage-collection/app-domain-resource-monitoring.md)
- [Hosting](index.md)
