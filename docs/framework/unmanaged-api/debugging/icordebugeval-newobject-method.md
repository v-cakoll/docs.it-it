---
title: Metodo ICorDebugEval::NewObject
ms.date: 03/30/2017
api_name:
- ICorDebugEval.NewObject
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::NewObject
helpviewer_keywords:
- NewObject method [.NET Framework debugging]
- ICorDebugEval::NewObject method [.NET Framework debugging]
ms.assetid: ce3025e8-defa-4c5e-8298-f49d71fa5736
topic_type:
- apiref
ms.openlocfilehash: 68a7e911c2bd1798ea8f34f6a6e24299fe68775d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137614"
---
# <a name="icordebugevalnewobject-method"></a>Metodo ICorDebugEval::NewObject
Alloca una nuova istanza dell'oggetto e chiama il metodo del costruttore specificato.  
  
 Questo metodo è obsoleto nella versione .NET Framework 2,0. Usare invece [ICorDebugEval2:: NewParameterizedObject](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobject-method.md) .  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT NewObject (  
    [in] ICorDebugFunction  *pConstructor,  
    [in] ULONG32            nArgs,  
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pConstructor`  
 in Costruttore da chiamare.  
  
 `nArgs`  
 [in] Dimensione della matrice `ppArgs`.  
  
 `ppArgs`  
 in Matrice di oggetti ICorDebugValue, ognuno dei quali rappresenta un argomento da passare al costruttore.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** 1,1, 1,0  
  
## <a name="see-also"></a>Vedere anche

- [Metodo NewParameterizedObject](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobject-method.md)
