---
title: Funzione _EFN_GetManagedObjectFieldInfo
ms.date: 03/30/2017
api_name:
- _EFN_GetManagedObjectFieldInfo
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- _EFN_GetManagedObjectFieldInfo
helpviewer_keywords:
- _EFN_GetManagedObjectFieldInfo function [.NET Framework debugging]
ms.assetid: 3b93bcff-62a4-47b2-babc-6bcf4216119a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c6195d9666afa8fba3f77322366e4709634e53bb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33405246"
---
# <a name="efngetmanagedobjectfieldinfo-function"></a>Funzione _EFN_GetManagedObjectFieldInfo
Ottiene l'offset per un campo dall'inizio di un oggetto e il valore del campo, usando il puntatore all'oggetto e il nome di campo forniti.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT _EFN_GetManagedObjectFieldInfo(  
    [in]  PDEBUG_CLIENT Client,  
    [in]  ULONG64       objAddr,  
    [in]  __out_ecount (mdNameLen) PSTR szFieldName,  
    [out] PULONG64      pValue,  
    [out] PULONG        pOffset  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `Client`  
 [in] Puntatore al client di debug.  
  
 `objAddr`  
 [in] Puntatore a un oggetto gestito.  
  
 szFieldName  
 [in] Un puntatore all'oggetto gestito per il nome del campo.  
  
 `pValue`  
 [out] Il valore del campo. Questo parametro può essere null.  
  
 `pOffset`  
 [out] L'offset dal `objAddr` al campo. Questo parametro può essere null.  
  
## <a name="remarks"></a>Note  
 Se l'offset è 0, viene scritto alcun offset.  
  
 Se non è presente nessun codice gestito sul thread attualmente in contesto, la funzione restituisce HRESULT SOS_E_NOMANAGEDCODE con un valore funzionalità 0xa0 e un codice di errore di 0x1000.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** SOS_Stacktrace. h  
  
 **Versione di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Funzioni statiche globali di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
