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
ms.openlocfilehash: 3736627e7f42ad9db6699c31a0a618e993eef770
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2020
ms.locfileid: "82893475"
---
# <a name="icordebugcode-interface"></a>Interfaccia ICorDebugCode

Rappresenta un segmento di codice MSIL (Microsoft Intermediate Language) o di codice nativo.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo CreateBreakpoint](icordebugcode-createbreakpoint-method.md)|Crea un punto di interruzione in corrispondenza dell'offset specificato.|  
|[Metodo GetAddress](icordebugcode-getaddress-method.md)|Ottiene l'indirizzo RVA (relativo Virtual Address) del segmento di codice `ICorDebugCode` rappresentato dall'oggetto.|  
|[Metodo GetCode](icordebugcode-getcode-method.md)|Ottiene tutto il codice per la funzione specificata, formattato per il disassembly. Questo metodo è stato deprecato. usare invece [ICorDebugCode2:: GetCodeChunks](icordebugcode2-getcodechunks-method.md) .|  
|[Metodo GetEnCRemapSequencePoints](icordebugcode-getencremapsequencepoints-method.md)|Non implementato.|  
|[Metodo GetFunction](icordebugcode-getfunction-method.md)|Ottiene l'oggetto "ICorDebugFunction" associato all' `ICorDebugCode`oggetto.|  
|[Metodo GetILToNativeMapping](icordebugcode-getiltonativemapping-method.md)|Ottiene una matrice di istanze "COR_DEBUG_IL_TO_NATIVE_MAP" che rappresentano i mapping da offset MSIL a offset nativi.|  
|[Metodo GetSize](icordebugcode-getsize-method.md)|Ottiene la dimensione, in byte, del codice binario rappresentato dall'oggetto `ICorDebugCode`.|  
|[Metodo GetVersionNumber](icordebugcode-getversionnumber-method.md)|Ottiene il numero in base 1 che identifica la versione del codice `ICorDebugCode` rappresentato dall'oggetto.|  
|[Metodo IsIL](icordebugcode-isil-method.md)|Ottiene un valore che indica se l' `ICorDebugCode` oggetto viene compilato in MSIL.|  
  
## <a name="remarks"></a>Osservazioni  
 `ICorDebugCode`può rappresentare codice MSIL o nativo. A un oggetto "ICorDebugFunction" che rappresenta il codice MSIL può essere associato uno `ICorDebugCode` o più oggetti. A un oggetto "ICorDebugFunction" che rappresenta il codice nativo può essere associato `ICorDebugCode` un numero qualsiasi di oggetti.  
  
> [!NOTE]
> Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugCode3](icordebugcode3-interface.md)
- [Interfacce di debug](debugging-interfaces.md)
