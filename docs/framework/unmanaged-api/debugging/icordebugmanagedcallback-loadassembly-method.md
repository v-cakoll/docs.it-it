---
title: Metodo ICorDebugManagedCallback::LoadAssembly
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.LoadAssembly
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::LoadAssembly
helpviewer_keywords:
- LoadAssembly method [.NET Framework debugging]
- ICorDebugManagedCallback::LoadAssembly method [.NET Framework debugging]
ms.assetid: 55cb673a-e240-43a6-a406-6912e7c0fe66
topic_type:
- apiref
ms.openlocfilehash: 80836cbbf82a97ccd6dc7251e5cbe934e0cbe66f
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76777281"
---
# <a name="icordebugmanagedcallbackloadassembly-method"></a>Metodo ICorDebugManagedCallback::LoadAssembly
Notifica al debugger che un assembly Common Language Runtime (CLR) è stato caricato correttamente.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT LoadAssembly (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugAssembly  *pAssembly  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pAppDomain`  
 in Puntatore a un oggetto ICorDebugAppDomain che rappresenta il dominio applicazione in cui è stato caricato l'assembly.  
  
 `pAssembly`  
 in Puntatore a un oggetto ICorDebugAssembly che rappresenta l'assembly.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Metodo UnloadAssembly](icordebugmanagedcallback-unloadassembly-method.md)
- [Interfaccia ICorDebugManagedCallback](icordebugmanagedcallback-interface.md)
