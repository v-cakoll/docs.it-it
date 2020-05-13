---
title: Interfaccia ICorDebugNativeFrame
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame
helpviewer_keywords:
- ICorDebugNativeFrame interface [.NET Framework debugging]
ms.assetid: 04819c58-7246-4b32-befb-680cf1dbc436
topic_type:
- apiref
ms.openlocfilehash: dd87745a29514a2f9f05aa142baae4e05d4b4a7b
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83206607"
---
# <a name="icordebugnativeframe-interface"></a>Interfaccia ICorDebugNativeFrame

Implementazione specializzata di ICorDebugFrame utilizzata per i frame nativi.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo CanSetIP](icordebugnativeframe-cansetip-method.md)|Ottiene un valore che indica se è sicuro impostare il puntatore all'istruzione sul percorso di offset specificato nel codice nativo.|  
|[Metodo GetIP](icordebugnativeframe-getip-method.md)|Ottiene l'offset del stack frame nel codice nativo.|  
|[Metodo GetLocalDoubleRegisterValue](icordebugnativeframe-getlocaldoubleregistervalue-method.md)|Ottiene un puntatore a un ICorDebugValue che rappresenta il valore di un argomento o di una variabile locale archiviata in due registri di memoria di un frame nativo.|  
|[Metodo GetLocalMemoryRegisterValue](icordebugnativeframe-getlocalmemoryregistervalue-method.md)|Ottiene un puntatore a un oggetto `ICorDebugValue` che rappresenta il valore di una variabile locale, di cui i bit bassi vengono archiviati nel registro specificato e i bit massimi vengono archiviati nell'indirizzo di memoria specificato.|  
|[Metodo GetLocalMemoryValue](icordebugnativeframe-getlocalmemoryvalue-method.md)|Ottiene un puntatore a un oggetto `ICorDebugValue` che rappresenta il valore di una variabile locale archiviata nell'indirizzo di memoria specificato.|  
|[Metodo GetLocalRegisterMemoryValue](icordebugnativeframe-getlocalregistermemoryvalue-method.md)|Ottiene un puntatore a un oggetto `ICorDebugValue` che rappresenta il valore di una variabile locale, di cui i bit massimi vengono archiviati nel registro specificato e i bit bassi vengono archiviati nell'indirizzo di memoria specificato.|  
|[Metodo GetLocalRegisterValue](icordebugnativeframe-getlocalregistervalue-method.md)|Ottiene un puntatore a un oggetto `ICorDebugValue` che rappresenta il valore di un argomento o una variabile locale archiviata nel registro nativo specificato.|  
|[Metodo GetRegisterSet](icordebugnativeframe-getregisterset-method.md)|Ottiene un puntatore a un [ICorDebugRegisterSet](icordebugregisterset-interface.md) che rappresenta il set di registri per questo oggetto `ICorDebugNativeFrame` .|  
|[Metodo SetIP](icordebugnativeframe-setip-method.md)|Imposta il puntatore all'istruzione per la posizione di offset specificata nel codice nativo.|  
  
## <a name="remarks"></a>Osservazioni  
  
> [!NOTE]
> Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](debugging-interfaces.md)
