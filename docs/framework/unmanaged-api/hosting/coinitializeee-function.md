---
title: Funzione CoInitializeEE
ms.date: 03/30/2017
api_name:
- CoInitializeEE
api_location:
- mscoree.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- CoInitializeEE
helpviewer_keywords:
- CoInitializeEE function [.NET Framework hosting]
ms.assetid: 7e42a928-5068-4ba6-b8c3-806551a01fa8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 18f1a4ede1a362860df1271835600e7b867eac00
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61696925"
---
# <a name="coinitializeee-function"></a>Funzione CoInitializeEE
Garantisce che il motore di esecuzione di common language runtime è caricato in un processo. Questa funzione è deprecata nel [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]. Usare la [ICLRRuntimeHost:: Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) metodo invece.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT CoInitializeEE (  
   [in] DWORD fFlags  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `fFlags`  
 [in] Uno dei [COINITIEE](../../../../docs/framework/unmanaged-api/metadata/coinitiee-enumeration.md) costanti di enumerazione.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce i codici di errore COM standard, come definito nel file Winerror. h e i valori nella tabella seguente.  
  
|Codice restituito|Descrizione|  
|-----------------|-----------------|  
|S_OK|Il motore di esecuzione è stato caricato correttamente.|  
|S_FALSE|Il motore di esecuzione è già caricato.|  
|E_FAIL|Non è stato possibile caricare il motore di esecuzione.|  
  
## <a name="remarks"></a>Note  
 Questo metodo carica il motore di esecuzione se non è stato caricato in precedenza.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Funzioni statiche globali dei metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
