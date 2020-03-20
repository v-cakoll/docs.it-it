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
ms.openlocfilehash: fb8b8f3e29c141e91587a4d0cdc81cdabccdbc9e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178641"
---
# <a name="icordebugprocess2setunmanagedbreakpoint-method"></a>Metodo ICorDebugProcess2::SetUnmanagedBreakpoint
Imposta un punto di interruzione non gestito in corrispondenza dell'offset dell'immagine nativa specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT SetUnmanagedBreakpoint (  
    [in]  CORDB_ADDRESS    address,  
    [in]  ULONG32          bufsize,  
    [out, size_is(bufsize), length_is(*bufLen)]
        BYTE               buffer[],  
    [out] ULONG32          *bufLen  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `address`  
 [in] Oggetto `CORDB_ADDRESS` che specifica l'offset dell'immagine nativa.  
  
 `bufsize`  
 [in] Dimensione, in byte, `buffer` della matrice.  
  
 `buffer`  
 [fuori] Matrice che contiene il codice operativo sostituito dal punto di interruzione.  
  
 `bufLen`  
 [fuori] Puntatore al numero di byte `buffer` restituiti nella matrice.  
  
## <a name="remarks"></a>Osservazioni  
 Se l'offset dell'immagine nativa si trova all'interno di Common Language Runtime (CLR), il punto di interruzione verrà ignorato. Ciò consente a CLR di evitare di inviare un punto di interruzione fuori banda, quando il punto di interruzione viene impostato dal debugger.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
