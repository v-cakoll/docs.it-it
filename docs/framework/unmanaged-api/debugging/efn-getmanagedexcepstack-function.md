---
title: Funzione _EFN_GetManagedExcepStack
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: _EFN_GetManagedExcepStack
api_location: mscordbi.dll
api_type: COM
f1_keywords: _EFN_GetManagedExcepStack
helpviewer_keywords: _EFN_GetManagedExcepStack function [.NET Framework debugging]
ms.assetid: 21ceed9e-62b2-4024-b027-6d095109955a
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: edcd93bec29c6f0fef3b0bed4b8293efead3932d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="efngetmanagedexcepstack-function"></a>Funzione _EFN_GetManagedExcepStack
Restituisce una versione stringa della traccia dello stack contenuta internamente, dato l'indirizzo di un oggetto eccezione gestita.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT _EFN_GetManagedExcepStack(  
    [in]  PDEBUG_CLIENT Client,  
    [in]  ULONG64       StackObjAddr,  
    [out] __out_ecount(cbString) PSTR szStackString,  
    [out] ULONG         cbString  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `Client`  
 [in] Il client è in corso il debug.  
  
 `StackObjAddr`  
 [in] Puntatore a un oggetto gestito, derivato da <xref:System.Exception>.  
  
 szStackString  
 [out] La stringa restituita.  
  
 `cbString`  
 [out] Il numero di caratteri disponibili nel buffer di stringa.  
  
## <a name="remarks"></a>Note  
 Se non è presente nessun codice gestito sul thread attualmente in contesto, la funzione restituisce HRESULT SOS_E_NOMANAGEDCODE con un valore funzionalità 0xa0 e un codice di errore di 0x1000.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** SOS_Stacktrace. h  
  
 **Versione di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Funzioni statiche globali di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
