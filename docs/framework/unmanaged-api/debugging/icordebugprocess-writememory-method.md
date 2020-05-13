---
title: Metodo ICorDebugProcess::WriteMemory
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.WriteMemory
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::WriteMemory
helpviewer_keywords:
- ICorDebugProcess::WriteMemory method [.NET Framework debugging]
- WriteMemory method [.NET Framework debugging]
ms.assetid: d5c07d86-045d-4391-893b-0bcd2959f90e
topic_type:
- apiref
ms.openlocfilehash: 0a433ccb81ef62ac92a4553a838a2c98a04fc7c1
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212815"
---
# <a name="icordebugprocesswritememory-method"></a>Metodo ICorDebugProcess::WriteMemory
Scrive i dati in un'area di memoria in questo processo.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT WriteMemory(  
    [in]  CORDB_ADDRESS address,  
    [in]  DWORD size,  
    [in, size_is(size)] BYTE buffer[],  
    [out] SIZE_T *written);  
```  
  
## <a name="parameters"></a>Parametri  
 `address`  
 in `CORDB_ADDRESS`Valore che rappresenta l'indirizzo di base dell'area di memoria in cui vengono scritti i dati. Prima che si verifichi il trasferimento dei dati, il sistema verifica che l'area di memoria della dimensione specificata, a partire dall'indirizzo di base, sia accessibile per la scrittura. Se non è accessibile, il metodo ha esito negativo.  
  
 `size`  
 in Numero di byte da scrivere nell'area di memoria.  
  
 `buffer`  
 in Buffer contenente i dati da scrivere.  
  
 `written`  
 out Puntatore a una variabile che riceve il numero di byte scritti nell'area di memoria del processo. Se `written` è null, questo parametro viene ignorato.  
  
## <a name="remarks"></a>Osservazioni  
 I dati vengono scritti automaticamente dietro i punti di interruzione. In .NET Framework versione 2,0 i debugger nativi non devono usare questo metodo per inserire i punti di interruzione nel flusso di istruzioni. Usare invece [ICorDebugProcess2:: SetUnmanagedBreakpoint](icordebugprocess2-setunmanagedbreakpoint-method.md) .  
  
 Il `WriteMemory` metodo deve essere utilizzato solo all'esterno del codice gestito. Questo metodo può danneggiare il runtime se usato in modo errato.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
