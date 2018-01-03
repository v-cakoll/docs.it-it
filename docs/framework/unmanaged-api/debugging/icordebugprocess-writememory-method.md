---
title: Metodo ICorDebugProcess::WriteMemory
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess.WriteMemory
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess::WriteMemory
helpviewer_keywords:
- ICorDebugProcess::WriteMemory method [.NET Framework debugging]
- WriteMemory method [.NET Framework debugging]
ms.assetid: d5c07d86-045d-4391-893b-0bcd2959f90e
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2a1a12d1393d1db69ea47833958fdf828b552064
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocesswritememory-method"></a>Metodo ICorDebugProcess::WriteMemory
Scrive dati in un'area di memoria nel processo.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT WriteMemory(  
    [in]  CORDB_ADDRESS address,  
    [in]  DWORD size,  
    [in, size_is(size)] BYTE buffer[],  
    [out] SIZE_T *written);  
```  
  
#### <a name="parameters"></a>Parametri  
 `address`  
 [in] Oggetto `CORDB_ADDRESS` valore corrispondente all'indirizzo di base dell'area di memoria per i dati viene scritto. Prima che si verifichi il trasferimento dei dati, il sistema verifica che l'area di memoria della dimensione specificata, a partire dall'indirizzo di base, sia accessibile in scrittura. Se non è accessibile, il metodo ha esito negativo.  
  
 `size`  
 [in] Il numero di byte da scrivere nell'area di memoria.  
  
 `buffer`  
 [in] Un buffer contenente dati da scrivere.  
  
 `written`  
 [out] Un puntatore a una variabile che riceve il numero di byte scritti nell'area di memoria nel processo. Se `written` è NULL, questo parametro viene ignorato.  
  
## <a name="remarks"></a>Note  
 Dati vengono scritti automaticamente dietro i punti di interruzione. In .NET Framework versione 2.0, il debugger nativo non deve utilizzare questo metodo per inserire punti di interruzione nel flusso di istruzioni. Utilizzare [ICorDebugProcess2::](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md) invece.  
  
 Il `WriteMemory` metodo deve essere utilizzato solo all'esterno di codice gestito. Questo metodo può danneggiare il runtime, se utilizzato in modo non corretto.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
