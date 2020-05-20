---
title: Interfaccia ICLRAssemblyIdentityManager
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager
helpviewer_keywords:
- ICLRAssemblyIdentityManager interface [.NET Framework hosting]
ms.assetid: 6a81c6fe-cc22-4062-ae27-d6eeee03a7b9
topic_type:
- apiref
ms.openlocfilehash: f06c8228d5eb850c0d5ff94d12be03d7fb75023b
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615917"
---
# <a name="iclrassemblyidentitymanager-interface"></a>Interfaccia ICLRAssemblyIdentityManager
Fornisce metodi che supportano la comunicazione tra l'host e il Common Language Runtime (CLR) sugli assembly.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo GetBindingIdentityFromFile](iclrassemblyidentitymanager-getbindingidentityfromfile-method.md)|Ottiene i dati dell'associazione di identità dell'assembly per l'assembly nel percorso del file specificato.|  
|[Metodo GetBindingIdentityFromStream](iclrassemblyidentitymanager-getbindingidentityfromstream-method.md)|Ottiene i dati di identità dell'assembly canonico per l'assembly nel flusso specificato.|  
|[Metodo GetCLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md)|Ottiene un'istanza di [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) dall'elenco fornito di identità di assembly parziali.|  
|[Metodo GetProbingAssembliesFromReference](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md)|Ottiene un enumeratore [ICLRProbingAssemblyEnum](iclrprobingassemblyenum-interface.md) per le identità di assembly a cui fa riferimento l'assembly con l'identità specificata.|  
|[Metodo GetReferencedAssembliesFromFile](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getreferencedassembliesfromfile-method.md)|Ottiene un'istanza di [ICLRReferenceAssemblyEnum](iclrreferenceassemblyenum-interface.md) che contiene un elenco di assembly a cui fa riferimento l'assembly nel percorso del file specificato.|  
|[Metodo GetReferencedAssembliesFromStream](iclrassemblyidentitymanager-getreferencedassembliesfromstream-method.md)|Ottiene un puntatore a un `ICLRReferenceAssemblyEnum` oggetto che contiene i dati di identità dell'assembly per gli assembly a cui fa riferimento l'assembly nel flusso specificato.|  
|[Metodo IsStronglyNamed](iclrassemblyidentitymanager-isstronglynamed-method.md)|Ottiene un valore che indica se l'assembly specificato ha un nome sicuro.|  
  
## <a name="remarks"></a>Osservazioni  
 Utilizzare `ICLRAssemblyIdentityManager` per ottenere le istanze di `ICLRAssemblyReferenceList` e per enumerare le identità degli assembly.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md)
- [Interfaccia ICLRProbingAssemblyEnum](iclrprobingassemblyenum-interface.md)
- [Interfacce di hosting](hosting-interfaces.md)
