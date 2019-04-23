---
title: Metodo ICorDebugRegisterSet::SetThreadContext
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet.SetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet::SetThreadContext
helpviewer_keywords:
- ICorDebugRegisterSet::SetThreadContext method [.NET Framework debugging]
- SetThreadContext method, ICorDebugRegisterSet interface [.NET Framework debugging]
ms.assetid: 73afa930-32cb-4c40-81f8-83e8e6fbe213
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7b1ea34c187de99d23b05b5e1a30c53bc54a6c0c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59197399"
---
# <a name="icordebugregistersetsetthreadcontext-method"></a>Metodo ICorDebugRegisterSet::SetThreadContext
`SetThreadContext` non è implementata in .NET Framework versione 2.0. Non chiamare questo metodo.  
  
> [!NOTE]
>  Usare l'operazione di livello superiore [ICorDebugNativeFrame](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md) per impostare il contesto di un thread.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT SetThreadContext (  
    [in] ULONG32 contextSize,  
    [in, length_is(contextSize),  
         size_is(contextSize)] BYTE context[]  
);  
```  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:** 1.1, 1.0  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
- [Interfaccia ICorDebugRegisterSet2](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
