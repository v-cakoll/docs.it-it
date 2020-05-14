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
ms.openlocfilehash: 5e88652ff75223e30e6abc454f1e1af91494c7b2
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396696"
---
# <a name="icordebugtype-interface"></a>Interfaccia ICorDebugType
Rappresenta un tipo, di base o complesso, ovvero definito dall'utente. Se il tipo è generico, `ICorDebugType` rappresenta il tipo generico di cui è stata creata un'istanza.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo EnumerateTypeParameters](icordebugtype-enumeratetypeparameters-method.md)|Ottiene un puntatore a interfaccia a un ICorDebugTypeEnum che fa riferimento ai parametri generici <xref:System.Type> della classe a cui fa riferimento questo oggetto `ICorDebugType` .|  
|[Metodo GetBase](icordebugtype-getbase-method.md)|Ottiene un puntatore a interfaccia a un oggetto `ICorDebugType` che fa riferimento alla classe di base della classe a cui fa riferimento `ICorDebugType` , se presente.|  
|[Metodo GetClass](icordebugtype-getclass-method.md)|Ottiene un puntatore a interfaccia a un ICorDebugClass che fa riferimento al costruttore tipizzato di questo oggetto `ICorDebugType` .|  
|[Metodo GetFirstTypeParameter](icordebugtype-getfirsttypeparameter-method.md)|Ottiene un puntatore a interfaccia a un oggetto `ICorDebugType` che fa riferimento al primo <xref:System.Type> parametro generico per il costruttore della classe a cui fa riferimento questo oggetto `ICorDebugType` .|  
|[Metodo GetRank](icordebugtype-getrank-method.md)|Ottiene il numero di dimensioni in un tipo di matrice.|  
|[Metodo GetStaticFieldValue](icordebugtype-getstaticfieldvalue-method.md)|Ottiene un puntatore a interfaccia a un ICorDebugValue che contiene il valore del campo statico a cui fa riferimento il token di campo specificato nell'stack frame specificato.|  
|[Metodo GetType](icordebugtype-gettype-method.md)|Ottiene un valore CorElementType che descrive il tipo nativo del Common Language Runtime a <xref:System.Type> cui fa riferimento questo oggetto `ICorDebugType` .|  
  
## <a name="remarks"></a>Commenti  
 Se il tipo è generico, rappresenta il tipo di cui non è stata `ICorDebugClass` creata un'istanza. L' `ICorDebugType` interfaccia rappresenta un tipo generico di cui è stata creata un'istanza. Ad esempio, Hashtable \< K, V> verrebbe rappresentato da `ICorDebugClass` , mentre Hashtable \< Int32, String> verrebbe rappresentato da `ICorDebugType` .  
  
 I tipi non generici sono rappresentati sia da `ICorDebugClass` che da `ICorDebugType` . Quest'ultima interfaccia è stata introdotta nella versione .NET Framework 2,0 per gestire la creazione dell'istanza del tipo.  
  
> [!NOTE]
> Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedi anche

- [Interfacce di debug](debugging-interfaces.md)
