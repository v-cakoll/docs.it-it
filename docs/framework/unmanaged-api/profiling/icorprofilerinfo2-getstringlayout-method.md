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
ms.openlocfilehash: cc94c63edb602d87a7c08a9051eb2ef760834477
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59200974"
---
# <a name="icorprofilerinfo2getstringlayout-method"></a>Metodo ICorProfilerInfo2::GetStringLayout
Ottiene informazioni sul layout di un oggetto stringa. Questo metodo è deprecato nel [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]ed è stato sostituito il [ICorProfilerInfo3::GetStringLayout2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getstringlayout2-method.md) (metodo).  
  
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
  
-   Lunghezza del buffer della stringa.  
  
-   La lunghezza della stringa stessa.  
  
-   Buffer che contiene la stringa effettiva di caratteri "wide".  
  
 Le stringhe possono essere con terminazione null.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [Interfaccia ICorProfilerInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
