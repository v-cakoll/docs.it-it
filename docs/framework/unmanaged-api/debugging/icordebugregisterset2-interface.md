---
title: Interfaccia ICorDebugRegisterSet2
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugRegisterSet2
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugRegisterSet2
helpviewer_keywords: ICorDebugRegisterSet2 interface [.NET Framework debugging]
ms.assetid: d7fbccbf-3b6b-4db8-a96d-768e1cb6b1a6
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 26967f50ded62f935a705c25eed58314b77bedd8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugregisterset2-interface"></a>Interfaccia ICorDebugRegisterSet2
Estende le funzionalità del [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) interfaccia per le piattaforme hardware con più di 64 registri.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[GetRegisters (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-getregisters-method.md)|Ottiene il valore di ogni registro (nel computer in cui è attualmente in esecuzione codice) specificato dalla maschera di bit.|  
|[GetRegistersAvailable (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-getregistersavailable-method.md)|Ottiene una matrice di byte che fornisce una bitmap dei registri disponibili.|  
|[SetRegisters (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-setregisters-method.md)|Non implementato in .NET Framework versione 2.0.|  
  
## <a name="remarks"></a>Note  
  
> [!NOTE]
>  Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [ICorDebugRegisterSet (interfaccia)](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
