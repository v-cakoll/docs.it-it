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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 895c8bc7b550fd063a9215c60f10f183e24bac83
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugassembly2isfullytrusted-method"></a>Metodo ICorDebugAssembly2::IsFullyTrusted
Ottiene un valore che indica se l'assembly è stata concessa l'attendibilità totale per il sistema di sicurezza di runtime.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT IsFullyTrusted(  
    [out] BOOL *pbFullyTrusted  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `pbFullyTrusted`  
 [out] `true` se l'assembly è stata concessa l'attendibilità totale per il sistema di sicurezza runtime; in caso contrario, `false`.  
  
## <a name="remarks"></a>Note  
 Questo metodo restituisce un valore HRESULT di CORDBG_E_NOTREADY se i criteri di sicurezza per l'assembly non sono ancora stato risolto, vale a dire, se nessun codice nell'assembly è stato ancora eseguito.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cordebug. idl, Cordebug. H  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
