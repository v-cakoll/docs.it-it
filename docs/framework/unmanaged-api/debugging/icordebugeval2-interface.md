---
title: Interfaccia ICorDebugEval2
ms.date: 03/30/2017
api_name:
- ICorDebugEval2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2
helpviewer_keywords:
- ICorDebugEval2 interface [.NET Framework debugging]
ms.assetid: fce34531-2687-406d-9131-d6ad94f2ce0e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d4315c9f5296e8c3ffc9d8241b929c71c2448db6
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56965865"
---
# <a name="icordebugeval2-interface"></a>Interfaccia ICorDebugEval2

Estende "ICorDebugEval" per fornire supporto per i tipi generici.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo CallParameterizedFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-callparameterizedfunction-method.md)|Imposta una chiamata all'oggetto specificato "ICorDebugFunction", che possono essere annidate all'interno di un tipo il cui costruttore accetta parametri di tipo oppure può accettare direttamente i parametri di tipo.|  
|[Metodo CreateValueForType](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-createvaluefortype-method.md)|Ottiene un puntatore a un nuovo "ICorDebugValue" del tipo specificato, con un valore iniziale pari a zero o null.|  
|[Metodo NewParameterizedArray](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedarray-method.md)|Consente di allocare una nuova matrice del tipo di elemento specificato e le dimensioni.|  
|[Metodo NewParameterizedObject](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobject-method.md)|Crea un'istanza di un nuovo oggetto di tipo con parametri e chiama il metodo costruttore dell'oggetto.|  
|[Metodo NewParameterizedObjectNoConstructor](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobjectnoconstructor-method.md)|Crea un'istanza di un nuovo oggetto di tipo con parametri della classe specificata senza effettuare alcun tentativo di chiamare un metodo del costruttore|  
|[Metodo NewStringWithLength](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newstringwithlength-method.md)|Crea una nuova stringa di lunghezza specificata con il contenuto specificato.|  
|[Metodo RudeAbort](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-rudeabort-method.md)|Interrompe il calcolo da questo `ICorDebugEval2` attualmente in esecuzione.|  
  
## <a name="remarks"></a>Note  
  
> [!NOTE]
>  Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
