---
title: Metodo ICorDebugProcess2::GetDesiredNGENCompilerFlags
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.GetDesiredNGENCompilerFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::GetDesiredNGENCompilerFlags
helpviewer_keywords:
- ICorDebugProcess2::GetDesiredNGENCompilerFlags method [.NET Framework debugging]
- GetDesiredNGENCompilerFlags method [.NET Framework debugging]
ms.assetid: fc834580-3a90-4315-95d2-349b6bb7d059
topic_type:
- apiref
ms.openlocfilehash: 015735e1c6c3b6c146f2fca3a9bdc28baeca2f92
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792513"
---
# <a name="icordebugprocess2getdesiredngencompilerflags-method"></a>Metodo ICorDebugProcess2::GetDesiredNGENCompilerFlags
Ottiene le impostazioni correnti del flag del compilatore utilizzate dal Common Language Runtime (CLR) per selezionare l'immagine precompilata (ovvero nativa) corretta da caricare in questo processo.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetDesiredNGENCompilerFlags (  
    [out] DWORD   *pdwFlags  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pdwFlags`  
 out Puntatore a una combinazione bit per bit dei valori di enumerazione [CorDebugJITCompilerFlags](cordebugjitcompilerflags-enumeration.md) usati per selezionare l'immagine precompilata corretta da caricare.  
  
## <a name="remarks"></a>Note  
 Utilizzare il metodo [ICorDebugProcess2:: SetDesiredNGENCompilerFlags](icordebugprocess2-setdesiredngencompilerflags-method.md) per impostare i flag che CLR utilizzerà per selezionare l'immagine precompilata corretta da caricare.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
