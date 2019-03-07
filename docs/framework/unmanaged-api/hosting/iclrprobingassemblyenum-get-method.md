---
title: Metodo ICLRProbingAssemblyEnum::Get
ms.date: 03/30/2017
api_name:
- ICLRProbingAssemblyEnum.Get
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRProbingAssemblyEnum::Get
helpviewer_keywords:
- Get method, ICLRProbingAssemblyEnum interface [.NET Framework hosting]
- ICLRProbingAssemblyEnum::Get method [.NET Framework hosting]
ms.assetid: fdb67a77-782f-44cf-a8a1-b75999b0f3c8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 909e18fe9086fa954ffc389ffe1c6fe49217d2f5
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57492452"
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
  
## <a name="parameters"></a>Parametri  
 `dwIndex`  
 [in] Indice a base zero dell'identità dell'assembly da restituire.  
  
 `pwzBuffer`  
 [out] Un buffer contenente i dati di identità di assembly.  
  
 `pcchBufferSize`  
 [in, out] Le dimensioni del `pwzBuffer` buffer.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|`Get` stato restituito correttamente.|  
|ERROR_INSUFFICIENT_BUFFER|`pwzBuffer` è troppo piccolo.|  
|ERROR_NO_MORE_ITEMS|L'enumerazione non contiene più elementi.|  
|HOST_E_CLRNOTAVAILABLE|Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non possiede il blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Se un metodo viene restituito E_FAIL, CLR non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Note  
 L'identità in corrispondenza dell'indice 0 è l'identità specifica per l'architettura del processore. L'identità in corrispondenza dell'indice 1 è l'assembly indipendenti dalla architettura per Microsoft intermediate language (MSIL). L'identità in corrispondenza dell'indice 2 non contiene alcuna informazione di architettura.  
  
 `Get` viene in genere chiamato due volte. La prima chiamata fornisce un valore null per `pwzBuffer`e imposta `pcchBufferSize` alle dimensioni appropriate per `pwzBuffer`. La seconda chiamata fornisce dimensioni appropriate `pwzBuffer`e contiene i dati di identità di assembly canonico dopo il completamento.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE.h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia ICLRProbingAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md)
- [Interfaccia ICLRAssemblyIdentityManager](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
