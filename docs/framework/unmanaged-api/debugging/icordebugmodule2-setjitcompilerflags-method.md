---
title: Metodo ICorDebugModule2::SetJITCompilerFlags
ms.date: 03/30/2017
api_name:
- ICorDebugModule2.SetJITCompilerFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule2::SetJITCompilerFlags
helpviewer_keywords:
- ICorDebugModule2::SetJITCompilerFlags method [.NET Framework debugging]
- SetJITCompilerFlags method [.NET Framework debugging]
ms.assetid: ea574c84-c622-4589-9a14-b55771af5e06
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c71ccbc62ea026a55a7e84f6925a78850594a813
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61942517"
---
# <a name="icordebugmodule2setjitcompilerflags-method"></a>Metodo ICorDebugModule2::SetJITCompilerFlags
Imposta i flag che controllano la compilazione just-in-time (JIT) di questa interfaccia ICorDebugModule2.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT SetJITCompilerFlags (  
    [in] DWORD dwFlags  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `dwFlags`  
 [in] Una combinazione bit per bit del [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) valori di enumerazione.  
  
## <a name="remarks"></a>Note  
 Se il `dwFlags` il valore è valido, il `SetJITCompilerFlags` metodo avrà esito negativo.  
  
 Il `SetJITCompilerFlags` metodo può essere chiamato solo dall'interno di [LoadModule](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadmodule-method.md) callback per questo modulo. Prova a chiamare una volta il `ICorDebugManagedCallback::LoadModule` callback è stato inviato avranno esito negativo.  
  
 Modifica e continuazione non è supportato in piattaforme Win9x o a 64 bit. Pertanto, se si chiama il `SetJITCompilerFlags` metodo su una di queste due piattaforme con il flag CORDEBUG_JIT_ENABLE_ENC impostato `dwFlags`, il `SetJITCompilerFlags` (metodo) e tutti i metodi specifici per modifica e continuazione, ad esempio [ICorDebugModule2:: ApplyChanges](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-applychanges-method.md), avrà esito negativo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
