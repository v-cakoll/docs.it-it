---
title: Struttura COR_TYPEID
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_TYPEID
api_location: mscordbi.dll
api_type: COM
f1_keywords: COR_TYPEID
helpviewer_keywords: COR_TYPEID structure [.NET Framework debugging]
ms.assetid: 1e172b14-ee22-4943-b3b8-3740e7bdcd2e
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 795dea77ac8dac1e1d22574c23f1e1c13344a71a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="cortypeid-structure"></a>Struttura COR_TYPEID
Contiene un identificatore di tipo.  
  
## <a name="syntax"></a>Sintassi  
  
```  
typedef struct COR_TYPEID{  
    UINT64 token1;  
    UINT64 token2;  
} COR_TYPEID;  
```  
  
## <a name="members"></a>Membri  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`token1`|Il primo token.|  
|`token2`|Il secondo token.|  
  
## <a name="remarks"></a>Note  
 Il `COR_TYPEID` struttura viene restituita da una serie di metodi di debug che forniscono informazioni sugli oggetti da sottoporre a garbage collection. Può quindi essere passato come argomento ad altri metodi di debug che forniscono informazioni aggiuntive su tale elemento. Ad esempio, enumerando un [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) dell'oggetto, è possibile recuperare singoli [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) gli oggetti che rappresentano i singoli oggetti nell'heap gestito. È quindi possibile passare il `COR_TYPEID` valore il `COR_HEAPOBJECT.type` campo il [icordebugprocess5:: Gettypefortypeid](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefortypeid-method.md) metodo per recuperare un oggetto ICorDebugType che fornisce informazioni sul tipo relative all'oggetto.  
  
 Oggetto `COR_TYPEID` oggetto deve essere opaca. I singoli campi non devono essere accessibile oppure modificati. L'uso esclusivo è un identificatore che viene fornito come un `out` parametro in una chiamata al metodo e che può essere passato a sua volta, agli altri metodi per fornire informazioni aggiuntive.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Strutture di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [Debug](../../../../docs/framework/unmanaged-api/debugging/index.md)
