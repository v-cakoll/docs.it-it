---
title: Funzione _EFN_GetManagedExcepStack
ms.date: 03/30/2017
api_name:
- _EFN_GetManagedExcepStack
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- _EFN_GetManagedExcepStack
helpviewer_keywords:
- _EFN_GetManagedExcepStack function [.NET Framework debugging]
ms.assetid: 21ceed9e-62b2-4024-b027-6d095109955a
topic_type:
- apiref
ms.openlocfilehash: 9bcc03cc97a62b4c1cadacd7c0b2bc46b9fec470
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134133"
---
# <a name="_efn_getmanagedexcepstack-function"></a>\_AAPN\_funzione GetManagedExcepStack
Restituisce una versione stringa della traccia dello stack contenuta internamente, dato l'indirizzo di un oggetto eccezione gestita.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT _EFN_GetManagedExcepStack(  
    [in]  PDEBUG_CLIENT Client,  
    [in]  ULONG64       StackObjAddr,  
    [out] __out_ecount(cbString) PSTR szStackString,  
    [out] ULONG         cbString  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `Client`  
 in Client di cui è in corso il debug.  
  
 `StackObjAddr`  
 in Puntatore a un oggetto gestito, derivato da <xref:System.Exception>.  
  
 szStackString  
 out Stringa restituita.  
  
 `cbString`  
 out Numero di caratteri disponibili nel buffer di stringa.  
  
## <a name="remarks"></a>Note  
 Se nel thread non è attualmente presente codice gestito nel contesto, la funzione restituisce HRESULT SOS_E_NOMANAGEDCODE con il valore della funzione messaggi 0XA0 e un codice di errore 0x1000.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** SOS_Stacktrace. h  
  
 **Versione .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Funzioni statiche globali di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
