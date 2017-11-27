---
title: Puntatore alla funzione LPOVERLAPPED_COMPLETION_ROUTINE
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: LPOVERLAPPED_COMPLETION_ROUTINE
api_location: mscoree.dll
api_type: COM
f1_keywords: LPOVERLAPPED_COMPLETION_ROUTINE
helpviewer_keywords: LPOVERLAPPED_COMPLETION_ROUTINE function pointer [.NET Framework hosting]
ms.assetid: 5fb645d9-b818-401c-8c2c-c30d86de58ba
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4d50f2058796d4c5c900474cdcbe71d8a5a911ca
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="lpoverlappedcompletionroutine-function-pointer"></a>Puntatore alla funzione LPOVERLAPPED_COMPLETION_ROUTINE
Punta a una funzione che notifica all'host quando un sovrapposte (vale a dire asincrona) i/o in un dispositivo è stata completata.  
  
 Questo puntatore a funzione è stato deprecato nel [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].  
  
## <a name="syntax"></a>Sintassi  
  
```  
typedef VOID (*LPOVERLAPPED_COMPLETION_ROUTINE) (  
    [in] DWORD  dwErrorCode,  
    [in] DWORD  dwNumberOfBytesTransfered,  
    [in] LPVOID lpOverlapped  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `dwErrorCode`  
 [in] Un valore che è un codice di errore se il dispositivo è stata chiusa; in caso contrario, questo valore è zero.  
  
 La chiusura di un dispositivo causa tutte in sospeso i/o al dispositivo per essere completate immediatamente.  
  
 `dwNumberOfBytesTransfered`  
 [in] Il numero di byte trasferiti dall'operazione dei / o.  
  
 `lpOverlapped`  
 [in] Un puntatore a una struttura che contiene le informazioni da utilizzare per completare la richiesta dei / o.  
  
## <a name="remarks"></a>Note  
 La funzione a cui `LPOVERLAPPED_COMPLETION_ROUTINE` punti è una funzione di callback e deve essere implementato dal writer dell'applicazione host. La funzione di callback consente all'host di elaborare la richiesta dei / o completata.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Mscoree. H  
  
 **Libreria:** MSCorWks.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Funzioni di Hosting CLR deprecate](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
