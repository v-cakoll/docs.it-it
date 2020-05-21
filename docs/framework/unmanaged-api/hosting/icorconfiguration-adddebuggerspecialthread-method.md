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
ms.openlocfilehash: 8b6593ad995872f0e0014b1e8bcd8a4b576bbeaf
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762428"
---
# <a name="icorconfigurationadddebuggerspecialthread-method"></a>Metodo ICorConfiguration::AddDebuggerSpecialThread
Indica ai servizi di debug che un determinato thread deve essere in grado di continuare l'esecuzione mentre nel debugger è stata arrestata un'applicazione durante gli scenari di debug gestiti o non gestiti.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT AddDebuggerSpecialThread (  
    [in] DWORD dwSpecialThreadId  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `dwSpecialThreadId`  
 in ID del thread a cui deve essere consentita l'esecuzione continua.  
  
## <a name="remarks"></a>Osservazioni  
 Al thread specificato non sarà consentito eseguire codice gestito o accedere in alcun modo al runtime. Un esempio di tale thread è costituito da un thread in-process per supportare i debugger di script legacy.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorConfiguration](icorconfiguration-interface.md)
