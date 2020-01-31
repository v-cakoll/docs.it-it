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
ms.openlocfilehash: 537840ac03b4136682b78cb964950ab5670a7d7e
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868616"
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
 out Puntatore all'offset della posizione, relativo al puntatore `ObjectID`, che archivia la lunghezza della stringa. La lunghezza viene archiviata come `DWORD`.  
  
> [!NOTE]
> Questo parametro restituisce la lunghezza della stringa stessa, non la lunghezza del buffer. La lunghezza del buffer non è più disponibile.  
  
 `PStringLengthOffset`  
 out Puntatore all'offset della posizione, relativo al puntatore `ObjectID`, in cui è archiviata la lunghezza della stringa stessa. La lunghezza viene archiviata come `DWORD`.  
  
 `pBufferOffset`  
 out Puntatore all'offset del buffer, relativo al puntatore `ObjectID`, che archivia la stringa di caratteri wide.  
  
## <a name="remarks"></a>Note  
 Il metodo `GetStringLayout` ottiene gli offset, relativi al puntatore `ObjectID`, delle posizioni in cui sono archiviati gli elementi seguenti:  
  
- Lunghezza del buffer della stringa.  
  
- Lunghezza della stringa stessa.  
  
- Buffer contenente la stringa effettiva di caratteri wide.  
  
 Le stringhe possono essere con terminazione null.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerInfo](icorprofilerinfo-interface.md)
- [Interfaccia ICorProfilerInfo2](icorprofilerinfo2-interface.md)
