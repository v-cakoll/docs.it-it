---
title: Metodo ICorDebugCode2::GetCompilerFlags
ms.date: 03/30/2017
api_name:
- ICorDebugCode2.GetCompilerFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode2::GetCompilerFlags
helpviewer_keywords:
- GetCompilerFlags method [.NET Framework debugging]
- ICorDebugCode2::GetCompilerFlags method [.NET Framework debugging]
ms.assetid: 532e9dfd-d114-4c75-b952-1accce102643
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: df7ecd7403c915df89fe26a0ce9229b88691d19c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54667466"
---
# <a name="icordebugcode2getcompilerflags-method"></a>Metodo ICorDebugCode2::GetCompilerFlags
Ottiene i flag che specificano le condizioni in cui questo oggetto di codice è stato entrambi just-in-time (JIT) compilate o generate usando il generatore di immagini native (Ngen.exe).  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetCompilerFlags (  
    [out] DWORD *pdwFlags  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `pdwFlags`  
 [out] Un puntatore a un valore di [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) enumerazione che specifica il comportamento del compilatore JIT o il generatore di immagini native.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

