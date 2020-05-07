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
ms.openlocfilehash: 40ecc183c32500ad9e88ceb1bfc0528d717430e8
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894460"
---
# <a name="icordebugchaingetstackrange-method"></a>Metodo ICorDebugChain::GetStackRange
Ottiene l'intervallo di indirizzi del segmento dello stack per questa catena.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetStackRange (  
    [out] CORDB_ADDRESS      *pStart,
    [out] CORDB_ADDRESS      *pEnd  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pStart`  
 out Puntatore a un `CORDB_ADDRESS` valore che rappresenta l'indirizzo iniziale del segmento dello stack.  
  
 `pEnd`  
 out Puntatore a un `CORDB_ADDRESS` valore che rappresenta l'indirizzo finale del segmento dello stack.  
  
## <a name="remarks"></a>Osservazioni  
 L'intervallo numerico è significativo solo per il confronto dei percorsi di stack frame. Non è possibile creare presupposti sugli elementi effettivamente archiviati nello stack.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
