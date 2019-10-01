---
title: Metodo ICorDebugCode::CreateBreakpoint
ms.date: 03/30/2017
api_name:
- ICorDebugCode.CreateBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::CreateBreakpoint
helpviewer_keywords:
- ICorDebugCode::CreateBreakpoint method [.NET Framework debugging]
- CreateBreakpoint method, ICorDebugCode interface [.NET Framework debugging]
ms.assetid: 46842618-0fe4-480b-871c-82fba82d23d9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1ec7d615b99ac301948d7ea25318115713ce06ea
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71700847"
---
# <a name="icordebugcodecreatebreakpoint-method"></a>Metodo ICorDebugCode::CreateBreakpoint
Crea un punto di interruzione in questo segmento di codice in corrispondenza dell'offset specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT CreateBreakpoint (  
    [in] ULONG32     offset,  
    [out] ICorDebugFunctionBreakpoint **ppBreakpoint  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `offset`  
 in Offset in corrispondenza del quale creare il punto di interruzione.  
  
 `ppBreakpoint`  
 out Puntatore all'indirizzo di un oggetto "ICorDebugFunctionBreakpoint" che rappresenta il punto di interruzione.  
  
## <a name="remarks"></a>Note  
 Prima che il punto di interruzione sia attivo, è necessario aggiungerlo all'oggetto processo.  
  
 Se questo codice è codice MSIL (Microsoft Intermediate Language) ed è presente una versione nativa del codice compilata JIT (just-in-Time), il punto di interruzione verrà applicato anche nel codice compilato tramite JIT. (Lo stesso vale se il codice viene compilato in modalità JIT in un secondo momento).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug. idl, CorDebug. h  
  
 **Libreria** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
