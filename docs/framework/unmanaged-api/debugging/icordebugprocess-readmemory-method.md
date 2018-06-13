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
ms.openlocfilehash: a0063e33a6a7861815ebb9d9eb3dabec64dd4b9d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33419653"
---
# <a name="icordebugprocessreadmemory-method"></a>Metodo ICorDebugProcess::ReadMemory
Legge un'area specificata di memoria per questo processo.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT ReadMemory(  
    [in]  CORDB_ADDRESS address,   
    [in]  DWORD size,  
    [out, size_is(size), length_is(size)] BYTE buffer[],  
    [out] SIZE_T *read);  
```  
  
#### <a name="parameters"></a>Parametri  
 `address`  
 [in] Oggetto `CORDB_ADDRESS` valore che specifica l'indirizzo di base della memoria da leggere.  
  
 `size`  
 [in] Il numero di byte da leggere dalla memoria.  
  
 `buffer`  
 [out] Un buffer che riceve il contenuto della memoria.  
  
 `read`  
 [out] Un puntatore al numero di byte trasferiti nel buffer specificato.  
  
## <a name="remarks"></a>Note  
 Il `ReadMemory` metodo viene usata principalmente per essere utilizzato per il debug di interoperabilità per controllare le aree della memoria in uso da parte dell'oggetto del debug non gestita. Questo metodo può anche essere utilizzato per leggere codice Microsoft intermediate language (MSIL) e codice nativo compilato tramite JIT.  
  
 I punti di interruzione gestiti verrà rimossa dal disco i dati restituiti nel `buffer` parametro. Verrà eseguita alcuna modifica per i punti di interruzione nativi impostato dal [ICorDebugProcess2::](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md).  
  
 Non viene eseguita nessuna memorizzazione nella cache della memoria del processo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cordebug. idl, Cordebug. H  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
