---
title: Metodo ICorDebugEval2::NewParameterizedArray
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugEval2.NewParameterizedArray
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugEval2::NewParameterizedArray
helpviewer_keywords:
- ICorDebugEval2::NewParameterizedArray method [.NET Framework debugging]
- NewParameterizedArray method [.NET Framework debugging]
ms.assetid: 45efb8ba-c4de-4109-945f-e734d376b43c
topic_type: apiref
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: cf7f8fb0d3418f863f2cd1531dc32b7e64c2b8a5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugeval2newparameterizedarray-method"></a>Metodo ICorDebugEval2::NewParameterizedArray
Alloca una nuova matrice del tipo di elemento specificato e le dimensioni.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT NewParameterizedArray(  
    [in] ICorDebugType          *pElementType,  
    [in] ULONG32                rank,  
    [in, size_is(rank)] ULONG32 dims[],  
    [in, size_is(rank)] ULONG32 lowBounds[]  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `pElementType`  
 [in] Un puntatore a un oggetto ICorDebugType che rappresenta il tipo di elemento memorizzato nella matrice.  
  
 `rank`  
 [in] Il numero di dimensioni della matrice. In .NET Framework versione 2.0, questo valore deve essere 1.  
  
 `dims`  
 [in] Le dimensioni in byte, di ciascuna dimensione della matrice.  
  
 `lowBounds`  
 [in] Facoltativo. Il limite inferiore di ogni dimensione della matrice. Se questo valore viene omesso, per ogni dimensione viene utilizzato un limite inferiore pari a zero.  
  
## <a name="remarks"></a>Note  
 Gli elementi della matrice possono essere istanze di un tipo generico. La matrice viene sempre creata nel dominio dell'applicazione in cui il thread attualmente in esecuzione. In .NET Framework 2.0, il valore di `rank` deve essere 1.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
