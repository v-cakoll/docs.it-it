---
title: Metodo ICLRAssemblyIdentityManager::GetReferencedAssembliesFromStream
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager.GetReferencedAssembliesFromStream
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager::GetReferencedAssembliesFromStream
helpviewer_keywords:
- ICLRAssemblyIdentityManager::GetReferencedAssembliesFromStream method [.NET Framework hosting]
- GetReferencedAssembliesFromStream method [.NET Framework hosting]
ms.assetid: fe9849c1-c3fc-477b-a31f-e8619f5516f5
topic_type:
- apiref
ms.openlocfilehash: 4f06dd7b85446eec986055418d2cf558b9b5bd7a
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615930"
---
# <a name="iclrassemblyidentitymanagergetreferencedassembliesfromstream-method"></a>Metodo ICLRAssemblyIdentityManager::GetReferencedAssembliesFromStream
Ottiene un puntatore a un oggetto [ICLRReferenceAssemblyEnum](iclrreferenceassemblyenum-interface.md) che contiene i dati di identità dell'assembly per gli assembly a cui fa riferimento l'assembly nel flusso specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetReferencedAssembliesFromStream (  
    [in]  IStream *pStream,  
    [in]  DWORD    dwFlags,  
    [in]  ICLRAssemblyReferenceList  *pExcludeAssembliesList,  
    [out] ICLRReferenceAssemblyEnum **ppReferenceEnum  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pStream`  
 in Puntatore a un'interfaccia `IStream` contenente l'assembly da valutare.  
  
 `dwFlags`  
 in Fornito per l'estendibilità futura. CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT è l'unico valore supportato dalla versione corrente di Common Language Runtime (CLR).  
  
 `pExcludeAssembliesList`  
 in Puntatore a un oggetto [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) che contiene i dati di identità dell'assembly per gli assembly da escludere `ppReferenceEnum` .  
  
 `ppReferenceEnum`  
 out Puntatore all'indirizzo di un `ICLRReferenceAssemblyEnum` oggetto che contiene i dati di identità dell'assembly per gli assembly a cui fa riferimento l'assembly in `pStream` , esclusi gli assembly in `pExcludeAssembliesList` .  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Description|  
|-------------|-----------------|  
|S_OK|Il metodo è stato restituito correttamente.|  
|HOST_E_CLRNOTAVAILABLE|CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non è il proprietario del blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Se un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Osservazioni  
 Il chiamante può scegliere di escludere un set di riferimenti ad assembly noti dall'elenco restituito. Questo set è definito da `pExcludeAssembliesList` .  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRAssemblyIdentityManager](iclrassemblyidentitymanager-interface.md)
- [Interfaccia ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md)
- [Interfaccia ICLRReferenceAssemblyEnum](iclrreferenceassemblyenum-interface.md)
