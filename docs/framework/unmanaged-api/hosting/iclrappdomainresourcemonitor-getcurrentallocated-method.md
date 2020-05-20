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
ms.openlocfilehash: 685d303b31b8f8c20cbbdb8aec6fc127650aa32a
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616047"
---
# <a name="iclrappdomainresourcemonitorgetcurrentallocated-method"></a>Metodo ICLRAppDomainResourceMonitor::GetCurrentAllocated
Ottiene le dimensioni totali, in byte, di tutte le allocazioni di memoria effettuate dal dominio applicazione da quando è stato creato, senza sottrarre memoria che è stata sottoposta a Garbage Collection.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetCurrentAllocated([in]  DWORD dwAppDomainId,  
                            [out] ULONGLONG* pBytesAllocated);  
```  
  
## <a name="parameters"></a>Parametri  
 `dwAppDomainId`  
 in ID del dominio applicazione richiesto.  
  
 `pBytesAllocated`  
 out Un puntatore alla dimensione totale di tutte le allocazioni di memoria.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.  
  
|HRESULT|Description|  
|-------------|-----------------|  
|S_OK|Metodo completato correttamente.|  
|COR_E_APPDOMAINUNLOADED|Il dominio applicazione è stato scaricato o non esiste.|  
  
## <a name="remarks"></a>Osservazioni  
 Questo metodo è l'equivalente non gestito della <xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=nameWithType> proprietà gestita.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Metahost. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRAppDomainResourceMonitor](iclrappdomainresourcemonitor-interface.md)
- [Monitoraggio delle risorse del dominio applicazione](../../../standard/garbage-collection/app-domain-resource-monitoring.md)
- [Interfacce di hosting](hosting-interfaces.md)
- [Hosting](index.md)
