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
ms.openlocfilehash: 7a27b8ec512498c7bf817aca36267c37d8070a4c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788573"
---
# <a name="icordebugilframe-interface"></a>Interfaccia ICorDebugILFrame

Rappresenta una stack frame di codice MSIL (Microsoft Intermediate Language). Questa interfaccia è una sottoclasse dell'interfaccia ICorDebugFrame.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo CanSetIP](icordebugilframe-cansetip-method.md)|Ottiene un valore che indica se è sicuro impostare il puntatore all'istruzione sul percorso di offset specificato.|  
|[Metodo EnumerateArguments](icordebugilframe-enumeratearguments-method.md)|Ottiene un enumeratore per gli argomenti in questo frame.|  
|[Metodo EnumerateLocalVariables](icordebugilframe-enumeratelocalvariables-method.md)|Ottiene un enumeratore per le variabili locali in questo frame.|  
|[Metodo GetArgument](icordebugilframe-getargument-method.md)|Ottiene il valore dell'argomento specificato in questo stack frame MSIL.|  
|[Metodo GetIP](icordebugilframe-getip-method.md)|Ottiene il valore del puntatore all'istruzione e un valore di combinazione bit per bit che descrive il modo in cui è stato ottenuto il valore del puntatore all'istruzione.|  
|[Metodo GetLocalVariable](icordebugilframe-getlocalvariable-method.md)|Ottiene il valore della variabile locale specificata in questo stack frame MSIL.|  
|[Metodo GetStackDepth](icordebugilframe-getstackdepth-method.md)|Non implementato.|  
|[Metodo GetStackValue](icordebugilframe-getstackvalue-method.md)|Non implementato.|  
|[Metodo SetIP](icordebugilframe-setip-method.md)|Imposta il puntatore all'istruzione per la posizione di offset specificata nel codice MSIL.|  
  
## <a name="remarks"></a>Note  
 L'interfaccia `ICorDebugILFrame` è un'interfaccia ICorDebugFrame specializzata. Viene usato per i frame di codice MSIL o per i frame compilati JIT (just-in-Time). I frame compilati tramite JIT implementano sia l'interfaccia `ICorDebugILFrame` che l'interfaccia ICorDebugNativeFrame.  
  
> [!NOTE]
> Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](debugging-interfaces.md)
