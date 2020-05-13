---
title: Metodo ICorDebugNativeFrame::GetLocalRegisterMemoryValue
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetLocalRegisterMemoryValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetLocalRegisterMemoryValue
helpviewer_keywords:
- ICorDebugNativeFrame::GetLocalRegisterMemoryValue method [.NET Framework debugging]
- GetLocalRegisterMemoryValue method [.NET Framework debugging]
ms.assetid: d350f69d-9aff-4f5a-8301-daea22dee2da
topic_type:
- apiref
ms.openlocfilehash: f16150ad7d9ecec4b4aceee5c9266e9a7859f1cb
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213296"
---
# <a name="icordebugnativeframegetlocalregistermemoryvalue-method"></a>Metodo ICorDebugNativeFrame::GetLocalRegisterMemoryValue
Ottiene il valore di un argomento o di una variabile locale, di cui la parola bassa e la parola alta vengono archiviati nella posizione di memoria e nel registro specificato rispettivamente per il frame nativo.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetLocalRegisterMemoryValue (  
    [in] CorDebugRegister   highWordReg,  
    [in] CORDB_ADDRESS      lowWordAddress,  
    [in] ULONG              cbSigBlob,  
    [in] PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `highWordReg`  
 in Valore dell'enumerazione "CorDebugRegister" che specifica il registro contenente la parola alta del valore.  
  
 `lowWordAddress`  
 in `CORDB_ADDRESS`Valore che specifica la posizione di memoria contenente la parola bassa del valore.  
  
 `cbSigBlob`  
 in Integer che specifica la dimensione della firma dei metadati binari a cui fa riferimento il `pvSigBlob` parametro.  
  
 `pvSigBlob`  
 in `PCCOR_SIGNATURE`Valore che punta alla firma dei metadati binaria del tipo del valore.  
  
 `ppValue`  
 out Puntatore all'indirizzo di un oggetto "ICorDebugValue" che rappresenta il valore recuperato archiviato nel registro e nella posizione di memoria specificati.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
