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
ms.openlocfilehash: 103ac75e7c3eaf9739c3a448ff1c052c158621db
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73090898"
---
# <a name="lpoverlapped_completion_routine-function-pointer"></a>Puntatore alla funzione LPOVERLAPPED_COMPLETION_ROUTINE
Punta a una funzione che notifica all'host quando è stata completata un'operazione di I/O sovrapposta (ovvero asincrona) a un dispositivo.  
  
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
 in Valore che rappresenta un codice di errore se il dispositivo è stato chiuso; in caso contrario, questo valore è zero.  
  
 La chiusura di un dispositivo comporta immediatamente il completamento di tutte le operazioni di I/O in sospeso nel dispositivo.  
  
 `dwNumberOfBytesTransfered`  
 in Numero di byte trasferiti dall'operazione di I/O.  
  
 `lpOverlapped`  
 in Puntatore a una struttura che contiene le informazioni da utilizzare per completare la richiesta di I/O.  
  
## <a name="remarks"></a>Note  
 Funzione a cui `LPOVERLAPPED_COMPLETION_ROUTINE` punti è una funzione di callback e deve essere implementata dal writer dell'applicazione host. La funzione di callback consente all'host di elaborare la richiesta di I/O completata.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** MSCorWks. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Funzioni di hosting CLR deprecate](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
