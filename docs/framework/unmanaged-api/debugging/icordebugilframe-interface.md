---
title: Interfaccia ICorDebugILFrame
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame
helpviewer_keywords:
- ICorDebugILFrame interface [.NET Framework debugging]
ms.assetid: d5cf5056-da4d-4629-914d-afe42a5393df
topic_type:
- apiref
ms.openlocfilehash: 01c247f838f66d1a77831755126a5a1f56870c1e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73095137"
---
# <a name="icordebugilframe-interface"></a>Interfaccia ICorDebugILFrame

Rappresenta una stack frame di codice MSIL (Microsoft Intermediate Language). Questa interfaccia è una sottoclasse dell'interfaccia ICorDebugFrame.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo CanSetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-cansetip-method.md)|Ottiene un valore che indica se è sicuro impostare il puntatore all'istruzione sul percorso di offset specificato.|  
|[Metodo EnumerateArguments](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratearguments-method.md)|Ottiene un enumeratore per gli argomenti in questo frame.|  
|[Metodo EnumerateLocalVariables](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratelocalvariables-method.md)|Ottiene un enumeratore per le variabili locali in questo frame.|  
|[Metodo GetArgument](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getargument-method.md)|Ottiene il valore dell'argomento specificato in questo stack frame MSIL.|  
|[Metodo GetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getip-method.md)|Ottiene il valore del puntatore all'istruzione e un valore di combinazione bit per bit che descrive il modo in cui è stato ottenuto il valore del puntatore all'istruzione.|  
|[Metodo GetLocalVariable](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md)|Ottiene il valore della variabile locale specificata in questo stack frame MSIL.|  
|[Metodo GetStackDepth](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getstackdepth-method.md)|Non implementato.|  
|[Metodo GetStackValue](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getstackvalue-method.md)|Non implementato.|  
|[Metodo SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md)|Imposta il puntatore all'istruzione per la posizione di offset specificata nel codice MSIL.|  
  
## <a name="remarks"></a>Note  
 L'interfaccia `ICorDebugILFrame` è un'interfaccia ICorDebugFrame specializzata. Viene usato per i frame di codice MSIL o per i frame compilati JIT (just-in-Time). I frame compilati tramite JIT implementano sia l'interfaccia `ICorDebugILFrame` che l'interfaccia ICorDebugNativeFrame.  
  
> [!NOTE]
> Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
