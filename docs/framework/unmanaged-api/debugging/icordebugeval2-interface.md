---
title: ICorDebugEval2 Interface1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugEval2
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugEval2
helpviewer_keywords: ICorDebugEval2 interface [.NET Framework debugging]
ms.assetid: fce34531-2687-406d-9131-d6ad94f2ce0e
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: fbcf36ff7aca84299c55083b4ae135ce0a9ec4f3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugeval2-interface1"></a>ICorDebugEval2 Interface1
Estende "ICorDebugEval" per fornire il supporto per i tipi generici.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[CallParameterizedFunction (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-callparameterizedfunction-method.md)|Imposta una chiamata all'oggetto specificato "ICorDebugFunction", che può essere annidata all'interno di un tipo il cui costruttore accetta parametri di tipo, o che può accettare direttamente i parametri di tipo.|  
|[CreateValueForType (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-createvaluefortype-method.md)|Ottiene un puntatore a un nuovo "ICorDebugValue" del tipo specificato, con un valore iniziale pari a zero o null.|  
|[NewParameterizedArray (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedarray-method.md)|Alloca una nuova matrice del tipo di elemento specificato e le dimensioni.|  
|[NewParameterizedObject (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobject-method.md)|Crea un nuovo oggetto di tipo con parametri e chiama il metodo costruttore dell'oggetto.|  
|[NewParameterizedObjectNoConstructor (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobjectnoconstructor-method.md)|Crea un nuovo oggetto di tipo con parametri della classe specificata senza tentare di chiamare un metodo del costruttore|  
|[NewStringWithLength (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newstringwithlength-method.md)|Crea una nuova stringa di lunghezza specificata con il contenuto specificato.|  
|[RudeAbort (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-rudeabort-method.md)|Interrompe il calcolo da questo `ICorDebugEval2` attualmente in esecuzione.|  
  
## <a name="remarks"></a>Note  
  
> [!NOTE]
>  Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
