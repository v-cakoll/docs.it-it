---
title: Enumerazione ILCodeKind
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: cpp
api_name: ILCodeKind
api_location: mscordbi.dll
api_type: COM
ms.assetid: b91765e4-82db-46f9-a6dc-6b80610276af
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 61fd5ad93c198000556e8e0be3a278a842ab5716
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ilcodekind-enumeration"></a>Enumerazione ILCodeKind
[Supportato in .NET Framework 4.5.2 e versioni successive]  
  
 Fornisce valori che specificano se il debugger può accedere a variabili locali o a codice aggiunto nella strumentazione ReJIT del profiler.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp
typedef enum ILCodeKind {  
   ILCODE_ORIGINAL_IL = 0x1,  
   ILCODE_REJIT_IL = 0x2,  
} ILCodeKind;  
```  
  
## <a name="members"></a>Membri  
  
|Nome del membro|Descrizione|  
|-----------------|-----------------|  
|`ILCODE_ORIGINAL_IL`|Il debugger non ha accesso alle informazioni della strumentazione ReJIT.|  
|`ILCODE_REJIT_IL`|Il debugger ha accesso alle informazioni della strumentazione ReJIT.|  
  
## <a name="remarks"></a>Note  
 Un membro del `ILCodeKind` enumerazione può essere passato al [EnumerateLocalVariablesEx](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-enumeratelocalvariablesex-method.md) e [GetLocalVariableEx](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-getlocalvariableex-method.md) metodi per determinare se il debugger può accedere a variabili aggiunte nella profiler Strumentazione ReJIT e di ottenere il [GetCodeEx](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-getcodeex-method.md) metodo per determinare se il debugger può accedere al instrumentato.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Enumerazioni di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
 [Interfaccia ICorDebugILFrame4](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-interface.md)  
 [ReJIT: Una Guida dettagliata](http://blogs.msdn.com/b/davbr/archive/2011/10/12/rejit-a-how-to-guide.aspx)
