---
title: Metodo ICorDebugProcess::ReadMemory
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.ReadMemory
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::ReadMemory
helpviewer_keywords:
- ReadMemory method [.NET Framework debugging]
- ICorDebugProcess::ReadMemory method [.NET Framework debugging]
ms.assetid: 28e4b2f6-9589-445c-be24-24a3306795e7
topic_type:
- apiref
ms.openlocfilehash: ccd2350589126109ff11da439a8b83abfc4b91fa
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210475"
---
# <a name="icordebugprocessreadmemory-method"></a>Metodo ICorDebugProcess::ReadMemory
Legge un'area di memoria specificata per questo processo.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT ReadMemory(  
    [in]  CORDB_ADDRESS address,
    [in]  DWORD size,  
    [out, size_is(size), length_is(size)] BYTE buffer[],  
    [out] SIZE_T *read);  
```  
  
## <a name="parameters"></a>Parametri  
 `address`  
 in `CORDB_ADDRESS`Valore che specifica l'indirizzo di base della memoria da leggere.  
  
 `size`  
 in Numero di byte da leggere dalla memoria.  
  
 `buffer`  
 out Buffer che riceve il contenuto della memoria.  
  
 `read`  
 out Puntatore al numero di byte trasferiti nel buffer specificato.  
  
## <a name="remarks"></a>Osservazioni  
 Il `ReadMemory` metodo è destinato principalmente a essere utilizzato dal debug di interoperabilità per esaminare le aree di memoria utilizzate dalla parte non gestita dell'oggetto del debug. Questo metodo può essere utilizzato anche per leggere codice MSIL (Microsoft Intermediate Language) e codice nativo compilato tramite JIT.  
  
 Eventuali punti di interruzione gestiti verranno rimossi dai dati restituiti nel `buffer` parametro. Non verranno apportate modifiche per i punti di interruzione nativi impostati da [ICorDebugProcess2:: SetUnmanagedBreakpoint](icordebugprocess2-setunmanagedbreakpoint-method.md).  
  
 Non viene eseguita la memorizzazione nella cache della memoria del processo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
