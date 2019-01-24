---
title: Metodo ICorDebugEval::CallFunction
ms.date: 03/30/2017
api_name:
- ICorDebugEval.CallFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::CallFunction
helpviewer_keywords:
- ICorDebugEval::CallFunction method [.NET Framework debugging]
- CallFunction method [.NET Framework debugging]
ms.assetid: 7f470c5c-e1c0-4d8d-aad8-830f113ae751
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 493b4850436b3724287210878992d1d8ce8fe168
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54589399"
---
# <a name="icordebugevalcallfunction-method"></a>Metodo ICorDebugEval::CallFunction
Imposta una chiamata alla funzione specificata.  
  
 Questo metodo è obsoleto in .NET Framework versione 2.0. Uso [ICorDebugEval2::CallParameterizedFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-callparameterizedfunction-method.md) invece.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT CallFunction (  
    [in] ICorDebugFunction  *pFunction,  
    [in] ULONG32            nArgs,  
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `pFunction`  
 [in] Puntatore a un oggetto ICorDebugFunction che specifica la funzione da chiamare.  
  
 `nArgs`  
 [in] Il numero di argomenti per la funzione.  
  
 `ppArgs`  
 [in] Una matrice di puntatori, ognuno dei quali punta a un oggetto ICorDebugValue che specifica un argomento deve essere passato alla funzione.  
  
## <a name="remarks"></a>Note  
 Se la funzione è virtuale, `CallFunction` eseguirà chiamate virtuali. Se la funzione è in un altro dominio applicazione, si verificherà una transizione, purché tutti gli argomenti sono presenti anche in tale dominio dell'applicazione.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:** 1.1, 1.0  
  
## <a name="see-also"></a>Vedere anche
- [Metodo CallParameterizedFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-callparameterizedfunction-method.md)
