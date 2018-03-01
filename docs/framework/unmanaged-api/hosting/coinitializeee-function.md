---
title: Funzione CoInitializeEE
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- CoInitializeEE
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- CoInitializeEE
helpviewer_keywords:
- CoInitializeEE function [.NET Framework hosting]
ms.assetid: 7e42a928-5068-4ba6-b8c3-806551a01fa8
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0ca564830411a9df0d47cc9765958286bbd40f96
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="coinitializeee-function"></a>Funzione CoInitializeEE
Assicura che il motore di esecuzione di common language runtime viene caricato in un processo. Questa funzione è deprecata nel [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]. Utilizzare il [ICLRRuntimeHost:: Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) metodo invece.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT CoInitializeEE (  
   [in] DWORD fFlags  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `fFlags`  
 [in] Uno del [COINITIEE](../../../../docs/framework/unmanaged-api/metadata/coinitiee-enumeration.md) costanti di enumerazione.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce codici di errore COM standard, come definito nel file Winerror. h e i valori nella tabella seguente.  
  
|Codice restituito|Descrizione|  
|-----------------|-----------------|  
|S_OK|Il motore di esecuzione è stato caricato correttamente.|  
|S_FALSE|Il motore di esecuzione è già caricato.|  
|E_FAIL|Impossibile caricare il motore di esecuzione.|  
  
## <a name="remarks"></a>Note  
 Se non è stato caricato in precedenza, questo metodo carica il motore di esecuzione.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** inclusa come risorsa in MsCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Funzioni statiche globali dei metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
