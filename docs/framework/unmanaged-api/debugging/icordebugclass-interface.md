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
ms.openlocfilehash: 7ac588591222a1abbc7b99ec7e973284c055f95e
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76784160"
---
# <a name="icordebugclass-interface"></a>Interfaccia ICorDebugClass

Rappresenta un tipo, che può essere di base o complesso, ovvero definito dall'utente. Se il tipo è generico, `ICorDebugClass` rappresenta il tipo generico privo di istanze.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo GetModule](icordebugclass-getmodule-method.md)|Ottiene il modulo che definisce questa classe.|  
|[Metodo GetStaticFieldValue](icordebugclass-getstaticfieldvalue-method.md)|Ottiene il valore del campo statico specificato.|  
|[Metodo GetToken](icordebugclass-gettoken-method.md)|Ottiene il token di metadati `TypeDef` per questa classe.|  
  
## <a name="remarks"></a>Note  
 L'interfaccia `ICorDebugClass` rappresenta un tipo generico di cui non è stata creata un'istanza. L'interfaccia ICorDebugType rappresenta un tipo generico di cui è stata creata un'istanza. Ad esempio, `Hashtable<K, V>` viene rappresentata da `ICorDebugClass`, mentre `Hashtable<Int32, String>` viene rappresentata da `ICorDebugType`.  
  
 I tipi non generici sono rappresentati sia da `ICorDebugClass` che da `ICorDebugType`. Quest'ultima interfaccia è stata introdotta nella versione .NET Framework 2,0 per gestire la creazione dell'istanza del tipo.  
  
> [!NOTE]
> Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](debugging-interfaces.md)
