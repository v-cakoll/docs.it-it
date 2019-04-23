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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d366a0093ca82d2e5b3c40729777a1b6c0766bda
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59092201"
---
# <a name="icorprofilerinfogetobjectsize-method"></a>Metodo ICorProfilerInfo::GetObjectSize
Ottiene le dimensioni di un oggetto specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetObjectSize(  
    [in]  ObjectID objectId,  
    [out] ULONG  *pcSize);  
```  
  
## <a name="parameters"></a>Parametri  
 `objectId`  
 [in] L'ID dell'oggetto.  
  
 `pcSize`  
 [out] Puntatore alla dimensione dell'oggetto, in byte.  
  
## <a name="remarks"></a>Note  
  
> [!IMPORTANT]
>  Questo metodo è obsoleto. Restituisce COR_E_OVERFLOW per gli oggetti maggiori di 4GB su piattaforme a 64 bit. Usare la [ICorProfilerInfo4::GetObjectSize2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getobjectsize2-method.md) metodo invece.  
  
 Oggetti diversi dello stesso tipo sono spesso le stesse dimensioni. Tuttavia, alcuni tipi, ad esempio le matrici o stringhe, potrebbero essere una dimensione diversa per ogni oggetto.  
  
 Le dimensioni restituite dal `GetObjectSize` (metodo) non include eventuali spaziature interne di allineamento che possono essere visualizzati dopo che l'oggetto è nell'heap di garbage collection. Se si usa il `GetObjectSize` metodo per passare da un oggetto a un oggetto nell'heap di garbage collection, aggiungere padding manualmente, in base alle esigenze di allineamento.  
  
-   In Windows a 32 bit, COR_PRF_GC_GEN_0 COR_PRF_GC_GEN_1 e COR_PRF_GC_GEN_2 usano l'allineamento a 4 byte e COR_PRF_GC_LARGE_OBJECT_HEAP Usa l'allineamento a 8 byte.  
  
-   In Windows a 64 bit, l'allineamento è sempre 8 byte.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
