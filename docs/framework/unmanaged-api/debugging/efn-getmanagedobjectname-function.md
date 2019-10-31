---
title: Funzione _EFN_GetManagedObjectName
ms.date: 03/30/2017
api_name:
- _EFN_GetManagedObjectName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- _EFN_GetManagedObjectName
helpviewer_keywords:
- _EFN_GetManagedObjectName function [.NET Framework debugging]
ms.assetid: 6e7c6bee-7ced-495f-bf6c-2a5f0c716f7e
topic_type:
- apiref
ms.openlocfilehash: c7333f8f7b95655ac821e9a2977d5db3794486a2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122998"
---
# <a name="_efn_getmanagedobjectname-function"></a>\_AAPN\_funzione GetManagedObjectName
Ottiene il nome di un tipo utilizzando il puntatore all'oggetto gestito fornito.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT _EFN_GetManagedObjectName(  
    [in]  PDEBUG_CLIENT  Client,  
    [in]  ULONG64        objAddr,  
    [out] __out_ecount(cbName) PSTR szName,  
    [out] ULONG          cbName  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `Client`  
 in Puntatore al client di debug.  
  
 `objAddr`  
 in Puntatore A un oggetto gestito.  
  
 szName  
 out Nome del tipo.  
  
 `cbName`  
 out Numero di caratteri disponibili nel buffer di stringa.  
  
## <a name="remarks"></a>Note  
 Se nel thread non è attualmente presente codice gestito nel contesto, la funzione restituisce HRESULT SOS_E_NOMANAGEDCODE con il valore della funzione messaggi 0XA0 e un codice di errore 0x1000.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** SOS_Stacktrace. h  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Funzioni statiche globali di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
