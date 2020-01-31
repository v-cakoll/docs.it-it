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
ms.openlocfilehash: 13ac5379992f4e768b09a03d31591143ba9bf627
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788716"
---
# <a name="icordebugevalnewarray-method"></a>Metodo ICorDebugEval::NewArray
Alloca una nuova matrice del tipo e delle dimensioni dell'elemento specificato.  
  
 Questo metodo è obsoleto nella versione .NET Framework 2,0. Usare invece [ICorDebugEval2:: NewParameterizedArray](icordebugeval2-newparameterizedarray-method.md) .  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
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
 in Valore dell'enumerazione CorElementType che specifica il tipo di elemento della matrice.  
  
 `pElementClass`  
 in Puntatore a un oggetto ICorDebugClass che specifica la classe dell'elemento. Questo valore può essere null se il tipo di elemento è un tipo primitivo.  
  
 `rank`  
 in Numero di dimensioni della matrice. Nel .NET Framework 2,0, questo valore deve essere 1.  
  
 `dims`  
 in Dimensione, in byte, di ogni dimensione della matrice.  
  
 `lowBounds`  
 [in] Facoltativo. Limite inferiore di ogni dimensione della matrice. Se questo valore viene omesso, per ogni dimensione viene utilizzato un limite inferiore pari a zero.  
  
## <a name="remarks"></a>Note  
 La matrice viene sempre creata nel dominio applicazione in cui è attualmente in esecuzione il thread.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** 1,1, 1,0
