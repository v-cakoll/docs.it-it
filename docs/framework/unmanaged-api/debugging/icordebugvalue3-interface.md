---
title: Interfaccia ICorDebugValue3
ms.date: 03/30/2017
api_name:
- ICorDebugValue3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue3
helpviewer_keywords:
- ICorDebugValue3 interface [.NET Framework debugging]
ms.assetid: 7d5385d3-f4a5-47c4-8478-a3513b5e9406
topic_type:
- apiref
ms.openlocfilehash: 9f521eb942f37b8cf1d00bcc672071a69692b876
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396641"
---
# <a name="icordebugvalue3-interface"></a>Interfaccia ICorDebugValue3
Estende le interfacce "ICorDebugValue" e "ICorDebugValue2" per fornire supporto per matrici di dimensioni maggiori di 2 GB.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo GetSize64](icordebugvalue3-getsize64-method.md)|Ottiene le dimensioni in byte di questo `ICorDebugValue3` oggetto.|  
  
## <a name="remarks"></a>Commenti  
 Il metodo [ICorDebugValue:: GetSize](icordebugvalue3-getsize64-method.md) restituisce le dimensioni dell'oggetto che variano da 0 a 2.147.483.647 byte. Nella .NET Framework 4,5, le dimensioni delle matrici possono superare i 2 GB. L' `ICorDebugValue3` interfaccia consente di determinare le dimensioni di queste matrici.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedi anche

- [Interfacce di debug](debugging-interfaces.md)
- [Debug](index.md)
