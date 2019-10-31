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
ms.openlocfilehash: ffab2762fd86e95c3272ca456039028e0897bc41
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137176"
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
 in Oggetto `CORDB_ADDRESS` che specifica l'offset dell'immagine nativa.  
  
 `bufsize`  
 in Dimensione, in byte, della matrice `buffer`.  
  
 `buffer`  
 out Matrice che contiene il codice operativo che viene sostituito dal punto di interruzione.  
  
 `bufLen`  
 out Puntatore al numero di byte restituiti nella matrice `buffer`.  
  
## <a name="remarks"></a>Note  
 Se l'offset dell'immagine nativa si trova all'interno del Common Language Runtime (CLR), il punto di interruzione verrà ignorato. Questo consente a CLR di evitare l'invio di un punto di interruzione fuori banda, quando il punto di interruzione viene impostato dal debugger.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
