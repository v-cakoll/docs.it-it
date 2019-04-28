---
title: ICorProfilerInfo7::ReadInMemorySymbols
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo7.ReadInMemorySymbols
api_location:
- CorProf.idl
- CorProf.h
- CorGuids.lib
api_type:
- COM
ms.assetid: 1745a0b9-8332-4777-a670-b549bff3b901
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 662863ec69e464dafe893552f1d81755313acc75
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61786209"
---
# <a name="icorprofilerinfo7readinmemorysymbols"></a>ICorProfilerInfo7::ReadInMemorySymbols
[Supportato in [!INCLUDE[net_v461](../../../../includes/net-v461-md.md)] e versioni successive]  
  
 Legge i byte da un flusso di simboli in memoria.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT ReadInMemorySymbols(  
        [in] ModuleID moduleId,  
        [in] DWORD symbolsReadOffset,  
        [out] BYTE* pSymbolBytes,  
        [in] DWORD countSymbolBytes,  
        [out] DWORD* pCountSymbolBytesRead  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `moduleId`  
 [in] L'identificatore del modulo contenente il flusso in memoria.  
  
 `symbolsReadOffset`  
 [in] L'offset all'interno del flusso in memoria in corrispondenza del quale iniziare la lettura dei byte.  
  
 `pSymbolBytes`  
 [out] Un puntatore al buffer in cui verranno copiati i dati. Il buffer deve avere `countSymbolBytes` di spazio disponibile.  
  
 `countSymbolBytes`  
 [in] Il numero di byte da copiare.  
  
 `pCountSymbolBytesRead`  
 [out] Quando il metodo viene restituito, contiene il numero effettivo di byte letti.  
  
## <a name="return-value"></a>Valore restituito  
 `S_OK`, se un numero diverso da zero di byte letti.  
  
 `CORPROF_E_MODULE_IS_DYNAMIC`, se il modulo è stato creato usando <xref:System.Reflection.Emit>.  
  
## <a name="remarks"></a>Note  
 Il `ReadInMemorySymbols` metodo tenta di leggere `countSymbolBytes` dei dati a partire dall'offset `symbolsReadOffset` all'interno del flusso in memoria. I dati vengono copiati `pSymbolBytes`, che deve disporre di `countSymbolBytes` dello spazio disponibile.     `pCountSymbolsBytesRead` contiene il numero effettivo di byte letti, che può essere inferiore rispetto a `countSymbolBytes` se viene raggiunta la fine del flusso.  
  
> [!NOTE]
>  L'implementazione corrente non supporta Reflection. Emit. Se il modulo è stato creato tramite Reflection. Emit, il metodo restituisce `CORPROF_E_MODULE_IS_DYNAMIC`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerInfo7](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)
