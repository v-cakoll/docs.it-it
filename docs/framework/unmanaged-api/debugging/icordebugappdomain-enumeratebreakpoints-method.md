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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b00afc900a27aea94389ee81065ea22ae359440d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61996268"
---
# <a name="icordebugappdomainenumeratebreakpoints-method"></a>Metodo ICorDebugAppDomain::EnumerateBreakpoints
Ottiene un enumeratore per tutti i punti di interruzione attivi nel dominio dell'applicazione.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT EnumerateBreakpoints (  
    [out] ICorDebugBreakpointEnum   **ppBreakpoints  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `ppBreakpoints`  
 [out] Un puntatore all'indirizzo di un oggetto ICorDebugBreakpointEnum che è l'enumeratore per tutti i punti di interruzione attivi nel dominio dell'applicazione.  
  
## <a name="remarks"></a>Note  
 L'enumeratore include tutti i tipi di punti di interruzione, tra cui i punti di interruzione di funzione e i punti di interruzione dei dati.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
