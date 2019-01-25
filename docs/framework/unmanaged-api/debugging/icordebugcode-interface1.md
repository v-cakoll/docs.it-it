---
title: Interfaccia1 ICorDebugCode
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
ms.openlocfilehash: db2fe1e854069d9b5d566fc00420615e0c06b3d8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54575947"
---
# <a name="icordebugcode-interface1"></a>Interfaccia1 ICorDebugCode
Rappresenta un segmento di codice MSIL (Microsoft Intermediate Language) o di codice nativo.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo CreateBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-createbreakpoint-method.md)|Crea un punto di interruzione in corrispondenza dell'offset specificato.|  
|[Metodo GetAddress](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getaddress-method.md)|Ottiene l'indirizzo virtuale relativo (RVA) del segmento di codice che questo `ICorDebugCode` rappresenta.|  
|[Metodo GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getcode-method.md)|Ottiene tutto il codice per la funzione specificata, formattata per il disassembly. Questo metodo è deprecato. usare [ICorDebugCode2::GetCodeChunks](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md) invece.|  
|[Metodo GetEnCRemapSequencePoints](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getencremapsequencepoints-method.md)|Non implementato.|  
|[Metodo GetFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getfunction-method.md)|Ottiene il "ICorDebugFunction" associato a questo `ICorDebugCode`.|  
|[Metodo GetILToNativeMapping](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getiltonativemapping-method.md)|Ottiene una matrice di istanze di "COR_DEBUG_IL_TO_NATIVE_MAP" che rappresentano i mapping dagli offset MSIL agli offset nativi.|  
|[Metodo GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getsize-method.md)|Ottiene la dimensione, espressa in byte, del codice binario rappresentato da questo `ICorDebugCode`.|  
|[Metodo GetVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getversionnumber-method.md)|Ottiene il numero in base 1 che identifica la versione del codice che questo `ICorDebugCode` rappresenta.|  
|[Metodo IsIL](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-isil-method.md)|Ottiene un valore che indica se questo `ICorDebugCode` viene compilata in MSIL.|  
  
## <a name="remarks"></a>Note  
 `ICorDebugCode` può rappresentare MSIL o codice nativo. Un oggetto "ICorDebugFunction" che rappresenta il codice MSIL può avere zero o uno `ICorDebugCode` associati oggetti. Un oggetto "ICorDebugFunction" che rappresenta il codice nativo può avere un numero qualsiasi di `ICorDebugCode` associati oggetti.  
  
> [!NOTE]
>  Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugCode3](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)
- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
