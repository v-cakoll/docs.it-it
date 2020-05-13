---
title: Interfaccia ICorDebugILCode2
ms.date: 03/30/2017
api_name:
- ICorDebugILCode2
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: f9dc2afd-df8a-464d-bdbf-5af0a1d4bf85
topic_type:
- apiref
ms.openlocfilehash: 65995e8386b3bc686178b79d4fbb21a7c71bed3e
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210332"
---
# <a name="icordebugilcode2-interface"></a>Interfaccia ICorDebugILCode2
[Supportato in .NET Framework 4.5.2 e versioni successive]  
  
 Estende logicamente l'interfaccia [ICorDebugILCode](icordebugilcode-interface.md) per fornire i metodi che restituiscono il token per la firma della variabile locale di una funzione e che mappano gli offset del linguaggio intermedio (il) instrumentato del profiler agli offset il di metodo originali.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo GetInstrumentedILMap](icordebugilcode2-getinstrumentedilmap-method.md)|Restituisce una mappa dagli offset IL instrumentati dal profiler agli offset IL elaborati con il metodo originale per l'istanza corrente.|  
|[Metodo GetLocalVarSigToken](icordebugilcode2-getlocalvarsigtoken-method.md)|Ottiene il token di metadati per la firma di una variabile locale della funzione rappresentata da questa istanza.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugILCode](icordebugilcode-interface.md)
- [Interfacce di debug](debugging-interfaces.md)
- [Debug](index.md)
