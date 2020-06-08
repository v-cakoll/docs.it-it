---
title: Metodo ICorProfilerInfo::GetObjectSize
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetObjectSize
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetObjectSize
helpviewer_keywords:
- GetObjectSize method [.NET Framework profiling]
- ICorProfilerInfo::GetObjectSize method [.NET Framework profiling]
ms.assetid: 9f02e763-73f7-42cb-a41c-f78499d9482c
topic_type:
- apiref
ms.openlocfilehash: 15c843fe138be55a3480f46e0ef8b37bcb445ad0
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84497972"
---
# <a name="icorprofilerinfogetobjectsize-method"></a>Metodo ICorProfilerInfo::GetObjectSize
Ottiene le dimensioni di un oggetto specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetObjectSize(  
    [in]  ObjectID objectId,  
    [out] ULONG  *pcSize);  
```  
  
## <a name="parameters"></a>Parametri  
 `objectId`  
 in ID dell'oggetto.  
  
 `pcSize`  
 out Puntatore alla dimensione dell'oggetto, in byte.  
  
## <a name="remarks"></a>Osservazioni  
  
> [!IMPORTANT]
> Questo metodo è obsoleto. Restituisce COR_E_OVERFLOW per oggetti maggiori di 4 GB sulle piattaforme a 64 bit. Usare invece il metodo [ICorProfilerInfo4:: GetObjectSize2](icorprofilerinfo4-getobjectsize2-method.md) .  
  
 Oggetti diversi degli stessi tipi spesso hanno le stesse dimensioni. Tuttavia, alcuni tipi, ad esempio matrici o stringhe, possono avere dimensioni diverse per ogni oggetto.  
  
 Le dimensioni restituite dal `GetObjectSize` metodo non includono la spaziatura interna dell'allineamento che può comparire dopo che l'oggetto si trova nell'heap del Garbage Collection. Se si usa il `GetObjectSize` metodo per passare da oggetto a oggetto nell'heap del Garbage Collection, aggiungere la spaziatura interna dell'allineamento manualmente, se necessario.  
  
- Nelle finestre a 32 bit COR_PRF_GC_GEN_0, COR_PRF_GC_GEN_1 e COR_PRF_GC_GEN_2 usare l'allineamento a 4 byte e COR_PRF_GC_LARGE_OBJECT_HEAP usa l'allineamento a 8 byte.  
  
- In Windows a 64 bit, l'allineamento è sempre di 8 byte.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerInfo](icorprofilerinfo-interface.md)
