---
title: Metodo ICorRuntimeHost::GetDefaultDomain
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.GetDefaultDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::GetDefaultDomain
helpviewer_keywords:
- ICorRuntimeHost::GetDefaultDomain method [.NET Framework hosting]
- GetDefaultDomain method [.NET Framework hosting]
ms.assetid: 5e17a6fc-f335-4aae-9bb0-c3e1271a9426
topic_type:
- apiref
ms.openlocfilehash: a23083777d0cd5965511f3689578a60220008420
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762230"
---
# <a name="icorruntimehostgetdefaultdomain-method"></a>Metodo ICorRuntimeHost::GetDefaultDomain
Ottiene un puntatore a interfaccia di tipo <xref:System._AppDomain?displayProperty=nameWithType> che rappresenta il dominio predefinito per il processo corrente.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetDefaultDomain (  
    [out] IUnknown** pAppDomain  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pAppDomain`  
 out Puntatore di interfaccia di tipo <xref:System._AppDomain?displayProperty=nameWithType> all' <xref:System.AppDomain> istanza di che rappresenta il dominio applicazione predefinito per il processo.  
  
 Questo puntatore è tipizzato `IUnknown` , quindi i chiamanti devono in genere chiamare `QueryInterface` per ottenere un puntatore a interfaccia di tipo <xref:System._AppDomain?displayProperty=nameWithType> .  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|L'operazione è stata completata.|  
|S_FALSE|Non è stato possibile completare l'operazione.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Se un metodo restituisce E_FAIL, il Common Language Runtime (CLR) non è più utilizzabile nel processo. Le chiamate successive a qualsiasi API di hosting restituiscono HOST_E_CLRNOTAVAILABLE.|  
|HOST_E_CLRNOTAVAILABLE|CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:** 1,0, 1,1  
  
## <a name="see-also"></a>Vedere anche

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [Interfaccia ICorRuntimeHost](icorruntimehost-interface.md)
