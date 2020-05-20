---
title: Interfaccia ICLRProbingAssemblyEnum
ms.date: 03/30/2017
api_name:
- ICLRProbingAssemblyEnum
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRProbingAssemblyEnum
helpviewer_keywords:
- ICLRProbingAssemblyEnum interface [.NET Framework hosting]
ms.assetid: e7d3ccab-b0f0-4872-8935-0ed72920171b
topic_type:
- apiref
ms.openlocfilehash: e1e114070f39e75254fc1bc0f8c1bf3e4733d5a2
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703380"
---
# <a name="iclrprobingassemblyenum-interface"></a>Interfaccia ICLRProbingAssemblyEnum
Fornisce metodi che consentono all'host di ottenere le identità di probe di un assembly usando le informazioni sull'identità dell'assembly interne al Common Language Runtime (CLR), senza dover creare o comprendere tale identità.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo Get](iclrprobingassemblyenum-get-method.md)|Ottiene l'identità dell'assembly in corrispondenza dell'indice specificato.|  
  
## <a name="remarks"></a>Osservazioni  
 I metodi, ad esempio [ICLRAssemblyIdentityManager:: GetProbingAssembliesFromReference](iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md) , restituiscono un' `ICLRProbingAssemblyEnum` istanza di.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRAssemblyIdentityManager](iclrassemblyidentitymanager-interface.md)
- [Interfaccia ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md)
- [Interfacce di hosting](hosting-interfaces.md)
