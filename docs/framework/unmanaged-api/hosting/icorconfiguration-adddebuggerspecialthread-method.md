---
title: Metodo ICorConfiguration::AddDebuggerSpecialThread
ms.date: 03/30/2017
api_name:
- ICorConfiguration.AddDebuggerSpecialThread
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- AddDebuggerSpecialThread
helpviewer_keywords:
- AddDebuggerSpecialThread method [.NET Framework hosting]
- ICorConfiguration::AddDebuggerSpecialThread method [.NET Framework hosting]
ms.assetid: 1f1e3239-438e-4be9-a3bb-7d0722d3a76d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a73232fb9327880f0038097d71698ddf8bf005e3
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779896"
---
# <a name="icorconfigurationadddebuggerspecialthread-method"></a>Metodo ICorConfiguration::AddDebuggerSpecialThread
Indica che un thread specifico deve essere consentito di continuare l'esecuzione mentre il debugger ha un'applicazione arrestata durante gli scenari di debug gestiti o per i servizi di debug.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT AddDebuggerSpecialThread (  
    [in] DWORD dwSpecialThreadId  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `dwSpecialThreadId`  
 [in] L'ID del thread che devono essere autorizzate di continuare l'esecuzione.  
  
## <a name="remarks"></a>Note  
 Il thread specificato non potrà essere eseguito il codice gestito o accedere al runtime in alcun modo. Un esempio di un thread di questo tipo sarebbe un thread in-process per supportare i debugger di script precedente.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE.h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorConfiguration](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)
