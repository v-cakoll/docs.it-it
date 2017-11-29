---
title: ICorDebugCode Interface1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugCode
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugCode
helpviewer_keywords: ICorDebugCode interface [.NET Framework debugging]
ms.assetid: 7bd14fb6-8b54-4484-a891-e3c21859c019
topic_type: apiref
caps.latest.revision: "22"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7813381c345db3d14318dddd93df1b491b46549e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugcode-interface1"></a>ICorDebugCode Interface1
Rappresenta un segmento di codice MSIL (Microsoft Intermediate Language) o di codice nativo.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[CreateBreakpoint (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-createbreakpoint-method.md)|Crea un punto di interruzione in corrispondenza dell'offset specificato.|  
|[GetAddress (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getaddress-method.md)|Ottiene l'indirizzo virtuale relativo (RVA) del segmento di codice che questo `ICorDebugCode` rappresenta.|  
|[GetCode (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getcode-method.md)|Ottiene il codice per la funzione specificata, formattata per il disassembly. Questo metodo è deprecato. Utilizzare [ICorDebugCode2:: GetCodeChunks](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md) invece.|  
|[GetEnCRemapSequencePoints (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getencremapsequencepoints-method.md)|Non implementato.|  
|[GetFunction (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getfunction-method.md)|Ottiene il "ICorDebugFunction" associato a questo `ICorDebugCode`.|  
|[GetILToNativeMapping (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getiltonativemapping-method.md)|Ottiene una matrice di istanze di "COR_DEBUG_IL_TO_NATIVE_MAP" che rappresentano i mapping dagli offset MSIL agli offset nativi.|  
|[GetSize (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getsize-method.md)|Ottiene le dimensioni, in byte, del codice binario rappresentato da questo `ICorDebugCode`.|  
|[GetVersionNumber (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getversionnumber-method.md)|Ottiene il numero in base 1 che identifica la versione del codice da questo `ICorDebugCode` rappresenta.|  
|[IsIL (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-isil-method.md)|Ottiene un valore che indica se questo `ICorDebugCode` viene compilata in MSIL.|  
  
## <a name="remarks"></a>Note  
 `ICorDebugCode`può rappresentare MSIL o codice nativo. Un oggetto "ICorDebugFunction" che rappresenta il codice MSIL può avere zero o uno `ICorDebugCode` oggetti associati. Un oggetto "ICorDebugFunction" che rappresenta il codice nativo può avere un numero qualsiasi di `ICorDebugCode` oggetti associati.  
  
> [!NOTE]
>  Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
    
 [Interfaccia ICorDebugCode3](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)  
 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
