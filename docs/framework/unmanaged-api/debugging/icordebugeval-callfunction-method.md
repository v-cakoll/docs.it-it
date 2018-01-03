---
title: Metodo ICorDebugEval::CallFunction
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugEval.CallFunction
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugEval::CallFunction
helpviewer_keywords:
- ICorDebugEval::CallFunction method [.NET Framework debugging]
- CallFunction method [.NET Framework debugging]
ms.assetid: 7f470c5c-e1c0-4d8d-aad8-830f113ae751
topic_type: apiref
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3c2d5582c9ac69692546e9a2310c4d0c9cdde83e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugevalcallfunction-method"></a>Metodo ICorDebugEval::CallFunction
Imposta una chiamata alla funzione specificata.  
  
 Questo metodo è obsoleto in .NET Framework versione 2.0. Utilizzare [ICorDebugEval2:: CallParameterizedFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-callparameterizedfunction-method.md) invece.  
  
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
 [in] Matrice di puntatori, ognuno dei quali punta a un oggetto ICorDebugValue che specifica un argomento deve essere passato alla funzione.  
  
## <a name="remarks"></a>Note  
 Se la funzione è virtuale, `CallFunction` eseguirà invio virtuale. Se la funzione è in un altro dominio applicazione, si verificherà una transizione, purché tutti gli argomenti sono anche nel dominio dell'applicazione.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:** 1.1, 1.0  
  
## <a name="see-also"></a>Vedere anche  
 [Metodo CallParameterizedFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-callparameterizedfunction-method.md)
