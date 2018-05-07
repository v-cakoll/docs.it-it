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
ms.openlocfilehash: 7c179ba23be07e8ff77e1397ed753d4287b22440
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="iclrappdomainresourcemonitorgetcurrentsurvived-method"></a>Metodo ICLRAppDomainResourceMonitor::GetCurrentSurvived
Ottiene il numero di byte esclusi l'ultima procedura completa di garbage collection bloccante e che fa riferimento il dominio applicazione corrente.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT STDMETHODCALLTYPE GetCurrentSurvived(  
             [in]  DWORD dwAppDomainId,  
             [out] ULONGLONG *pAppDomainBytesSurvived,  
             [out] ULONGLONG *pTotalBytesSurvived);  
```  
  
#### <a name="parameters"></a>Parametri  
 `dwAppDomainId`  
 [in] ID del dominio di applicazione richiesto.  
  
 `pAppDomainBytesSurvived`  
 [out] Puntatore al numero di byte rimasti dopo l'ultima garbage collection vengono mantenuti attivi da questo dominio applicazione. Dopo una raccolta completa, questo numero è preciso e completo. Dopo una raccolta temporanea, questo numero è potenzialmente incompleto. Questo parametro può essere `null`.  
  
 `pRuntimeBytesSurvived`  
 [out] Puntatore al numero totale di byte rimasti dall'ultima garbage collection. Dopo una raccolta completa, questo numero rappresenta il numero di byte che vengono mantenuti attivi negli heap gestiti. Dopo una raccolta temporanea, questo numero rappresenta il numero di byte mantenuti attivi in generazioni temporanee. Questo parametro può essere `null`.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|Metodo completato correttamente.|  
|COR_E_APPDOMAINUNLOADED|Il dominio applicazione è stato scaricato o non esiste.|  
  
## <a name="remarks"></a>Note  
 Le statistiche vengono aggiornate solo dopo una procedura completa di garbage collection; bloccante ovvero, si verifica una raccolta che include tutte le generazioni e che interrompe l'applicazione durante la raccolta. Ad esempio, il <xref:System.GC.Collect?displayProperty=nameWithType> overload del metodo esegue una procedura completa di Garbage collection bloccante. Garbage collection simultanea avviene in background e non blocca l'applicazione.  
  
 Il `GetCurrentSurvived` metodo equivale a non gestito di gestito <xref:System.AppDomain.MonitoringSurvivedMemorySize%2A?displayProperty=nameWithType> proprietà.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Metahost. H  
  
 **Libreria:** inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICLRAppDomainResourceMonitor](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)  
 [Monitoraggio delle risorse del dominio dell'applicazione](../../../../docs/standard/garbage-collection/app-domain-resource-monitoring.md)  
 [Interfacce di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md)
