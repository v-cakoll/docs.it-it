---
title: Metodo ICorProfilerInfo2::GetStringLayout
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetStringLayout
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetStringLayout
helpviewer_keywords:
- GetStringLayout method [.NET Framework profiling]
- ICorProfilerInfo2::GetStringLayout method [.NET Framework profiling]
ms.assetid: 43189651-a535-4803-a1d1-f1c427ace2ca
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: faa5ecf63ac3795a58369d94f9fb15f853edb576
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490707"
---
# <a name="icorprofilerinfo2getstringlayout-method"></a>Metodo ICorProfilerInfo2::GetStringLayout
Ottiene informazioni sul layout di un oggetto stringa. Questo metodo è deprecato in .NET Framework 4 ed è stato sostituito il [ICorProfilerInfo3::GetStringLayout2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getstringlayout2-method.md) (metodo).  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetStringLayout(  
    [out] ULONG *pBufferLengthOffset,  
    [out] ULONG *pStringLengthOffset,  
    [out] ULONG *pBufferOffset);  
```  
  
## <a name="parameters"></a>Parametri  
 `pBufferLengthOffset`  
 [out] Un puntatore all'offset della posizione relativa per il `ObjectID` puntatore, che archivia la lunghezza della stringa. La lunghezza viene archiviata come un `DWORD`.  
  
> [!NOTE]
>  Questo parametro restituisce la lunghezza della stringa, non la lunghezza del buffer. La lunghezza del buffer non è più disponibile.  
  
 `PStringLengthOffset`  
 [out] Un puntatore all'offset della posizione relativa per il `ObjectID` puntatore, che archivia la lunghezza della stringa stessa. La lunghezza viene archiviata come un `DWORD`.  
  
 `pBufferOffset`  
 [out] L'offset del buffer relativo a un puntatore di `ObjectID` puntatore, che archivia la stringa di caratteri "wide".  
  
## <a name="remarks"></a>Note  
 Il `GetStringLayout` metodo ottiene gli offset rispetto al `ObjectID` puntatore, delle posizioni in cui sono archiviati i seguenti:  
  
- Lunghezza del buffer della stringa.  
  
- La lunghezza della stringa stessa.  
  
- Buffer che contiene la stringa effettiva di caratteri "wide".  
  
 Le stringhe possono essere con terminazione null.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [Interfaccia ICorProfilerInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
