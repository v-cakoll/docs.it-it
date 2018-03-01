---
title: Metodo ICorDebugILFrame::GetIP
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 79b18c6fe15e28b2cec07ef9dfaa06ee295ab42d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugilframegetip-method"></a>Metodo ICorDebugILFrame::GetIP
Ottiene il valore del puntatore all'istruzione e un valore di combinazione bit per bit che descrive la modalità in cui è stato ottenuto il valore del puntatore all'istruzione.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetIP (  
    [out] ULONG32               *pnOffset,   
    [out] CorDebugMappingResult *pMappingResult  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `pnOffset`  
 [out] Il valore del puntatore all'istruzione.  
  
 `pMappingResult`  
 [out] Un puntatore a una combinazione bit per bit dei valori di enumerazione CorDebugMappingResult che descrivono la modalità in cui è stato ottenuto il valore del puntatore all'istruzione.  
  
## <a name="remarks"></a>Note  
 Il valore del puntatore all'istruzione è l'offset del frame dello stack nel codice della funzione Microsoft intermediate language (MSIL). Se lo stack frame è attivo, questo indirizzo è l'istruzione successiva da eseguire. Se lo stack frame non è attivo, questo indirizzo è l'istruzione successiva da eseguire quando viene riattivato lo stack frame.  
  
 Se il frame è un frame compilato di just-in-time (JIT), il valore del puntatore all'istruzione verrà determinato eseguendo il mapping con le versioni precedenti dal puntatore all'istruzione nativo effettivo, pertanto il valore può essere solo approssimativo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
