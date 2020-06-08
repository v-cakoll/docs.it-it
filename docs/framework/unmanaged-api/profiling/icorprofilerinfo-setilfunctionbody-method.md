---
title: Metodo ICorProfilerInfo::SetILFunctionBody
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.SetILFunctionBody
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::SetILFunctionBody
helpviewer_keywords:
- ICorProfilerInfo::SetILFunctionBody method [.NET Framework profiling]
- SetILFunctionBody method [.NET Framework profiling]
ms.assetid: b159c712-00f4-4fc7-a990-40bf9f642e8f
topic_type:
- apiref
ms.openlocfilehash: 462fc7222243f8cad4e1d03d1717eedace549836
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502938"
---
# <a name="icorprofilerinfosetilfunctionbody-method"></a>Metodo ICorProfilerInfo::SetILFunctionBody
Sostituisce il corpo della funzione specificata nel modulo specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT SetILFunctionBody(  
    [in] ModuleID    moduleId,  
    [in] mdMethodDef methodid,  
    [in] LPCBYTE     pbNewILMethodHeader);  
```  
  
## <a name="parameters"></a>Parametri  
 `moduleId`  
 in ID del modulo in cui risiede la funzione.  
  
 `methodid`  
 in Token della funzione per cui sostituire il corpo.  
  
 `pbNewILMethodHeader`  
 in Nuova intestazione per la funzione.  
  
## <a name="remarks"></a>Osservazioni  
 Il `SetILFunctionBody` metodo sostituisce l'indirizzo virtuale relativo della funzione nei metadati in modo che punti al nuovo corpo della funzione e modifichi tutte le strutture di dati interne in base alle esigenze.  
  
 Il `SetILFunctionBody` metodo può essere chiamato solo sulle funzioni che non sono mai state compilate da un compilatore JIT (just-in-Time).  
  
 Usare il metodo [ICorProfilerInfo:: GetILFunctionBodyAllocator](icorprofilerinfo-getilfunctionbodyallocator-method.md) per allocare spazio al nuovo metodo per assicurarsi che il buffer sia compatibile.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerInfo](icorprofilerinfo-interface.md)
