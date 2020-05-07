---
title: Interfaccia ICorDebugClass
ms.date: 03/30/2017
api_name:
- ICorDebugClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass
helpviewer_keywords:
- ICorDebugClass interface [.NET Framework debugging]
ms.assetid: 03a6facb-f12f-49be-9839-e73b9c791cd5
topic_type:
- apiref
ms.openlocfilehash: d7417e8dc193172c77d23fe3fa72c8298d802b5c
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894048"
---
# <a name="icordebugclass-interface"></a>Interfaccia ICorDebugClass

Rappresenta un tipo, che può essere di base o complesso, ovvero definito dall'utente. Se il tipo è generico, `ICorDebugClass` rappresenta il tipo generico privo di istanze.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo GetModule](icordebugclass-getmodule-method.md)|Ottiene il modulo che definisce questa classe.|  
|[Metodo GetStaticFieldValue](icordebugclass-getstaticfieldvalue-method.md)|Ottiene il valore del campo statico specificato.|  
|[Metodo GetToken](icordebugclass-gettoken-method.md)|Ottiene il `TypeDef` token di metadati per questa classe.|  
  
## <a name="remarks"></a>Osservazioni  
 L' `ICorDebugClass` interfaccia rappresenta un tipo generico di cui non è stata creata un'istanza. L'interfaccia ICorDebugType rappresenta un tipo generico di cui è stata creata un'istanza. Ad esempio, `Hashtable<K, V>` verrebbe rappresentato da `ICorDebugClass`, mentre `Hashtable<Int32, String>` verrebbe rappresentato da. `ICorDebugType`  
  
 I tipi non generici sono rappresentati `ICorDebugClass` sia `ICorDebugType`da che da. Quest'ultima interfaccia è stata introdotta nella versione .NET Framework 2,0 per gestire la creazione dell'istanza del tipo.  
  
> [!NOTE]
> Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](debugging-interfaces.md)
