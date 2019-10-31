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
ms.openlocfilehash: 9e90772ae8c3e6be5744fcccc9901123df871831
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131936"
---
# <a name="coinitializeee-function"></a>Funzione CoInitializeEE
Garantisce che il motore di esecuzione Common Language Runtime venga caricato in un processo. Questa funzione è deprecata nel .NET Framework 4. Usare invece il metodo [ICLRRuntimeHost:: Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) .  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT CoInitializeEE (  
   [in] DWORD fFlags  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `fFlags`  
 in Una delle costanti di enumerazione [COINITIEE](../../../../docs/framework/unmanaged-api/metadata/coinitiee-enumeration.md) .  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce i codici di errore COM standard come definito in Winerror. h e i valori nella tabella seguente.  
  
|Codice restituito|Descrizione|  
|-----------------|-----------------|  
|S_OK|Il motore di esecuzione è stato caricato correttamente.|  
|S_FALSE|Il motore di esecuzione è già caricato.|  
|E_FAIL|Non è stato possibile caricare il motore di esecuzione.|  
  
## <a name="remarks"></a>Note  
 Questo metodo carica il motore di esecuzione se non è stato caricato in precedenza.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Incluso come risorsa in MsCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Funzioni statiche globali dei metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
