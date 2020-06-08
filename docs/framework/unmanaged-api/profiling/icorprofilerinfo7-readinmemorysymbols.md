---
title: 'ICorProfilerInfo7:: ReadInMemorySymbols'
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
ms.openlocfilehash: 6732457220d795bbf8ae54277ef9f5c07cf96359
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84495359"
---
# <a name="icorprofilerinfo7readinmemorysymbols"></a>ICorProfilerInfo7:: ReadInMemorySymbols
[Supportata in .NET Framework 4.6.1 e versioni successive]  
  
 Legge i byte da un flusso di simboli in memoria.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
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
 in Identificatore del modulo contenente il flusso in memoria.  
  
 `symbolsReadOffset`  
 in Offset all'interno del flusso in memoria da cui iniziare la lettura dei byte.  
  
 `pSymbolBytes`  
 out Puntatore al buffer in cui verranno copiati i dati. Lo spazio del buffer deve essere `countSymbolBytes` disponibile.  
  
 `countSymbolBytes`  
 in Numero di byte da copiare.  
  
 `pCountSymbolBytesRead`  
 out Quando il metodo viene restituito, contiene il numero effettivo di byte letti.  
  
## <a name="return-value"></a>Valore restituito  
 `S_OK`Se è stato letto un numero di byte diverso da zero.  
  
 `CORPROF_E_MODULE_IS_DYNAMIC`Se il modulo è stato creato usando <xref:System.Reflection.Emit> .  
  
## <a name="remarks"></a>Osservazioni  
 Il `ReadInMemorySymbols` metodo tenta di leggere i `countSymbolBytes` dati a partire dall'offset `symbolsReadOffset` all'interno del flusso in memoria. I dati vengono copiati in `pSymbolBytes` , che dovrebbe avere `countSymbolBytes` spazio disponibile.     `pCountSymbolsBytesRead`contiene il numero effettivo di byte letti, che può essere minore di `countSymbolBytes` se viene raggiunta la fine del flusso.  
  
> [!NOTE]
> L'implementazione corrente non supporta Reflection. Emit. Se il modulo è stato creato usando Reflection. Emit, il metodo restituisce `CORPROF_E_MODULE_IS_DYNAMIC` .  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerInfo7](icorprofilerinfo7-interface.md)
