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
ms.openlocfilehash: e9cbf4551c2f8b183e9e6c37a74b13aff3a19ec1
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76860969"
---
# <a name="imethodmalloc-interface"></a>Interfaccia IMethodMalloc
Fornisce un metodo per allocare memoria per un nuovo corpo della funzione MSIL (Microsoft Intermediate Language).  
  
> [!NOTE]
> L'interfaccia `IMethodMalloc` è un semplice allocatore di memoria. Consente di allocare memoria, ma non di liberarla.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo Alloc](imethodmalloc-alloc-method.md)|Tenta di allocare una quantità specificata di memoria per un nuovo corpo della funzione MSIL.|  
  
## <a name="remarks"></a>Note  
 Ogni allocatore è specifico del modulo e garantisce che il corpo della funzione si trovi in corrispondenza di un offset positivo rispetto alla base del modulo. La memoria al di sopra della base di un modulo può essere preziosa, quindi l'allocatore deve essere usato per allocare memoria solo per il corpo di una funzione.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di profilatura](profiling-interfaces.md)
