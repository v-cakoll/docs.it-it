---
title: Metodo ICoreClrDebugTarget::FreeMemory
ms.date: 03/30/2017
api_name:
- ICoreDebugTarget.FreeMemory
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- ICoreClrDebugTarget::FreeMemory
helpviewer_keywords:
- remote debugging API [Silverlight]
- FreeMemory method, ICoreClrDebugTarget interface [Silverlight debugging]
- ICorClrDebugTarget::FreeMemory method [Silverlight debugging]
- Silverlight, remote debugging
ms.assetid: 98f2a0db-a6ec-4f9b-861d-f82485237d08
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ec156ca7590a2ec637cb59e022fc2dd1a71226e0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59198504"
---
# <a name="icoreclrdebugtargetfreememory-method"></a>Metodo ICoreClrDebugTarget::FreeMemory
Libera la memoria allocata per il [ICoreClrDebugTarget:: EnumProcesses](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-enumprocesses-method.md) e [ICoreClrDebugTarget:: EnumRuntimes](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-enumruntimes-method.md) metodi.  
  
## <a name="syntax"></a>Sintassi  
  
```  
void FreeMemory (  
     [in] void*pMemory);  
```  
  
## <a name="parameters"></a>Parametri  
 `pMemory`  
 [in] Un puntatore alla matrice restituita tramite il [ICoreClrDebugTarget:: EnumProcesses](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-enumprocesses-method.md) o il [ICoreClrDebugTarget:: EnumRuntimes](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-enumruntimes-method.md) (metodo).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CoreClrRemoteDebuggingInterfaces.h  
  
 **Library:** mscordbi_macx86.dll  
  
 **Versioni di .NET framework:** 3.5 SP1  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICoreClrDebugTarget](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-interface.md)
