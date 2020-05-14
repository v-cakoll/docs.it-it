---
title: Metodo ICoreClrDebugTarget::EnumProcesses
ms.date: 03/30/2017
api_name:
- ICoreClrDebugTarget.EnumProcesses
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- ICoreClrDebugTarget::EnumProcesses
helpviewer_keywords:
- remote debugging API [Silverlight]
- EnumProcesses method, ICorClrDebugTarget interface [Silverlight debugging]
- ICorClrDebugTarget::EnumProcesses method [Silverlight debugging]
- Silverlight, remote debugging
ms.assetid: e00fd477-4f49-43d3-bd0e-3094824b1136
topic_type:
- apiref
ms.openlocfilehash: 0c1b18f24fd30b5f6d5e85633fc0c25839aba6df
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396412"
---
# <a name="icoreclrdebugtargetenumprocesses-method"></a>Metodo ICoreClrDebugTarget::EnumProcesses
Enumera i processi in esecuzione in un computer remoto.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT EnumProcesses (  
       [out]  DWORD*                  pcProcs,
       [out]  CoreClrDebugProcInfo**  ppProcs  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pcProcs`  
 [out] Numero di processi restituiti in `ppProcs`. Il valore può essere 0 (zero).  
  
 `ppProcs`  
 out Matrice di strutture [CoreClrDebugProcInfo](coreclrdebugprocinfo-structure.md) che rappresentano i processi in esecuzione nel computer remoto.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK  
 Operazione completata.  
  
 E_OUTOFMEMORY  
 Non è possibile allocare memoria sufficiente per `ppProcs`.  
  
 E_FAIL (o altri codici E_ restituiti)  
 Altri errori.  
  
## <a name="remarks"></a>Commenti  
 Per liberare la memoria allocata da questo metodo, chiamare il metodo [ICoreClrDebugTarget:: FreeMemory](icoreclrdebugtarget-freememory-method.md) .  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CoreClrRemoteDebuggingInterfaces. h  
  
 **Libreria:** mscordbi_macx86. dll  
  
 **Versioni .NET Framework:** 3,5 SP1  
  
## <a name="see-also"></a>Vedi anche

- [Interfaccia ICoreClrDebugTarget](icoreclrdebugtarget-interface.md)
