---
title: Puntatore alla funzione LPOVERLAPPED_COMPLETION_ROUTINE
ms.date: 03/30/2017
api_name:
- LPOVERLAPPED_COMPLETION_ROUTINE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- LPOVERLAPPED_COMPLETION_ROUTINE
helpviewer_keywords:
- LPOVERLAPPED_COMPLETION_ROUTINE function pointer [.NET Framework hosting]
ms.assetid: 5fb645d9-b818-401c-8c2c-c30d86de58ba
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dcf63000de549b42d92ba157a7e550ac605bbfcd
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67768387"
---
# <a name="lpoverlappedcompletionroutine-function-pointer"></a>Puntatore alla funzione LPOVERLAPPED_COMPLETION_ROUTINE
Punta a una funzione che notifica all'host quando un sovrapposta (vale a dire, asincrona) i/o a un dispositivo è stata completata.  
  
 Questo puntatore a funzione è stato deprecato in .NET Framework 4.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef VOID (*LPOVERLAPPED_COMPLETION_ROUTINE) (  
    [in] DWORD  dwErrorCode,  
    [in] DWORD  dwNumberOfBytesTransfered,  
    [in] LPVOID lpOverlapped  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `dwErrorCode`  
 [in] Un valore che corrisponde a un codice di errore se il dispositivo è stato chiuso; in caso contrario, questo valore è zero.  
  
 Chiusura di un dispositivo fa sì che tutte in sospeso i/o al dispositivo per essere completata immediatamente.  
  
 `dwNumberOfBytesTransfered`  
 [in] Il numero di byte trasferiti dall'operazione dei / o.  
  
 `lpOverlapped`  
 [in] Un puntatore a una struttura che contiene le informazioni da utilizzare per completare la richiesta dei / o.  
  
## <a name="remarks"></a>Note  
 La funzione a cui `LPOVERLAPPED_COMPLETION_ROUTINE` punti è una funzione di callback e devono essere implementati dal writer dell'applicazione host. La funzione di richiamata consente all'host elaborare la richiesta dei / o completata.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE.h  
  
 **Libreria:** MSCorWks.dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Funzioni di hosting CLR deprecate](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
