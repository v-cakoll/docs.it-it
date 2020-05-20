---
title: Metodo ICLRReferenceAssemblyEnum::Get
ms.date: 03/30/2017
api_name:
- ICLRReferenceAssemblyEnum.Get
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRReferenceAssemblyEnum::Get
helpviewer_keywords:
- ICLRReferenceAssemblyEnum::Get method [.NET Framework hosting]
- Get method, ICLRReferenceAssemblyEnum interface [.NET Framework hosting]
ms.assetid: f21c1612-9c5d-4abc-a337-577086d29c17
topic_type:
- apiref
ms.openlocfilehash: 5afa7b37b804b6a11a894e0e6c7708c7787a20ae
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703359"
---
# <a name="iclrreferenceassemblyenumget-method"></a>Metodo ICLRReferenceAssemblyEnum::Get
Ottiene l'identità dell'assembly in corrispondenza dell'indice fornito.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT Get (  
    [in] DWORD dwIndex,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `dwIndex`  
 in Indice in base zero dell'identità dell'assembly da restituire.  
  
 `pwzBuffer`  
 out Buffer contenente i dati di identità dell'assembly.  
  
 `pcchBufferSize`  
 [in, out] Dimensioni del `pwzBuffer` buffer.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Description|  
|-------------|-----------------|  
|S_OK|`Get`la restituzione è riuscita.|  
|ERROR_INSUFFICIENT_BUFFER|Il valore di `pwzBuffer` è troppo piccolo.|  
|ERROR_NO_MORE_ITEMS|L'enumerazione non contiene altri elementi.|  
|HOST_E_CLRNOTAVAILABLE|Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non è il proprietario del blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Se un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Osservazioni  
 `Get`viene in genere chiamato due volte. La prima chiamata fornisce un valore null per `pwzBuffer` e imposta `pcchBufferSize` sulle dimensioni appropriate per `pwzBuffer` . La seconda chiamata fornisce un oggetto di dimensioni appropriate `pwzBuffer` e contiene i dati di identità dell'assembly canonico al termine del completamento.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md)
- [Interfaccia ICLRReferenceAssemblyEnum](iclrreferenceassemblyenum-interface.md)
