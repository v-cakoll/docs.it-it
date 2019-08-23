---
title: Interfaccia ICorDebugCode
ms.date: 03/30/2017
api_name:
- ICorDebugCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode
helpviewer_keywords:
- ICorDebugCode interface [.NET Framework debugging]
ms.assetid: 7bd14fb6-8b54-4484-a891-e3c21859c019
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 75cc8ea9d88dda42362f50b519864b1a78e1a64b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69960798"
---
# <a name="icordebugcode-interface"></a>Interfaccia ICorDebugCode

Rappresenta un segmento di codice MSIL (Microsoft Intermediate Language) o di codice nativo.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|DESCRIZIONE|  
|------------|-----------------|  
|[Metodo CreateBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-createbreakpoint-method.md)|Crea un punto di interruzione in corrispondenza dell'offset specificato.|  
|[Metodo GetAddress](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getaddress-method.md)|Ottiene l'indirizzo RVA (relativo Virtual Address) del segmento `ICorDebugCode` di codice rappresentato dall'oggetto.|  
|[Metodo GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getcode-method.md)|Ottiene tutto il codice per la funzione specificata, formattato per il disassembly. Questo metodo è stato deprecato. usare invece [ICorDebugCode2:: GetCodeChunks](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md) .|  
|[Metodo GetEnCRemapSequencePoints](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getencremapsequencepoints-method.md)|Non implementato.|  
|[Metodo GetFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getfunction-method.md)|Ottiene l'oggetto "ICorDebugFunction" associato all' `ICorDebugCode`oggetto.|  
|[Metodo GetILToNativeMapping](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getiltonativemapping-method.md)|Ottiene una matrice di istanze "COR_DEBUG_IL_TO_NATIVE_MAP" che rappresentano i mapping da offset MSIL a offset nativi.|  
|[Metodo GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getsize-method.md)|Ottiene la dimensione, in byte, del codice binario rappresentato dall' `ICorDebugCode`oggetto.|  
|[Metodo GetVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getversionnumber-method.md)|Ottiene il numero in base 1 che identifica la versione del codice `ICorDebugCode` rappresentato dall'oggetto.|  
|[Metodo IsIL](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-isil-method.md)|Ottiene un valore che indica se l' `ICorDebugCode` oggetto viene compilato in MSIL.|  
  
## <a name="remarks"></a>Note  
 `ICorDebugCode`può rappresentare codice MSIL o nativo. A un oggetto "ICorDebugFunction" che rappresenta il codice MSIL può essere associato uno `ICorDebugCode` o più oggetti. A un oggetto "ICorDebugFunction" che rappresenta il codice nativo può essere associato `ICorDebugCode` un numero qualsiasi di oggetti.  
  
> [!NOTE]
> Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug. idl, CorDebug. h  
  
 **Libreria** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugCode3](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)
- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
