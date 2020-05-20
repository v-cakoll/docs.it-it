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
ms.openlocfilehash: ea66c142afc097d1003df4e7f5f5b960a91e2ab0
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703393"
---
# <a name="iclrprobingassemblyenumget-method"></a>Metodo ICLRProbingAssemblyEnum::Get
Ottiene l'identità dell'assembly in corrispondenza dell'indice specificato.  
  
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
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Se un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo. Le chiamate successive a tutti i metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Osservazioni  
 L'identità in corrispondenza dell'indice 0 è l'identità specifica dell'architettura del processore. L'identità in corrispondenza dell'indice 1 è l'assembly indipendente dall'architettura per Microsoft Intermediate Language (MSIL). L'identità in corrispondenza dell'indice 2 non contiene informazioni sull'architettura.  
  
 `Get`viene in genere chiamato due volte. La prima chiamata fornisce un valore null per `pwzBuffer` e imposta `pcchBufferSize` sulle dimensioni appropriate per `pwzBuffer` . La seconda chiamata fornisce un oggetto di dimensioni appropriate `pwzBuffer` e contiene i dati di identità dell'assembly canonico al termine del completamento.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRProbingAssemblyEnum](iclrprobingassemblyenum-interface.md)
- [Interfaccia ICLRAssemblyIdentityManager](iclrassemblyidentitymanager-interface.md)
