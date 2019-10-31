---
title: Metodo ICorDebugAssembly2::IsFullyTrusted
ms.date: 03/30/2017
api_name:
- ICorDebugAssembly2.IsFullyTrusted
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssembly2::IsFullyTrusted
helpviewer_keywords:
- ICorDebugAssembly2::IsFullyTrusted method [.NET Framework debugging]
- IsFullyTrusted method [.NET Framework debugging]
ms.assetid: 26cbd27d-12bf-444a-8197-ccd14d37dda3
topic_type:
- apiref
ms.openlocfilehash: bef51fe9df0f85659603c637f11ed4e856c8e01a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133958"
---
# <a name="icordebugassembly2isfullytrusted-method"></a>Metodo ICorDebugAssembly2::IsFullyTrusted
Ottiene un valore che indica se all'assembly è stata concessa l'attendibilità totale dal sistema di sicurezza del runtime.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT IsFullyTrusted(  
    [out] BOOL *pbFullyTrusted  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pbFullyTrusted`  
 [out] `true` se all'assembly è stata concessa l'attendibilità totale dal sistema di sicurezza di runtime; in caso contrario, `false`.  
  
## <a name="remarks"></a>Note  
 Questo metodo restituisce un valore HRESULT di CORDBG_E_NOTREADY se i criteri di sicurezza per l'assembly non sono stati ancora risolti, ovvero se non è stato ancora eseguito alcun codice nell'assembly.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
