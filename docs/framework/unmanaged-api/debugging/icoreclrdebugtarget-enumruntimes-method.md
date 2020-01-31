---
title: Metodo ICoreClrDebugTarget::EnumRuntimes
ms.date: 03/30/2017
api_name:
- ICoreClrDebugTarget.EnumRuntimes
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- ICoreClrDebugTarget::EnumRuntimes
helpviewer_keywords:
- remote debugging API [Silverlight]
- ICorClrDebugTarget::EnumRuntimes method [Silverlight debugging]
- EnumRuntimes method, ICoreClrDebugTarget interface [Silverlight debugging]
- Silverlight, remote debugging
ms.assetid: 316df866-442d-40cc-b049-45e8adcb65d1
topic_type:
- apiref
ms.openlocfilehash: 4b55ac1d895bfecbe74be447bd06f4aa22b9d04f
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790785"
---
# <a name="icoreclrdebugtargetenumruntimes-method"></a>Metodo ICoreClrDebugTarget::EnumRuntimes
Enumera i Common Language Runtime (CLR) nel processo specificato in cui è in esecuzione in un computer remoto.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT EnumRuntimes (  
      [in] DWORD       dwInternalProcessID,  
      [out] DWORD*     pcRuntimes,  
      [out] CoreClrDebugRuntimeInfo**    ppRuntimes  
    );  
```  
  
## <a name="parameters"></a>Parametri  
 `dwInternalProcessID`  
 [in] ID del processo interno per il quale si vogliono enumerare i runtime. Questa operazione verrà `m_dwInternalID` dal [CoreClrDebugProcInfo](coreclrdebugprocinfo-structure.md)corrispondente.  
  
 `pcRuntimes`  
 [out] Numero di runtime restituiti in `ppRuntimes`. Il valore può essere 0 (zero).  
  
 `ppRuntimes`  
 out Matrice di strutture [CoreClrDebugRuntimeInfo](coreclrdebugruntimeinfo-structure.md) che rappresentano i runtime caricati nel processo di destinazione remoto.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK  
 Operazione completata.  
  
 S_FALSE  
 `dwInternalProcessID` non corrisponde a nessun processo in esecuzione nel computer, probabilmente perché il processo è stato terminato. `pcRuntimes` e `ppRuntimes` saranno null.  
  
 E_OUTOFMEMORY  
 Non è possibile allocare memoria sufficiente per `ppRuntimes`.  
  
 E_FAIL (o altri codici E_ restituiti)  
 Altri errori.  
  
## <a name="remarks"></a>Note  
 Per liberare la memoria allocata da questo metodo, chiamare il metodo [ICoreClrDebugTarget:: FreeMemory](icoreclrdebugtarget-freememory-method.md) .  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CoreClrRemoteDebuggingInterfaces. h  
  
 **Libreria:** mscordbi_macx86. dll  
  
 **Versioni .NET Framework:** 3,5 SP1  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICoreClrDebugTarget](icoreclrdebugtarget-interface.md)
