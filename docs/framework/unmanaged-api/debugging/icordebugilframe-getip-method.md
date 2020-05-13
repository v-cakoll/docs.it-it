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
ms.openlocfilehash: 3890cb4236f113bc6efc23bfb606d19a525ec234
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210267"
---
# <a name="icordebugilframegetip-method"></a>Metodo ICorDebugILFrame::GetIP
Ottiene il valore del puntatore all'istruzione e un valore di combinazione bit per bit che descrive il modo in cui è stato ottenuto il valore del puntatore all'istruzione.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetIP (  
    [out] ULONG32               *pnOffset,
    [out] CorDebugMappingResult *pMappingResult  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pnOffset`  
 out Valore del puntatore all'istruzione.  
  
 `pMappingResult`  
 out Puntatore a una combinazione bit per bit dei valori di Enumerazione CorDebugMappingResult che descrivono come è stato ottenuto il valore del puntatore all'istruzione.  
  
## <a name="remarks"></a>Osservazioni  
 Il valore del puntatore all'istruzione è l'offset del stack frame nel codice MSIL (Microsoft Intermediate Language) della funzione. Se la stack frame è attiva, questo indirizzo è l'istruzione successiva da eseguire. Se il stack frame non è attivo, questo indirizzo è l'istruzione successiva da eseguire quando viene riattivata la stack frame.  
  
 Se questo frame è un frame compilato JIT (just-in-Time), il valore del puntatore all'istruzione verrà determinato eseguendo il mapping all'indietro rispetto al puntatore di istruzione nativo effettivo, quindi il valore può essere solo approssimativo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
