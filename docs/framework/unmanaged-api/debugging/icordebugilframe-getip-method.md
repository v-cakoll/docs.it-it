---
title: Metodo ICorDebugILFrame::GetIP
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.GetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::GetIP
helpviewer_keywords:
- GetIP method, ICorDebugILFrame interface [.NET Framework debugging]
- ICorDebugILFrame::GetIP method [.NET Framework debugging]
ms.assetid: 18217ba1-1776-4297-a3b9-f77e64b0fead
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4d7eca3c2825707c9190436377bba7e4bb0d5447
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67757968"
---
# <a name="icordebugilframegetip-method"></a>Metodo ICorDebugILFrame::GetIP
Ottiene il valore del puntatore dell'istruzione e un valore di combinazione bit per bit che descrive come è stato ottenuto il valore del puntatore dell'istruzione.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetIP (  
    [out] ULONG32               *pnOffset,   
    [out] CorDebugMappingResult *pMappingResult  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pnOffset`  
 [out] Il valore del puntatore dell'istruzione.  
  
 `pMappingResult`  
 [out] Un puntatore a una combinazione bit per bit dei valori di enumerazione CorDebugMappingResult indicanti il modo in cui è stato ottenuto il valore del puntatore dell'istruzione.  
  
## <a name="remarks"></a>Note  
 Il valore del puntatore dell'istruzione è l'offset del frame dello stack nel codice della funzione Microsoft intermediate language (MSIL). Se lo stack frame è attivo, questo indirizzo è l'istruzione successiva da eseguire. Se lo stack frame non è attivo, questo indirizzo è l'istruzione successiva da eseguire quando viene riattivato lo stack frame.  
  
 Se il frame è un frame compilato tramite just-in-time (JIT), il valore del puntatore dell'istruzione verrà determinato eseguendo il mapping con le versioni precedenti dal puntatore alle istruzioni native effettivo, pertanto il valore può essere solo approssimativo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
