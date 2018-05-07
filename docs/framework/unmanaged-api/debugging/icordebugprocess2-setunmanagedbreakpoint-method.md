---
title: Metodo ICorDebugProcess2::SetUnmanagedBreakpoint
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.SetUnmanagedBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::SetUnmanagedBreakpoint
helpviewer_keywords:
- ICorDebugProcess2::SetUnmanagedBreakpoint method [.NET Framework debugging]
- SetUnmanagedBreakpoint method [.NET Framework debugging]
ms.assetid: 93829d15-d942-4e2d-b7a4-dfc9d7fb96be
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d4326c6d8a3ee780cf63652badc8c527f55a075c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugprocess2setunmanagedbreakpoint-method"></a>Metodo ICorDebugProcess2::SetUnmanagedBreakpoint
Imposta un punto di interruzione non gestita in corrispondenza dell'offset specificato immagini native.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT SetUnmanagedBreakpoint (  
    [in]  CORDB_ADDRESS    address,  
    [in]  ULONG32          bufsize,  
    [out, size_is(bufsize), length_is(*bufLen)]   
        BYTE               buffer[],  
    [out] ULONG32          *bufLen  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `address`  
 [in] Oggetto `CORDB_ADDRESS` oggetto che specifica l'offset di immagini native.  
  
 `bufsize`  
 [in] Le dimensioni, in byte, del `buffer` matrice.  
  
 `buffer`  
 [out] Matrice che contiene il codice operativo che viene sostituito dal punto di interruzione.  
  
 `bufLen`  
 [out] Un puntatore al numero di byte restituiti nella `buffer` matrice.  
  
## <a name="remarks"></a>Note  
 Se l'offset di immagini native è all'interno di common language runtime (CLR), il punto di interruzione verrà ignorato. In questo modo la CLR evitare l'invio di un punto di interruzione fuori banda, quando è impostato il punto di interruzione dal debugger.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cordebug. idl, Cordebug. H  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
