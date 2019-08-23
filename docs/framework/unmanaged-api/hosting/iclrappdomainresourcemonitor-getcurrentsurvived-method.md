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
ms.openlocfilehash: bf285b6e1f703c8776937fa33c7ab5801f04f80f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69950154"
---
# <a name="iclrappdomainresourcemonitorgetcurrentsurvived-method"></a>Metodo ICLRAppDomainResourceMonitor::GetCurrentSurvived
Ottiene il numero di byte esclusi dall'ultimo blocco completo Garbage Collection e a cui fa riferimento il dominio applicazione corrente.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT STDMETHODCALLTYPE GetCurrentSurvived(  
             [in]  DWORD dwAppDomainId,  
             [out] ULONGLONG *pAppDomainBytesSurvived,  
             [out] ULONGLONG *pTotalBytesSurvived);  
```  
  
## <a name="parameters"></a>Parametri  
 `dwAppDomainId`  
 in ID del dominio applicazione richiesto.  
  
 `pAppDomainBytesSurvived`  
 out Puntatore al numero di byte sopravvissuti dopo l'ultimo Garbage Collection mantenuto dal dominio dell'applicazione. Dopo una raccolta completa, questo numero è preciso e completo. Dopo una raccolta temporanea, questo numero è potenzialmente incompleto. Questo parametro può essere `null`.  
  
 `pRuntimeBytesSurvived`  
 out Puntatore al numero totale di byte esclusi dall'ultima Garbage Collection. Dopo una raccolta completa, questo numero rappresenta il numero di byte conservati negli heap gestiti. Dopo una raccolta temporanea, questo numero rappresenta il numero di byte mantenuti attivi in generazioni effimere. Questo parametro può essere `null`.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.  
  
|HRESULT|DESCRIZIONE|  
|-------------|-----------------|  
|S_OK|Metodo completato correttamente.|  
|COR_E_APPDOMAINUNLOADED|Il dominio applicazione è stato scaricato o non esiste.|  
  
## <a name="remarks"></a>Note  
 Le statistiche vengono aggiornate solo dopo un Garbage Collection di blocco completo; ovvero una raccolta che include tutte le generazioni e che interrompe l'applicazione mentre si verifica la raccolta. Ad esempio, l' <xref:System.GC.Collect?displayProperty=nameWithType> overload del metodo esegue una raccolta di blocco completa. Il Garbage Collection simultaneo si verifica in background e non blocca l'applicazione.  
  
 Il `GetCurrentSurvived` metodo è l'equivalente non gestito della proprietà gestita <xref:System.AppDomain.MonitoringSurvivedMemorySize%2A?displayProperty=nameWithType> .  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Metahost. h  
  
 **Libreria** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRAppDomainResourceMonitor](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)
- [Monitoraggio delle risorse del dominio dell'applicazione](../../../standard/garbage-collection/app-domain-resource-monitoring.md)
- [Interfacce di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md)
