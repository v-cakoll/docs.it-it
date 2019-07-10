---
title: Metodo ICorPublish::GetProcess
ms.date: 03/30/2017
api_name:
- ICorPublish.GetProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublish::GetProcess
helpviewer_keywords:
- ICorPublish::GetProcess method [.NET Framework debugging]
- GetProcess method, ICorPublish interface [.NET Framework debugging]
ms.assetid: c5143805-2eb7-45b8-85ed-c8fb34df1084
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2b2dcdaed34044122dd2a61c9e0b5bb02f8cc0d9
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67774268"
---
# <a name="icorpublishgetprocess-method"></a>Metodo ICorPublish::GetProcess
Ottiene un' [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) istanza che rappresenta il processo con l'identificatore specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetProcess(  
    [in] unsigned              pid,   
    [out] ICorPublishProcess   **ppProcess  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pid`  
 [in] L'identificatore del processo.  
  
 `ppProcess`  
 [out] Un puntatore all'indirizzo di un `ICorPublishProcess` istanza che rappresenta il processo.  
  
## <a name="remarks"></a>Note  
 `GetProcess` non riesce se il processo non esiste o non è un processo gestito che è possibile eseguire il debug dell'utente corrente.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorPub.idl, CorPub.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorPublish](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md)
