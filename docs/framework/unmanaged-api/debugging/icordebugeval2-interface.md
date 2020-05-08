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
ms.openlocfilehash: b597d95b5b25e5ebf04fac48e4f3fda312a9594c
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976122"
---
# <a name="icordebugeval2-interface"></a>Interfaccia ICorDebugEval2

Estende "ICorDebugEval" per fornire supporto per i tipi generici.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo CallParameterizedFunction](icordebugeval2-callparameterizedfunction-method.md)|Imposta una chiamata all'oggetto "ICorDebugFunction" specificato, che può essere annidato all'interno di un tipo il cui costruttore accetta parametri di tipo oppure accetta parametri di tipo.|  
|[Metodo CreateValueForType](icordebugeval2-createvaluefortype-method.md)|Ottiene un puntatore a un nuovo oggetto "ICorDebugValue" del tipo specificato, con un valore iniziale null o zero.|  
|[Metodo NewParameterizedArray](icordebugeval2-newparameterizedarray-method.md)|Alloca una nuova matrice del tipo e delle dimensioni dell'elemento specificato.|  
|[Metodo NewParameterizedObject](icordebugeval2-newparameterizedobject-method.md)|Crea un'istanza di un nuovo oggetto di tipo con parametri e chiama il metodo del costruttore dell'oggetto.|  
|[Metodo NewParameterizedObjectNoConstructor](icordebugeval2-newparameterizedobjectnoconstructor-method.md)|Crea un'istanza di un nuovo oggetto di tipo con parametri della classe specificata senza provare a chiamare un metodo del costruttore|  
|[Metodo NewStringWithLength](icordebugeval2-newstringwithlength-method.md)|Crea una nuova stringa della lunghezza specificata con il contenuto specificato.|  
|[Metodo RudeAbort](icordebugeval2-rudeabort-method.md)|Interrompe il calcolo `ICorDebugEval2` attualmente in esecuzione.|  
  
## <a name="remarks"></a>Osservazioni  
  
> [!NOTE]
> Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](debugging-interfaces.md)
