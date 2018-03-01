---
title: Metodo ICorDebugEval::NewArray
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f9116c2ee7edbc39d203728909ce37e963c896fc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugevalnewarray-method"></a>Metodo ICorDebugEval::NewArray
Alloca una nuova matrice del tipo di elemento specificato e le dimensioni.  
  
 Questo metodo è obsoleto in .NET Framework versione 2.0. Utilizzare [ICorDebugEval2::](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedarray-method.md) invece.  
  
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
  
#### <a name="parameters"></a>Parametri  
 `elementType`  
 [in] Valore dell'enumerazione CorElementType che specifica il tipo di elemento della matrice.  
  
 `pElementClass`  
 [in] Un puntatore a un oggetto ICorDebugClass che specifica la classe dell'elemento. Questo valore può essere null se il tipo di elemento è un tipo primitivo.  
  
 `rank`  
 [in] Il numero di dimensioni della matrice. In .NET Framework 2.0, questo valore deve essere 1.  
  
 `dims`  
 [in] Le dimensioni in byte, di ciascuna dimensione della matrice.  
  
 `lowBounds`  
 [in] Facoltativo. Il limite inferiore di ogni dimensione della matrice. Se questo valore viene omesso, per ogni dimensione viene utilizzato un limite inferiore pari a zero.  
  
## <a name="remarks"></a>Note  
 La matrice viene sempre creata nel dominio dell'applicazione in cui il thread è in esecuzione.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:** 1.1, 1.0
