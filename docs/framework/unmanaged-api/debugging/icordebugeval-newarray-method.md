---
title: Metodo ICorDebugEval::NewArray
ms.date: 03/30/2017
api_name:
- ICorDebugEval.NewArray
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::NewArray
helpviewer_keywords:
- NewArray method [.NET Framework debugging]
- ICorDebugEval::NewArray method [.NET Framework debugging]
ms.assetid: cc79a67d-5368-434d-a943-209db90491b9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d1abe307e3b9fa607912f98e456a11176eb17c56
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61934758"
---
# <a name="icordebugevalnewarray-method"></a>Metodo ICorDebugEval::NewArray
Consente di allocare una nuova matrice del tipo di elemento specificato e le dimensioni.  
  
 Questo metodo è obsoleto in .NET Framework versione 2.0. Uso [ICorDebugEval2::NewParameterizedArray](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedarray-method.md) invece.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT NewArray (  
    [in] CorElementType     elementType,  
    [in] ICorDebugClass     *pElementClass,  
    [in] ULONG32            rank,  
    [in, size_is(rank)] ULONG32 dims[],  
    [in, size_is(rank)] ULONG32 lowBounds[]  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `elementType`  
 [in] Valore dell'enumerazione CorElementType che specifica il tipo di elemento della matrice.  
  
 `pElementClass`  
 [in] Un puntatore a un oggetto ICorDebugClass che specifica la classe dell'elemento. Questo valore può essere null se il tipo di elemento è un tipo primitivo.  
  
 `rank`  
 [in] Il numero di dimensioni della matrice. In .NET Framework 2.0, questo valore deve essere 1.  
  
 `dims`  
 [in] Le dimensioni, in byte, di ogni dimensione della matrice.  
  
 `lowBounds`  
 [in] Facoltativo. Il limite inferiore di ogni dimensione della matrice. Se questo valore viene omesso, per ogni dimensione viene utilizzato un limite inferiore pari a zero.  
  
## <a name="remarks"></a>Note  
 La matrice viene sempre creata nel dominio dell'applicazione in cui il thread è in esecuzione.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:** 1.1, 1.0
