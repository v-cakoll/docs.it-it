---
title: Metodo ICorDebugAppDomain::EnumerateBreakpoints
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.EnumerateBreakpoints
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::EnumerateBreakpoints
helpviewer_keywords:
- ICorDebugAppDomain::EnumerateBreakpoints method [.NET Framework debugging]
- EnumerateBreakpoints method [.NET Framework debugging]
ms.assetid: 206069c5-25cb-4794-9d69-67c5aa7ed0af
topic_type:
- apiref
ms.openlocfilehash: bb994ae32c9e0e61c06c60521361a5c6c78d12fa
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895283"
---
# <a name="icordebugappdomainenumeratebreakpoints-method"></a>Metodo ICorDebugAppDomain::EnumerateBreakpoints
Ottiene un enumeratore per tutti i punti di interruzione attivi nel dominio applicazione.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT EnumerateBreakpoints (  
    [out] ICorDebugBreakpointEnum   **ppBreakpoints  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `ppBreakpoints`  
 out Puntatore all'indirizzo di un oggetto ICorDebugBreakpointEnum che rappresenta l'enumeratore per tutti i punti di interruzione attivi nel dominio applicazione.  
  
## <a name="remarks"></a>Osservazioni  
 L'enumeratore include tutti i tipi di punti di interruzione, inclusi i punti di interruzione delle funzioni e i punti di interruzione dei dati.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
