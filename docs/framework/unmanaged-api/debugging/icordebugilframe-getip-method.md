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
ms.openlocfilehash: f30516a8f59b90de9b4c052d92a8c88575ace3c4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178830"
---
# <a name="icordebugilframegetip-method"></a>Metodo ICorDebugILFrame::GetIP
Ottiene il valore del puntatore all'istruzione e un valore di combinazione bit per bit che descrive come è stato ottenuto il valore del puntatore all'istruzione.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetIP (  
    [out] ULONG32               *pnOffset,
    [out] CorDebugMappingResult *pMappingResult  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pnOffset`  
 [fuori] Valore del puntatore all'istruzione.  
  
 `pMappingResult`  
 [fuori] Puntatore a una combinazione bit per bit dei valori di enumerazione CorDebugMappingResult che descrivono come è stato ottenuto il valore del puntatore all'istruzione.  
  
## <a name="remarks"></a>Osservazioni  
 Il valore del puntatore all'istruzione è l'offset dello stack frame nel codice MSIL (Microsoft Intermediate Language) della funzione. Se lo stack frame è attivo, questo indirizzo è l'istruzione successiva da eseguire. Se lo stack frame non è attivo, questo indirizzo è l'istruzione successiva da eseguire quando lo stack frame viene riattivato.  
  
 Se questo frame è un frame compilato JIT (Just-In-Time), il valore del puntatore all'istruzione verrà determinato eseguendo il mapping all'indietro dal puntatore all'istruzione nativo effettivo, pertanto il valore può essere solo approssimativo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
