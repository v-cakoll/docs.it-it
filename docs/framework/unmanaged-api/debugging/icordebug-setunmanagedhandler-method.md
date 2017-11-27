---
title: Metodo ICorDebug::SetUnmanagedHandler
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebug.SetUnmanagedHandler
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebug::SetUnmanagerHandler
helpviewer_keywords:
- SetUnmanagedHandler method [.NET Framework debugging]
- ICorDebug::SetUnmanagedHandler method [.NET Framework debugging]
ms.assetid: 6b546be4-f86d-4536-8cfc-1d08e5066eb6
topic_type: apiref
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 658cbaeb10496ccd88e0abb3d2174289a820c2e6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugsetunmanagedhandler-method"></a>Metodo ICorDebug::SetUnmanagedHandler
Specifica l'oggetto di gestore eventi per gli eventi non gestiti.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT SetUnmanagedHandler (  
    [in] ICorDebugUnmanagedCallback  *pCallback  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `pCallback`  
 [in] Un puntatore a un [ICorDebugUnmanagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-interface.md) oggetto che rappresenta il gestore eventi per gli eventi non gestiti.  
  
## <a name="remarks"></a>Note  
 Il gestore dell'evento oggetto non gestito eventi devono essere impostati dopo una chiamata a [ICorDebug:: Initialize](../../../../docs/framework/unmanaged-api/debugging/icordebug-initialize-method.md) e prima delle chiamate a [ICorDebug:: CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md) o [ICorDebug:: DebugActiveProcess ](../../../../docs/framework/unmanaged-api/debugging/icordebug-debugactiveprocess-method.md). Per applicazioni legacy, non è tuttavia necessario impostare l'oggetto di gestore eventi per gli eventi non gestiti fino a quando non viene generato il primo evento di debug nativo. In particolare, se `ICorDebug::CreateProcess` ha impostato il flag CREATE_SUSPENDED, gli eventi non possono essere inviati fino a quando non viene ripreso il thread principale di debug nativo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
