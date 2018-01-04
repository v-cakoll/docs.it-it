---
title: Metodo ICorProfilerInfo2::GetStringLayout
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo2.GetStringLayout
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo2::GetStringLayout
helpviewer_keywords:
- GetStringLayout method [.NET Framework profiling]
- ICorProfilerInfo2::GetStringLayout method [.NET Framework profiling]
ms.assetid: 43189651-a535-4803-a1d1-f1c427ace2ca
topic_type: apiref
caps.latest.revision: "17"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1ad91829fab31b47a1dd51bb6cc9118c2ebe4c3a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo2getstringlayout-method"></a>Metodo ICorProfilerInfo2::GetStringLayout
Ottiene informazioni sul layout di un oggetto stringa. Questo metodo è deprecato nel [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]ed è stato sostituito il [ICorProfilerInfo3:: Getstringlayout2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getstringlayout2-method.md) metodo.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetStringLayout(  
    [out] ULONG *pBufferLengthOffset,  
    [out] ULONG *pStringLengthOffset,  
    [out] ULONG *pBufferOffset);  
```  
  
#### <a name="parameters"></a>Parametri  
 `pBufferLengthOffset`  
 [out] Un puntatore all'offset della posizione relativa al `ObjectID` puntatore, che archivia la lunghezza della stringa. La lunghezza viene archiviata come un `DWORD`.  
  
> [!NOTE]
>  Questo parametro restituisce la lunghezza della stringa stessa, non la lunghezza del buffer. La lunghezza del buffer non è più disponibile.  
  
 `PStringLengthOffset`  
 [out] Un puntatore all'offset della posizione relativa al `ObjectID` puntatore, che archivia la lunghezza della stringa stessa. La lunghezza viene archiviata come un `DWORD`.  
  
 `pBufferOffset`  
 [out] Un puntatore all'offset del buffer relativo al `ObjectID` puntatore, che archivia la stringa di caratteri wide.  
  
## <a name="remarks"></a>Note  
 Il `GetStringLayout` metodo ottiene gli offset, relativo al `ObjectID` puntatore, delle posizioni in cui sono archiviate le operazioni seguenti:  
  
-   La lunghezza del buffer della stringa.  
  
-   La lunghezza della stringa stessa.  
  
-   Buffer che contiene la stringa effettiva di caratteri wide.  
  
 Le stringhe possono essere con terminazione null.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [Interfaccia ICorProfilerInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
