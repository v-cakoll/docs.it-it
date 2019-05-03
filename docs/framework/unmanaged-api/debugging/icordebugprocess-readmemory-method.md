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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 218279684304b766a9bf009f5891ac4910254a3c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61994383"
---
# <a name="icordebugprocessreadmemory-method"></a>Metodo ICorDebugProcess::ReadMemory
Legge un'area specificata di memoria del processo.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT ReadMemory(  
    [in]  CORDB_ADDRESS address,   
    [in]  DWORD size,  
    [out, size_is(size), length_is(size)] BYTE buffer[],  
    [out] SIZE_T *read);  
```  
  
## <a name="parameters"></a>Parametri  
 `address`  
 [in] Oggetto `CORDB_ADDRESS` valore che specifica l'indirizzo di base della memoria da leggere.  
  
 `size`  
 [in] Il numero di byte da leggere dalla memoria.  
  
 `buffer`  
 [out] Un buffer che riceve il contenuto della memoria.  
  
 `read`  
 [out] Un puntatore al numero di byte trasferiti nel buffer specificato.  
  
## <a name="remarks"></a>Note  
 Il `ReadMemory` metodo è principalmente destinato a essere usato per il debug di interoperabilità per controllare le aree della memoria in uso da parte dell'oggetto del debug non gestita. Questo metodo può essere utilizzato anche leggere codice Microsoft intermediate language (MSIL) e codice nativo compilato tramite JIT.  
  
 Punti di interruzione gestite verrà rimossa dai dati che viene restituiti nel `buffer` parametro. Non verrà eseguita alcuna modifica per impostare punti di interruzione native [ICorDebugProcess2::SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md).  
  
 Nessuna memorizzazione nella cache della memoria del processo viene eseguito.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
