---
title: Metodo ICorDebugChain::GetStackRange
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetStackRange
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetStackRange
helpviewer_keywords:
- ICorDebugChain::GetStackRange method [.NET Framework debugging]
- GetStackRange method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: 554284e7-3f6c-4d40-8da5-1c9317fbd484
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ac40927ac9469e4a2fb74fb550287130b9bb9f83
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57481560"
---
# <a name="icordebugchaingetstackrange-method"></a>Metodo ICorDebugChain::GetStackRange
Ottiene l'intervallo di indirizzi del segmento di stack per questa catena.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetStackRange (  
    [out] CORDB_ADDRESS      *pStart,   
    [out] CORDB_ADDRESS      *pEnd  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pStart`  
 [out] Un puntatore a un `CORDB_ADDRESS` valore, ovvero l'indirizzo iniziale del segmento dello stack.  
  
 `pEnd`  
 [out] Un puntatore a un `CORDB_ADDRESS` valore che corrisponde all'indirizzo finale del segmento dello stack.  
  
## <a name="remarks"></a>Note  
 L'intervallo numerico è significativa solo per il confronto dei percorsi dello stack frame. È possibile fare supposizioni su ciò che effettivamente è memorizzato nello stack.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
