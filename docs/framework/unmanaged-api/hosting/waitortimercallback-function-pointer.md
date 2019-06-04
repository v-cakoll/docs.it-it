---
title: Puntatore alla funzione WAITORTIMERCALLBACK
ms.date: 03/30/2017
api_name:
- WAITORTIMERCALLBACK
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- WAITORTIMERCALLBACK
helpviewer_keywords:
- WAITORTIMERCALLBACK function pointer [.NET Framework hosting]
ms.assetid: 1fec4aef-0a06-4df0-bae7-d31a9ef9603d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f938c7dcf08654eef1e2403426eb5c54d6d2a6b3
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490116"
---
# <a name="waitortimercallback-function-pointer"></a>Puntatore alla funzione WAITORTIMERCALLBACK
Punta a una funzione che notifica all'host che un handle di attesa (<xref:System.Threading.WaitHandle>) è stato segnalato o timeout.  
  
 Questo puntatore a funzione è stato deprecato in .NET Framework 4.  
  
## <a name="syntax"></a>Sintassi  
  
```  
typedef VOID (__stdcall *WAITORTIMERCALLBACK) (  
    [in] PVOID lpParameter,  
    [in] BOOL  TimerOrWaitFired  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `lpParameter`  
 [in] Un puntatore a un oggetto che contiene le informazioni definite dall'host.  
  
 `TimerOrWaitFired`  
 [in] `true` se l'handle di attesa si è verificato un timeout, o `false` se è stato segnalato.  
  
## <a name="remarks"></a>Note  
 La funzione a cui `WAITORTIMERCALLBACK` punti è una funzione di callback e devono essere implementati dal writer dell'applicazione host.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE.h  
  
 **Libreria:** MSCorWks.dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Funzioni di hosting CLR deprecate](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
