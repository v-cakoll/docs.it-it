---
title: Metodo ICLRAppDomainResourceMonitor::GetCurrentSurvived
ms.date: 03/30/2017
api_name:
- ICLRAppDomainResourceMonitor.GetCurrentSurvived
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAppDomainResourceMonitor::GetCurrentSurvived
helpviewer_keywords:
- ICLRAppDomainResourceMonitor::GetCurrentSurvived method [.NET Framework hosting]
- GetCurrentSurvived method [.NET Framework hosting]
ms.assetid: 392e9009-40ef-40e3-ad4d-7ce93a989e78
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 408ef5419fbc2081d25ad442986ec8155bcb4c62
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59141544"
---
# <a name="iclrappdomainresourcemonitorgetcurrentsurvived-method"></a>Metodo ICLRAppDomainResourceMonitor::GetCurrentSurvived
Ottiene il numero di byte esclusi dall'ultima completa di garbage collection di blocco e che fa riferimento il dominio applicazione corrente.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT STDMETHODCALLTYPE GetCurrentSurvived(  
             [in]  DWORD dwAppDomainId,  
             [out] ULONGLONG *pAppDomainBytesSurvived,  
             [out] ULONGLONG *pTotalBytesSurvived);  
```  
  
## <a name="parameters"></a>Parametri  
 `dwAppDomainId`  
 [in] L'ID del dominio dell'applicazione richiesta.  
  
 `pAppDomainBytesSurvived`  
 [out] Puntatore al numero di byte rimasti dopo l'ultima garbage collection che vengono mantenuti attivi da questo dominio applicazione. Dopo una raccolta completa, questo numero è preciso e completo. Dopo una raccolta temporanea, questo numero è potenzialmente incompleto. Questo parametro può essere `null`.  
  
 `pRuntimeBytesSurvived`  
 [out] Puntatore al numero totale di byte rimasti dall'ultima garbage collection. Dopo una raccolta completa, questo numero rappresenta il numero di byte che vengono mantenuti attivi negli heap gestiti. Dopo una raccolta temporanea, questo numero rappresenta il numero di byte mantenuti attivi in generazioni temporanee. Questo parametro può essere `null`.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|Metodo completato correttamente.|  
|COR_E_APPDOMAINUNLOADED|Il dominio dell'applicazione è stato scaricato o non esiste.|  
  
## <a name="remarks"></a>Note  
 Le statistiche vengono aggiornate solo dopo una procedura completa di blocco della garbage collection; vale a dire, si verifica una raccolta che include tutte le generazioni e che l'applicazione durante la raccolta viene arrestata. Ad esempio, il <xref:System.GC.Collect?displayProperty=nameWithType> overload del metodo esegue una procedura completa di Garbage collection di blocco. Garbage collection simultanea avviene in background e non blocca l'applicazione.  
  
 Il `GetCurrentSurvived` metodo è l'equivalente gestito di managed <xref:System.AppDomain.MonitoringSurvivedMemorySize%2A?displayProperty=nameWithType> proprietà.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MetaHost.h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRAppDomainResourceMonitor](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)
- [Monitoraggio delle risorse del dominio dell'applicazione](../../../../docs/standard/garbage-collection/app-domain-resource-monitoring.md)
- [Interfacce di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md)
