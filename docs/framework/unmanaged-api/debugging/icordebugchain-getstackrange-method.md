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
ms.openlocfilehash: 226f8c431b90d53366aa5e504101e7de581ec570
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33402470"
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
  
#### <a name="parameters"></a>Parametri  
 `pStart`  
 [out] Un puntatore a un `CORDB_ADDRESS` valore che corrisponde all'indirizzo iniziale del segmento di stack.  
  
 `pEnd`  
 [out] Un puntatore a un `CORDB_ADDRESS` valore che corrisponde all'indirizzo finale del segmento di stack.  
  
## <a name="remarks"></a>Note  
 L'intervallo numerico è significativo solo per il confronto di percorsi dello stack frame. È possibile apportare ipotesi in merito a ciò che effettivamente è memorizzato nello stack.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cordebug. idl, Cordebug. H  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
