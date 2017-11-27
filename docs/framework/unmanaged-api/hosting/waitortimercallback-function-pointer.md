---
title: Puntatore alla funzione WAITORTIMERCALLBACK
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: WAITORTIMERCALLBACK
api_location: mscoree.dll
api_type: COM
f1_keywords: WAITORTIMERCALLBACK
helpviewer_keywords: WAITORTIMERCALLBACK function pointer [.NET Framework hosting]
ms.assetid: 1fec4aef-0a06-4df0-bae7-d31a9ef9603d
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 873d2ff489085ec2a0c37be2feeb3e15f61c9227
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="waitortimercallback-function-pointer"></a>Puntatore alla funzione WAITORTIMERCALLBACK
Punta a una funzione che notifica all'host che un handle di attesa (<xref:System.Threading.WaitHandle>) è stato segnalato o timeout.  
  
 Questo puntatore a funzione è stato deprecato nel [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].  
  
## <a name="syntax"></a>Sintassi  
  
```  
typedef VOID (__stdcall *WAITORTIMERCALLBACK) (  
    [in] PVOID lpParameter,  
    [in] BOOL  TimerOrWaitFired  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `lpParameter`  
 [in] Puntatore a un oggetto che contiene le informazioni definite dall'host.  
  
 `TimerOrWaitFired`  
 [in] `true` se l'handle di attesa si è verificato un timeout, o `false` se è stato segnalato.  
  
## <a name="remarks"></a>Note  
 La funzione a cui `WAITORTIMERCALLBACK` punti è una funzione di callback e deve essere implementato dal writer dell'applicazione host.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Mscoree. H  
  
 **Libreria:** MSCorWks.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Funzioni di Hosting CLR deprecate](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
