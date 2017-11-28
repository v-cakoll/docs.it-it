---
title: Metodo ICorRuntimeHost::GetDefaultDomain
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorRuntimeHost.GetDefaultDomain
api_location: mscoree.dll
api_type: COM
f1_keywords: ICorRuntimeHost::GetDefaultDomain
helpviewer_keywords:
- ICorRuntimeHost::GetDefaultDomain method [.NET Framework hosting]
- GetDefaultDomain method [.NET Framework hosting]
ms.assetid: 5e17a6fc-f335-4aae-9bb0-c3e1271a9426
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4c482247a0a227c202bb81db09d13ad9af71e60f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icorruntimehostgetdefaultdomain-method"></a>Metodo ICorRuntimeHost::GetDefaultDomain
Ottiene un puntatore a interfaccia di tipo <xref:System._AppDomain?displayProperty=nameWithType> che rappresenta il dominio predefinito per il processo corrente.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetDefaultDomain (  
    [out] IUnknown** pAppDomain  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `pAppDomain`  
 [out] Un puntatore a interfaccia di tipo <xref:System._AppDomain?displayProperty=nameWithType> per il <xref:System.AppDomain> istanza che rappresenta il dominio applicazione predefinito per il processo.  
  
 Il puntatore è tipizzato `IUnknown`, i chiamanti devono in genere utilizzare `QueryInterface` per ottenere un puntatore a interfaccia di tipo <xref:System._AppDomain?displayProperty=nameWithType>.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|L'operazione è riuscita.|  
|S_FALSE|Impossibile completare l'operazione.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Se un metodo restituisce E_FAIL, common language runtime (CLR) non è più utilizzabile nel processo. Le chiamate successive a qualsiasi API di hosting restituiranno HOST_E_CLRNOTAVAILABLE.|  
|HOST_E_CLRNOTAVAILABLE|CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Mscoree. H  
  
 **Libreria:** inclusa come risorsa in MSCorEE.dll  
  
 **Versioni di .NET framework:** 1.0, 1.1  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System._AppDomain>  
 <xref:System.AppDomain>  
 [ICorRuntimeHost (interfaccia)](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
