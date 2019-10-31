---
title: Metodo ICorRuntimeHost::NextDomain
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.NextDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::NextDomain
helpviewer_keywords:
- ICorRuntimeHost::NextDomain method [.NET Framework hosting]
- NextDomain method [.NET Framework hosting]
ms.assetid: fe07a05b-f6d6-44b5-ab01-b9a6eb15c350
topic_type:
- apiref
ms.openlocfilehash: 36eacedfb83c1248fc252091872bcfeecdbcd874
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139506"
---
# <a name="icorruntimehostnextdomain-method"></a>Metodo ICorRuntimeHost::NextDomain
Ottiene un puntatore a interfaccia al dominio successivo nell'enumerazione.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT NextDomain (  
    [in] HCORENUM hEnum,  
    [out] void** pAppDomain  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `hEnum`  
 in Enumeratore ottenuto tramite una chiamata a [EnumDomains](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-enumdomains-method.md).  
  
 `pAppDomain`  
 out Puntatore di interfaccia al tipo di <xref:System._AppDomain?displayProperty=nameWithType> che rappresenta il dominio successivo nell'enumerazione, o null, se non esistono altri domini.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|Operazione completata.|  
|S_FALSE|Non è stato possibile completare l'operazione oppure non sono presenti altri domini nell'enumerazione.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Se un metodo restituisce E_FAIL, il Common Language Runtime (CLR) non è più utilizzabile nel processo. Le chiamate successive a qualsiasi API di hosting restituiscono HOST_E_CLRNOTAVAILABLE.|  
|HOST_E_CLRNOTAVAILABLE|CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:** 1,0, 1,1  
  
## <a name="see-also"></a>Vedere anche

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [Interfaccia ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
