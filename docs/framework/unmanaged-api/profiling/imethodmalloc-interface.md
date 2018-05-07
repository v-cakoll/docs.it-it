---
title: Interfaccia IMethodMalloc
ms.date: 03/30/2017
api_name:
- IMethodMalloc
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- IMethodMalloc
helpviewer_keywords:
- IMethodMalloc interface [.NET Framework profiling]
ms.assetid: 8c8ab5dc-557c-473a-82f2-6e403eca7dac
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b11cf0fadc9142ee291115cf9f0d84e6429834fb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="imethodmalloc-interface"></a>Interfaccia IMethodMalloc
Fornisce un metodo per allocare memoria per un nuovo corpo della funzione Microsoft intermediate language (MSIL).  
  
> [!NOTE]
>  Il `IMethodMalloc` interfaccia è un semplice allocatore di memoria. Consente di allocare memoria, ma non per liberarlo.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo Alloc](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-alloc-method.md)|Tenta di allocare una quantità di memoria specificata per il corpo di una nuova funzione MSIL.|  
  
## <a name="remarks"></a>Note  
 Ogni allocatore è specifico del modulo e assicura che il corpo della funzione sarà un offset positivo dalla base del modulo. Memoria di sopra della base di un modulo può essere preziosa, pertanto l'allocatore deve essere utilizzata per allocare memoria solo per un corpo della funzione.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfacce di profilatura](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
