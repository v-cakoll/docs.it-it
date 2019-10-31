---
title: Metodo ICorDebugNativeFrame::GetLocalMemoryRegisterValue
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetLocalMemoryRegisterValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetLocalMemoryRegisterValue
helpviewer_keywords:
- ICorDebugNativeFrame::GetLocalMemoryRegisterValue method [.NET Framework debugging]
- GetLocalMemoryRegisterValue method
ms.assetid: 33a19f6e-1029-4d53-af64-19591c6e58ee
topic_type:
- apiref
ms.openlocfilehash: 788ce2d47769caa72518e0357a0affdff5862699
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137277"
---
# <a name="icordebugnativeframegetlocalmemoryregistervalue-method"></a>Metodo ICorDebugNativeFrame::GetLocalMemoryRegisterValue
Ottiene il valore di un argomento o di una variabile locale, di cui la parola bassa e la parola alta vengono archiviate rispettivamente nel registro e nella posizione di memoria specificati per il frame nativo.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetLocalMemoryRegisterValue (  
    [in] CORDB_ADDRESS      highWordAddress,  
    [in] CorDebugRegister   lowWordRegister,  
    [in] ULONG              cbSigBlob,  
    [in] PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `highWordAddress`  
 in Valore `CORDB_ADDRESS` che specifica la posizione di memoria contenente la parola alta del valore.  
  
 `lowWordRegister`  
 in Valore dell'enumerazione "CorDebugRegister" che specifica il registro contenente la parola bassa del valore.  
  
 `cbSigBlob`  
 in Integer che specifica la dimensione della firma dei metadati binari a cui fa riferimento il parametro `pvSigBlob`.  
  
 `pvSigBlob`  
 in Valore `PCCOR_SIGNATURE` che punta alla firma dei metadati binaria del tipo del valore.  
  
 `ppValue`  
 out Puntatore all'indirizzo di un oggetto "ICorDebugValue" che rappresenta il valore recuperato archiviato nel registro e nella posizione di memoria specificati.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
