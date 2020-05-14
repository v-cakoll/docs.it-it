---
title: Interfaccia ICorDebugValueBreakpoint
ms.date: 03/30/2017
api_name:
- ICorDebugValueBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValueBreakpoint
helpviewer_keywords:
- ICorDebugValueBreakpoint interface [.NET Framework debugging]
ms.assetid: c02338fe-da6c-467f-9567-70ebb387e901
topic_type:
- apiref
ms.openlocfilehash: 1183f9f6d1ac221b20767f0a1bab15b3e9665a61
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396604"
---
# <a name="icordebugvaluebreakpoint-interface"></a>Interfaccia ICorDebugValueBreakpoint
Estende l'interfaccia ICorDebugBreakpoint per fornire l'accesso a valori specifici.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo GetValue](icordebugvaluebreakpoint-getvalue-method.md)|Ottiene un puntatore a interfaccia a un oggetto ICorDebugValue che rappresenta il valore dell'oggetto su cui è impostato il punto di interruzione.|  
  
## <a name="remarks"></a>Commenti  
  
> [!NOTE]
> Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedi anche

- [Interfacce di debug](debugging-interfaces.md)
