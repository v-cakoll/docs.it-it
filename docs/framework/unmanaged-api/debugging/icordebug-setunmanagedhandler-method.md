---
title: Metodo ICorDebug::SetUnmanagedHandler
ms.date: 03/30/2017
api_name:
- ICorDebug.SetUnmanagedHandler
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::SetUnmanagerHandler
helpviewer_keywords:
- SetUnmanagedHandler method [.NET Framework debugging]
- ICorDebug::SetUnmanagedHandler method [.NET Framework debugging]
ms.assetid: 6b546be4-f86d-4536-8cfc-1d08e5066eb6
topic_type:
- apiref
ms.openlocfilehash: 7c3251b2cf7a4d0d97df0e6ecc9b332e3ed8e500
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895331"
---
# <a name="icordebugsetunmanagedhandler-method"></a>Metodo ICorDebug::SetUnmanagedHandler
Specifica l'oggetto gestore eventi per gli eventi non gestiti.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT SetUnmanagedHandler (  
    [in] ICorDebugUnmanagedCallback  *pCallback  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pCallback`  
 in Puntatore a un oggetto [ICorDebugUnmanagedCallback](icordebugunmanagedcallback-interface.md) che rappresenta il gestore eventi per gli eventi non gestiti.  
  
## <a name="remarks"></a>Osservazioni  
 L'oggetto gestore eventi per gli eventi non gestiti deve essere impostato dopo una chiamata a [ICorDebug:: Initialize](icordebug-initialize-method.md) e prima di qualsiasi chiamata a [ICorDebug:: CreateProcess](icordebug-createprocess-method.md) o [ICorDebug::D ebugactiveprocess](icordebug-debugactiveprocess-method.md). Per gli scopi legacy, tuttavia, non è necessario impostare l'oggetto gestore eventi per gli eventi non gestiti fino a quando non viene generato il primo evento di debug nativo. In particolare, `ICorDebug::CreateProcess` se ha impostato il flag di CREATE_SUSPENDED, non è possibile inviare gli eventi di debug nativi finché il thread principale non viene ripreso.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebug](icordebug-interface.md)
