---
title: Metodo ICorProfilerInfo::GetObjectSize
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.GetObjectSize
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo::GetObjectSize
helpviewer_keywords:
- GetObjectSize method [.NET Framework profiling]
- ICorProfilerInfo::GetObjectSize method [.NET Framework profiling]
ms.assetid: 9f02e763-73f7-42cb-a41c-f78499d9482c
topic_type: apiref
caps.latest.revision: "16"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9425938042485c4330fe3fbc50cdabde6451b427
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfogetobjectsize-method"></a>Metodo ICorProfilerInfo::GetObjectSize
Ottiene le dimensioni di un oggetto specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetObjectSize(  
    [in]  ObjectID objectId,  
    [out] ULONG  *pcSize);  
```  
  
#### <a name="parameters"></a>Parametri  
 `objectId`  
 [in] L'ID dell'oggetto.  
  
 `pcSize`  
 [out] Puntatore alla dimensione dell'oggetto, in byte.  
  
## <a name="remarks"></a>Note  
  
> [!IMPORTANT]
>  Questo metodo è obsoleto. Restituisce COR_E_OVERFLOW per gli oggetti maggiori di 4GB su piattaforme a 64 bit. Utilizzare il [icorprofilerinfo4:: Getobjectsize2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getobjectsize2-method.md) metodo invece.  
  
 Oggetti diversi dello stesso tipo hanno spesso la stessa dimensione. Tuttavia, alcuni tipi, ad esempio, stringhe o matrici possono avere una dimensione diversa per ogni oggetto.  
  
 Le dimensioni restituite dal `GetObjectSize` metodo non include alcun riempimento di allineamento che possono essere visualizzati quando l'oggetto è nell'heap del garbage collection. Se si utilizza il `GetObjectSize` metodo per passare da un oggetto a un oggetto nell'heap di garbage collection, aggiungere spaziatura interna manualmente, in base alle esigenze di allineamento.  
  
-   In Windows a 32 bit COR_PRF_GC_GEN_0 COR_PRF_GC_GEN_1 e COR_PRF_GC_GEN_2 usano l'allineamento a 4 byte e COR_PRF_GC_LARGE_OBJECT_HEAP Usa l'allineamento a 8 byte.  
  
-   In Windows a 64 bit, l'allineamento è sempre 8 byte.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
