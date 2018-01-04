---
title: Metodo ICLRProbingAssemblyEnum::Get
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRProbingAssemblyEnum.Get
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRProbingAssemblyEnum::Get
helpviewer_keywords:
- Get method, ICLRProbingAssemblyEnum interface [.NET Framework hosting]
- ICLRProbingAssemblyEnum::Get method [.NET Framework hosting]
ms.assetid: fdb67a77-782f-44cf-a8a1-b75999b0f3c8
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: dd54558eeb49ebf7a2a2e9304830b09a08d1038e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="iclrprobingassemblyenumget-method"></a>Metodo ICLRProbingAssemblyEnum::Get
Ottiene l'identità dell'assembly in corrispondenza dell'indice specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT Get (  
    [in] DWORD dwIndex,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `dwIndex`  
 [in] Indice in base zero dell'identità dell'assembly da restituire.  
  
 `pwzBuffer`  
 [out] Un buffer contenente i dati di identità di assembly.  
  
 `pcchBufferSize`  
 [in, out] Le dimensioni del `pwzBuffer` buffer.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|`Get`stato restituito correttamente.|  
|ERROR_INSUFFICIENT_BUFFER|`pwzBuffer`è troppo piccolo.|  
|ERROR_NO_MORE_ITEMS|L'enumerazione non contiene più elementi.|  
|HOST_E_CLRNOTAVAILABLE|Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non dispone del blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Se un metodo restituisce E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Note  
 L'identità in corrispondenza dell'indice 0 è l'identità specifica per l'architettura del processore. L'identità in corrispondenza dell'indice 1 è l'assembly di architettura neutra per Microsoft intermediate language (MSIL). L'identità in corrispondenza dell'indice 2 non contiene alcuna informazione di architettura.  
  
 `Get`viene in genere chiamato due volte. La prima chiamata fornisce un valore null per `pwzBuffer`e imposta `pcchBufferSize` per le dimensioni appropriate per `pwzBuffer`. La seconda chiamata viene fornito un dimensionati `pwzBuffer`e contiene i dati di identità assembly canonica dopo il completamento.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Mscoree. H  
  
 **Libreria:** inclusa come risorsa in MSCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICLRProbingAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md)  
 [Interfaccia ICLRAssemblyIdentityManager](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
