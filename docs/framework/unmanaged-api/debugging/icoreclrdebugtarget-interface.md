---
title: Interfaccia ICoreClrDebugTarget
ms.date: 03/30/2017
api_name:
- ICoreClrDebugTarget
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- ICoreClrDebugTarget
helpviewer_keywords:
- remote debugging API [Silverlight]
- ICorClrDebugTarget interface
- Silverlight, remote debugging
ms.assetid: 7cfaee76-e284-4a66-a431-8e33f0f60038
topic_type:
- apiref
ms.openlocfilehash: 190671b4f690f8c2cad43cf446a1196985ec5a42
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790745"
---
# <a name="icoreclrdebugtarget-interface"></a>Interfaccia ICoreClrDebugTarget
Fornisce metodi che controllano i conteggi dei riferimenti, enumerano i processi e liberano la memoria associata a un debugger collegato a una destinazione di Silverlight per Macintosh remota.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
class ICoreClrDebugTarget {  
      HRESULT EnumProcesses (  
          [out] DWORD*                    pcProcs,  
          [out] CoreClrDebugProcInfo**    ppProcs  
      );  
  
      HRESULT EnumRuntimes (  
      [in]  DWORD                      dwInternalProcessID,  
      [out] DWORD*                     pcRuntimes,  
      [out] CoreClrDebugRuntimeInfo**  ppRuntimes  
      );  
  
      void FreeMemory (  
      [in] void*      pMemory  
    );  
};  
```  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo ICoreClrDebugTarget::EnumProcesses](icoreclrdebugtarget-enumprocesses-method.md)|Enumera i processi in esecuzione in un computer remoto.|  
|[Metodo ICoreClrDebugTarget::EnumRuntimes](icoreclrdebugtarget-enumruntimes-method.md)|Enumera i Common Language Runtime (CLR) nel processo specificato in un computer remoto.|  
|[Metodo ICoreClrDebugTarget::FreeMemory](icoreclrdebugtarget-freememory-method.md)|Libera la memoria allocata dai metodi di enumerazione in questa classe.|  
  
## <a name="remarks"></a>Note  
 Questa funzionalità è attualmente supportata solo per il debug di una destinazione applicazione basata su Silverlight in esecuzione su un computer Macintosh remoto.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CoreClrRemoteDebuggingInterfaces. h  
  
 **Libreria:** mscordbi_macx86. dll  
  
 **Versioni .NET Framework:** 3,5 SP1  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugRemoteTarget](icordebugremotetarget-interface.md)
- [Interfaccia ICorDebug](icordebug-interface.md)

- [Interfacce di debug](debugging-interfaces.md)
