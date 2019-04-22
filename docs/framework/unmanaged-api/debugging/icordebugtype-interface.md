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
ms.openlocfilehash: 74863af1096f8600b8095e593c1f3c820c512e9d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59166803"
---
# <a name="icordebugtype-interface"></a>Interfaccia ICorDebugType
Rappresenta un tipo di base o complesso (che è, definita dall'utente). Se il tipo è generico, `ICorDebugType` rappresenta il tipo generico di cui è stata creata un'istanza.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo EnumerateTypeParameters](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-enumeratetypeparameters-method.md)|Ottiene un puntatore a interfaccia a un'interfaccia ICorDebugTypeEnum che fa riferimento il tipo generico <xref:System.Type> parametri della classe a cui fa riferimento `ICorDebugType`.|  
|[Metodo GetBase](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getbase-method.md)|Ottiene un puntatore a interfaccia a un `ICorDebugType` che fa riferimento la classe di base della classe a cui fa riferimento `ICorDebugType`, se presente.|  
|[Metodo GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md)|Ottiene un puntatore a interfaccia ICorDebugClass che fa riferimento al costruttore dell'oggetto tipizzato `ICorDebugType`.|  
|[Metodo GetFirstTypeParameter](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getfirsttypeparameter-method.md)|Ottiene un puntatore a interfaccia a un `ICorDebugType` che fa riferimento il primo tipo generico <xref:System.Type> parametro per il costruttore della classe a cui fa riferimento `ICorDebugType`.|  
|[Metodo GetRank](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getrank-method.md)|Ottiene il numero di dimensioni in un tipo di matrice.|  
|[Metodo GetStaticFieldValue](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getstaticfieldvalue-method.md)|Ottiene un puntatore a interfaccia a ICorDebugValue che contiene il valore del campo statico a cui fa riferimento il campo specificato token lo stack frame specificato.|  
|[Metodo GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md)|Ottiene un valore CorElementType che descrive il tipo nativo del common language runtime <xref:System.Type> fa riferimento questo `ICorDebugType`.|  
  
## <a name="remarks"></a>Note  
 Se il tipo è generico, `ICorDebugClass` rappresenta il tipo privo di istanze. Il `ICorDebugType` interfaccia rappresenta un tipo generico con istanze. Ad esempio, Hashtable\<K, V > viene rappresentato da `ICorDebugClass`, mentre Hashtable\<Int32, String > sarebbe rappresentato da `ICorDebugType`.  
  
 I tipi non generici sono rappresentati da entrambi `ICorDebugClass` e `ICorDebugType`. L'interfaccia di quest'ultima è stato introdotto in .NET Framework versione 2.0 per gestire la creazione di istanze di tipo.  
  
> [!NOTE]
>  Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
