---
title: Interfaccia ICorDebugValue2
ms.date: 03/30/2017
api_name:
- ICorDebugValue2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue2
helpviewer_keywords:
- ICorDebugValue2 interface [.NET Framework debugging]
ms.assetid: 3ff2ad2a-da5a-461b-8627-1a8eba49df9c
topic_type:
- apiref
ms.openlocfilehash: d036ddf353aa3a622ade05e1e2daa7f170d28f63
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396770"
---
# <a name="icordebugvalue2-interface"></a>Interfaccia ICorDebugValue2
Estende l'interfaccia "ICorDebugValue" per fornire supporto per gli oggetti "ICorDebugType".  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo GetExactType](icordebugvalue2-getexacttype-method.md)|Ottiene un puntatore a interfaccia a un `ICorDebugType` oggetto che rappresenta l'oggetto <xref:System.Type> di questo valore.|  
  
## <a name="remarks"></a>Commenti  
  
> [!NOTE]
> Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedi anche

- [Interfacce di debug](debugging-interfaces.md)

- [Interfaccia ICorDebugValue3](icordebugvalue3-interface.md)
