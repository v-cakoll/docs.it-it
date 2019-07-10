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
ms.openlocfilehash: 7e7c1de620979b387e969f4b8c9f17f493e7bcb8
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776554"
---
# <a name="iclrmetahostrequestruntimeloadednotification-method"></a>Metodo ICLRMetaHost::RequestRuntimeLoadedNotification
Fornisce una funzione di callback che viene garantita da chiamare quando viene caricata inizialmente una versione di common language runtime (CLR), ma non ancora iniziata. Questo metodo sostituisce le [LockClrVersion](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md) (funzione).  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT RequestRuntimeLoadedNotification (  
    [in] RuntimeLoadedCallbackFnPtr pCallbackFunction);  
```  
  
## <a name="parameters"></a>Parametri  
 `pCallbackFunction`  
 [in] La funzione di callback che viene richiamata quando è stato caricato un nuovo runtime.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|Metodo completato correttamente.|  
|E_POINTER|`pCallbackFunction` è null.|  
  
## <a name="remarks"></a>Note  
 La richiamata funziona nel modo seguente:  
  
- Il callback viene richiamato solo quando viene caricato un runtime per la prima volta.  
  
- Non viene richiamato il callback per i caricamenti rientranti dello stesso runtime.  
  
- Per i carichi di runtime non rientrante, le chiamate alla funzione di callback vengono serializzate.  
  
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
  
 Se l'host si intende caricare o provocare un altro runtime da caricare in modo rientrante, la `pfnCallbackThreadSet` e `pfnCallbackThreadUnset` parametri che vengono messe a disposizione nel callback di funzione deve essere utilizzata nel modo seguente:  
  
- `pfnCallbackThreadSet` deve essere chiamato dal thread che potrebbe causare un carico di runtime prima del tentativo di un carico di questo tipo.  
  
- `pfnCallbackThreadUnset` deve essere chiamato quando il thread non è più comporterà un caricamento di runtime (e prima della restituzione dal callback iniziale).  
  
- `pfnCallbackThreadSet` e `pfnCallbackThreadUnset` sono entrambi non rientrante.  
  
> [!NOTE]
>  Hosting di applicazioni non devono chiamare `pfnCallbackThreadSet` e `pfnCallbackThreadUnset` rientrano nell'ambito del `pCallbackFunction` parametro.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MetaHost.h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)
- [Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md)
