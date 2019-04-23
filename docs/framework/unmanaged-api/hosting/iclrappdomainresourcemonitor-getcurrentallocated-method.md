---
title: Metodo ICLRAppDomainResourceMonitor::GetCurrentAllocated
ms.date: 03/30/2017
api_name:
- ICLRAppDomainResourceMonitor.GetCurrentAllocated
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAppDomainResourceMonitor::GetCurrentAllocated
helpviewer_keywords:
- GetCurrentAllocated method [.NET Framework hosting]
- ICLRAppDomainResourceMonitor::GetCurrentAllocated method [.NET Framework hosting]
ms.assetid: 7bab209c-efd4-44c2-af30-61abab0ae2fc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7fcd7a3aa1a6c034985099c24071429384563700
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59129389"
---
# <a name="iclrappdomainresourcemonitorgetcurrentallocated-method"></a>Metodo ICLRAppDomainResourceMonitor::GetCurrentAllocated
Ottiene la dimensione totale, espressa in byte, di tutte le allocazioni di memoria che sono state apportate dal dominio dell'applicazione perché è stato creato, senza sottrarre la memoria che è stato sottoposto a garbage collection.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetCurrentAllocated([in]  DWORD dwAppDomainId,  
                            [out] ULONGLONG* pBytesAllocated);  
```  
  
## <a name="parameters"></a>Parametri  
 `dwAppDomainId`  
 [in] L'ID del dominio dell'applicazione richiesta.  
  
 `pBytesAllocated`  
 [out] Puntatore alla dimensione totale di tutte le allocazioni di memoria.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|Metodo completato correttamente.|  
|COR_E_APPDOMAINUNLOADED|Il dominio dell'applicazione è stato scaricato o non esiste.|  
  
## <a name="remarks"></a>Note  
 Questo metodo è l'equivalente gestito di gestita <xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=nameWithType> proprietà.  
  
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
