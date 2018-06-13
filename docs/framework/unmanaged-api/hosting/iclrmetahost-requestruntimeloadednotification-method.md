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
ms.openlocfilehash: 9ac041db64a874cc143657c601f30e4482dd2462
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33434435"
---
# <a name="iclrmetahostrequestruntimeloadednotification-method"></a>Metodo ICLRMetaHost::RequestRuntimeLoadedNotification
Fornisce una funzione di callback che viene chiamato quando è caricata una versione di common language runtime (CLR), ma non ancora avviata. Questo metodo sostituisce il [LockClrVersion](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md) (funzione).  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT RequestRuntimeLoadedNotification (  
    [in] RuntimeLoadedCallbackFnPtr pCallbackFunction);  
```  
  
#### <a name="parameters"></a>Parametri  
 `pCallbackFunction`  
 [in] La funzione di callback che viene richiamata quando un nuovo runtime è stato caricato.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|Metodo completato correttamente.|  
|E_POINTER|`pCallbackFunction` è null.|  
  
## <a name="remarks"></a>Note  
 Il callback funziona nel modo seguente:  
  
-   Il callback viene richiamato solo quando viene caricato un runtime per la prima volta.  
  
-   Per i caricamenti rientranti del runtime stesso non viene richiamato il callback.  
  
-   Per i caricamenti di runtime non rientrante, le chiamate alla funzione di callback vengono serializzate.  
  
 La funzione di callback è il seguente prototipo:  
  
```  
typedef void (__stdcall *RuntimeLoadedCallbackFnPtr)(  
                     ICLRRuntimeInfo *pRuntimeInfo,  
                     CallbackThreadSetFnPtr pfnCallbackThreadSet,  
                     CallbackThreadUnsetFnPtr pfnCallbackThreadUnset);  
```  
  
 I prototipi di funzione di callback sono i seguenti:  
  
-   `pfnCallbackThreadSet`:  
  
    ```  
    typedef HRESULT (__stdcall *CallbackThreadSetFnPtr)();  
    ```  
  
-   `pfnCallbackThreadUnset`:  
  
    ```  
    typedef HRESULT (__stdcall *CallbackThreadUnsetFnPtr)();  
    ```  
  
 Se l'host tenta di caricare o causare un altro runtime da caricare in modo rientrante, la `pfnCallbackThreadSet` e `pfnCallbackThreadUnset` parametri che vengono fornite nel callback di funzione deve essere utilizzata nel modo seguente:  
  
-   `pfnCallbackThreadSet` deve essere chiamato dal thread che potrebbero causare un carico di runtime prima di tenta un carico di questo tipo.  
  
-   `pfnCallbackThreadUnset` deve essere chiamato quando il thread non comporterà un carico di runtime (e prima di restituire il callback iniziale).  
  
-   `pfnCallbackThreadSet` e `pfnCallbackThreadUnset` sono entrambi non rientrante.  
  
> [!NOTE]
>  Hosting di applicazioni non devono chiamare `pfnCallbackThreadSet` e `pfnCallbackThreadUnset` all'esterno dell'ambito del `pCallbackFunction` parametro.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Metahost. H  
  
 **Libreria:** inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)  
 [Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md)
