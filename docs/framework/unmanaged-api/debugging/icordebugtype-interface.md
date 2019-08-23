---
title: Interfaccia ICorDebugType
ms.date: 03/30/2017
api_name:
- ICorDebugType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType
helpviewer_keywords:
- ICorDebugType interface [.NET Framework debugging]
ms.assetid: 94e02e31-67ea-4b00-8148-a46740a4571d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b830af5d59c0eb177d815451ecedbdc14121aaad
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964752"
---
# <a name="icordebugtype-interface"></a>Interfaccia ICorDebugType
Rappresenta un tipo, di base o complesso, ovvero definito dall'utente. Se il tipo è generico, `ICorDebugType` rappresenta il tipo generico di cui è stata creata un'istanza.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo EnumerateTypeParameters](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-enumeratetypeparameters-method.md)|Ottiene un puntatore a interfaccia a un ICorDebugTypeEnum che fa riferimento <xref:System.Type> ai parametri generici della classe a cui `ICorDebugType`fa riferimento questo oggetto.|  
|[Metodo GetBase](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getbase-method.md)|Ottiene un puntatore a interfaccia a `ICorDebugType` un oggetto che fa riferimento alla classe di base della classe a `ICorDebugType`cui fa riferimento, se presente.|  
|[Metodo GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md)|Ottiene un puntatore a interfaccia a un ICorDebugClass che fa riferimento al costruttore tipizzato di questo `ICorDebugType`oggetto.|  
|[Metodo GetFirstTypeParameter](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getfirsttypeparameter-method.md)|Ottiene un puntatore a interfaccia a `ICorDebugType` un oggetto che fa riferimento <xref:System.Type> al primo parametro generico per il costruttore della classe a cui `ICorDebugType`fa riferimento questo oggetto.|  
|[Metodo GetRank](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getrank-method.md)|Ottiene il numero di dimensioni in un tipo di matrice.|  
|[Metodo GetStaticFieldValue](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getstaticfieldvalue-method.md)|Ottiene un puntatore a interfaccia a un ICorDebugValue che contiene il valore del campo statico a cui fa riferimento il token di campo specificato nell'stack frame specificato.|  
|[Metodo GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md)|Ottiene un valore CorElementType che descrive il tipo nativo del Common Language Runtime <xref:System.Type> a cui fa riferimento questo `ICorDebugType`oggetto.|  
  
## <a name="remarks"></a>Note  
 Se il tipo è generico, `ICorDebugClass` rappresenta il tipo di cui non è stata creata un'istanza. L' `ICorDebugType` interfaccia rappresenta un tipo generico di cui è stata creata un'istanza. Ad esempio, Hashtable\<K, V > verrebbe rappresentato da `ICorDebugClass`, mentre Hashtable\<Int32, String > verrebbe rappresentato da `ICorDebugType`.  
  
 I tipi non generici sono rappresentati `ICorDebugClass` sia `ICorDebugType`da che da. Quest'ultima interfaccia è stata introdotta nella versione .NET Framework 2,0 per gestire la creazione dell'istanza del tipo.  
  
> [!NOTE]
> Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug. idl, CorDebug. h  
  
 **Libreria** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
