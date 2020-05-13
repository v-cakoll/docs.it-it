---
title: Interfaccia ICorDebugFunction3
ms.date: 03/30/2017
api_name:
- ICorDebugFunction3
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: b22717b9-ead5-4eea-887e-789b52d613dc
topic_type:
- apiref
ms.openlocfilehash: 71aa482cc2268da17f1376d8c305dd6a818d92d0
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213166"
---
# <a name="icordebugfunction3-interface"></a>Interfaccia ICorDebugFunction3
[Supportato in .NET Framework 4.5.2 e versioni successive]  
  
 Estende a livello logico l'interfaccia ICorDebugFunction in modo da fornire accesso al codice da una richiesta ReJIT.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo GetActiveReJitRequestILCode](icordebugfunction3-getactiverejitrequestilcode-method.md)|Ottiene un puntatore a interfaccia a un [ICorDebugILCode](icordebugilcode-interface.md) che contiene il il da una richiesta ReJIT attiva.|  
  
## <a name="remarks"></a>Osservazioni  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](debugging-interfaces.md)
- [Debug](index.md)
- [ReJIT: Guida alle procedure](https://docs.microsoft.com/archive/blogs/davbr/rejit-a-how-to-guide)
