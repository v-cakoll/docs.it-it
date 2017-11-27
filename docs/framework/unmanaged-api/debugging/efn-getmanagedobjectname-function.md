---
title: Funzione _EFN_GetManagedObjectName
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: _EFN_GetManagedObjectName
api_location: mscordbi.dll
api_type: COM
f1_keywords: _EFN_GetManagedObjectName
helpviewer_keywords: _EFN_GetManagedObjectName function [.NET Framework debugging]
ms.assetid: 6e7c6bee-7ced-495f-bf6c-2a5f0c716f7e
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 80e36f6c60c4c305cad9176cd7f185d8b6d2fdf2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="efngetmanagedobjectname-function"></a>Funzione _EFN_GetManagedObjectName
Ottiene il nome di un tipo utilizzando il puntatore all'oggetto gestito fornito.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT _EFN_GetManagedObjectName(  
    [in]  PDEBUG_CLIENT  Client,  
    [in]  ULONG64        objAddr,  
    [out] __out_ecount(cbName) PSTR szName,  
    [out] ULONG          cbName  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `Client`  
 [in] Puntatore al client di debug.  
  
 `objAddr`  
 [in] Puntatore a un oggetto gestito.  
  
 szName  
 [out] Il nome del tipo.  
  
 `cbName`  
 [out] Il numero di caratteri disponibili nel buffer di stringa.  
  
## <a name="remarks"></a>Note  
 Se non è presente nessun codice gestito sul thread attualmente in contesto, la funzione restituisce HRESULT SOS_E_NOMANAGEDCODE con un valore funzionalità 0xa0 e un codice di errore di 0x1000.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** SOS_Stacktrace. h  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Funzioni statiche globali di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
