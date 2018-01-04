---
title: 'Icorprofilerinfo7:: Readinmemorysymbols'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
api_name: ICorProfilerInfo7.ReadInMemorySymbols
api_location:
- CorProf.idl
- CorProf.h
- CorGuids.lib
api_type: COM
ms.assetid: 1745a0b9-8332-4777-a670-b549bff3b901
caps.latest.revision: "3"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5851f73cc899ef21d8a5dcfd8f03617641a6625a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo7readinmemorysymbols"></a>Icorprofilerinfo7:: Readinmemorysymbols
[Supportato in [!INCLUDE[net_v461](../../../../includes/net-v461-md.md)] e versioni successive]  
  
 Legge i byte dal flusso simbolo in memoria.  
  
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
  
#### <a name="parameters"></a>Parametri  
 `moduleId`  
 [in] L'identificatore del modulo contenente il flusso in memoria.  
  
 `symbolsReadOffset`  
 [in] L'offset all'interno del flusso in memoria in corrispondenza del quale iniziare la lettura dei byte.  
  
 `pSymbolBytes`  
 [out] Un puntatore al buffer in cui verranno copiati i dati. Il buffer deve essere `countSymbolBytes` di spazio disponibile.  
  
 `countSymbolBytes`  
 [in] Il numero di byte da copiare.  
  
 `pCountSymbolBytesRead`  
 [out] Quando il metodo viene restituito, contiene il numero effettivo di byte letti.  
  
## <a name="return-value"></a>Valore restituito  
 `S_OK`, se un numero diverso da zero di byte letti.  
  
 `CORPROF_E_MODULE_IS_DYNAMIC`, se il modulo è stato creato utilizzando <xref:System.Reflection.Emit>.  
  
## <a name="remarks"></a>Note  
 Il `ReadInMemorySymbols` metodo tenta di leggere `countSymbolBytes` dei dati a partire dall'offset `symbolsReadOffset` all'interno del flusso in memoria. I dati vengono copiati in `pSymbolBytes`, che dovranno avere `countSymbolBytes` di spazio disponibile.     `pCountSymbolsBytesRead`contiene il numero effettivo di byte letti, che può essere inferiore rispetto a `countSymbolBytes` se viene raggiunta la fine del flusso.  
  
> [!NOTE]
>  L'implementazione corrente non supporta Reflection. Emit. Se il modulo è stato creato tramite Reflection. Emit, il metodo restituisce `CORPROF_E_MODULE_IS_DYNAMIC`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorProfilerInfo7](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)
