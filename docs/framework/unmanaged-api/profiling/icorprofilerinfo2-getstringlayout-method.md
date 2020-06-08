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
ms.openlocfilehash: 257cf24fa476c75d6ec949e17a5b83fc015b8d43
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84496789"
---
# <a name="icorprofilerinfo2getstringlayout-method"></a>Metodo ICorProfilerInfo2::GetStringLayout
Ottiene informazioni sul layout di un oggetto stringa. Questo metodo è deprecato nel .NET Framework 4 e viene sostituito dal metodo [ICorProfilerInfo3:: GetStringLayout2](icorprofilerinfo3-getstringlayout2-method.md) .  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetStringLayout(  
    [out] ULONG *pBufferLengthOffset,  
    [out] ULONG *pStringLengthOffset,  
    [out] ULONG *pBufferOffset);  
```  
  
## <a name="parameters"></a>Parametri  
 `pBufferLengthOffset`  
 out Puntatore all'offset della posizione, relativo al `ObjectID` puntatore, che archivia la lunghezza della stringa. La lunghezza viene archiviata come `DWORD` .  
  
> [!NOTE]
> Questo parametro restituisce la lunghezza della stringa stessa, non la lunghezza del buffer. La lunghezza del buffer non è più disponibile.  
  
 `PStringLengthOffset`  
 out Puntatore all'offset della posizione, relativo al `ObjectID` puntatore, che archivia la lunghezza della stringa stessa. La lunghezza viene archiviata come `DWORD` .  
  
 `pBufferOffset`  
 out Puntatore all'offset del buffer, relativo al `ObjectID` puntatore, che archivia la stringa di caratteri wide.  
  
## <a name="remarks"></a>Osservazioni  
 Il `GetStringLayout` metodo ottiene gli offset, relativi al `ObjectID` puntatore, dei percorsi in cui sono archiviati gli elementi seguenti:  
  
- Lunghezza del buffer della stringa.  
  
- Lunghezza della stringa stessa.  
  
- Buffer contenente la stringa effettiva di caratteri wide.  
  
 Le stringhe possono essere con terminazione null.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerInfo](icorprofilerinfo-interface.md)
- [Interfaccia ICorProfilerInfo2](icorprofilerinfo2-interface.md)
