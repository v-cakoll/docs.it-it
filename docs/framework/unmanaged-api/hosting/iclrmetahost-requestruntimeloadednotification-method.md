---
title: Metodo ICLRMetaHost::RequestRuntimeLoadedNotification
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.RequestRuntimeLoadedNotification
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::RequestRuntimeLoadedNotification
helpviewer_keywords:
- RequestRuntimeLoadedNotification method [.NET Framework hosting]
- ICLRMetaHost::RequestRuntimeLoadedNotification method [.NET Framework hosting]
ms.assetid: 0d5ccc4d-0193-41f5-af54-45d7b70d5321
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 539f69c33b67ad1a8a514062c5d777deaced1599
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964998"
---
# <a name="iclrmetahostrequestruntimeloadednotification-method"></a>Metodo ICLRMetaHost::RequestRuntimeLoadedNotification
Fornisce una funzione di callback che è garantita per essere chiamata quando una versione di Common Language Runtime (CLR) viene caricata per la prima volta, ma non ancora avviata. Questo metodo sostituisce la funzione [LockClrVersion](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md) .  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT RequestRuntimeLoadedNotification (  
    [in] RuntimeLoadedCallbackFnPtr pCallbackFunction);  
```  
  
## <a name="parameters"></a>Parametri  
 `pCallbackFunction`  
 in Funzione di callback richiamata quando un nuovo runtime è stato caricato.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|Metodo completato correttamente.|  
|E_POINTER|`pCallbackFunction` è null.|  
  
## <a name="remarks"></a>Note  
 Il callback funziona nel modo seguente:  
  
- Il callback viene richiamato solo quando un runtime viene caricato per la prima volta.  
  
- Il callback non viene richiamato per i caricamenti rientranti dello stesso runtime.  
  
- Per i caricamenti del runtime non rientranti, le chiamate alla funzione di callback vengono serializzate.  
  
 La funzione di callback presenta il seguente prototipo:  
  
```cpp  
typedef void (__stdcall *RuntimeLoadedCallbackFnPtr)(  
                     ICLRRuntimeInfo *pRuntimeInfo,  
                     CallbackThreadSetFnPtr pfnCallbackThreadSet,  
                     CallbackThreadUnsetFnPtr pfnCallbackThreadUnset);  
```  
  
 I prototipi di funzione di callback sono i seguenti:  
  
- `pfnCallbackThreadSet`:  
  
    ```cpp  
    typedef HRESULT (__stdcall *CallbackThreadSetFnPtr)();  
    ```  
  
- `pfnCallbackThreadUnset`:  
  
    ```cpp  
    typedef HRESULT (__stdcall *CallbackThreadUnsetFnPtr)();  
    ```  
  
 Se l'host intende caricare o causare il caricamento di un altro runtime in modo rientrante, è necessario utilizzare `pfnCallbackThreadSet` i `pfnCallbackThreadUnset` parametri e forniti nella funzione di callback nel modo seguente:  
  
- `pfnCallbackThreadSet`deve essere chiamato dal thread che potrebbe causare un caricamento in fase di esecuzione prima che venga eseguito un tentativo di caricamento.  
  
- `pfnCallbackThreadUnset`deve essere chiamato quando il thread non provocherà più un carico di runtime di questo tipo (e prima della restituzione dal callback iniziale).  
  
- `pfnCallbackThreadSet`e `pfnCallbackThreadUnset` sono entrambi non rientranti.  
  
> [!NOTE]
> Le applicazioni host non devono `pfnCallbackThreadSet` chiamare `pfnCallbackThreadUnset` né al di `pCallbackFunction` fuori dell'ambito del parametro.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Metahost. h  
  
 **Libreria** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)
- [Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md)
