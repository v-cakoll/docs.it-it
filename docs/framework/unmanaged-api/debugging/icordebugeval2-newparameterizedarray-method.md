---
title: Metodo ICorDebugEval2::NewParameterizedArray
ms.date: 03/30/2017
api_name:
- ICorDebugEval2.NewParameterizedArray
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::NewParameterizedArray
helpviewer_keywords:
- ICorDebugEval2::NewParameterizedArray method [.NET Framework debugging]
- NewParameterizedArray method [.NET Framework debugging]
ms.assetid: 45efb8ba-c4de-4109-945f-e734d376b43c
topic_type:
- apiref
ms.openlocfilehash: 9476bcc9706e89fd3d7e0abc14031f70a0aa0ad0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73084828"
---
# <a name="icordebugeval2newparameterizedarray-method"></a>Metodo ICorDebugEval2::NewParameterizedArray
Alloca una nuova matrice del tipo e delle dimensioni dell'elemento specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT NewParameterizedArray(  
    [in] ICorDebugType          *pElementType,  
    [in] ULONG32                rank,  
    [in, size_is(rank)] ULONG32 dims[],  
    [in, size_is(rank)] ULONG32 lowBounds[]  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pElementType`  
 in Puntatore a un oggetto ICorDebugType che rappresenta il tipo di elemento archiviato nella matrice.  
  
 `rank`  
 in Numero di dimensioni della matrice. Nel .NET Framework versione 2,0, questo valore deve essere 1.  
  
 `dims`  
 in Dimensione, in byte, di ogni dimensione della matrice.  
  
 `lowBounds`  
 [in] Facoltativo. Limite inferiore di ogni dimensione della matrice. Se questo valore viene omesso, per ogni dimensione viene utilizzato un limite inferiore pari a zero.  
  
## <a name="remarks"></a>Note  
 Gli elementi della matrice possono essere istanze di un tipo generico. La matrice viene sempre creata nel dominio applicazione in cui è attualmente in esecuzione il thread. Nel .NET Framework 2,0, il valore di `rank` deve essere 1.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
