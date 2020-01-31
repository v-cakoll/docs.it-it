---
title: Metodo ICorDebug::SetManagedHandler
ms.date: 03/30/2017
api_name:
- ICorDebug.SetManagedHandler
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::SetManagedHandler
helpviewer_keywords:
- ICorDebug::SetManagedHandler method [.NET Framework debugging]
- SetManagedHandler method [.NET Framework debugging]
ms.assetid: d079131b-685b-4869-95be-826b88d28bd2
topic_type:
- apiref
ms.openlocfilehash: 54ef1cab27a39de39b39996729be6b8160570745
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788964"
---
# <a name="icordebugsetmanagedhandler-method"></a>Metodo ICorDebug::SetManagedHandler
Specifica l'oggetto gestore eventi per gli eventi gestiti.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT SetManagedHandler (  
    [in] ICorDebugManagedCallback     *pCallback  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pCallback`  
 in Puntatore a un oggetto [ICorDebugManagedCallback](icordebugmanagedcallback-interface.md) , che è l'oggetto del gestore eventi.  
  
## <a name="remarks"></a>Note  
 `SetManagedHandler` deve essere chiamato in fase di creazione.  
  
 Se l'implementazione del `ICorDebugManagedCallback` non contiene interfacce sufficienti per gestire gli eventi di debug per l'applicazione di cui è in corso il debug, `SetManagedHandler` restituisce un valore HRESULT di E_NOINTERFACE.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebug](icordebug-interface.md)
