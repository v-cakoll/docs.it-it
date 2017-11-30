---
title: Interfaccia ICLRAssemblyIdentityManager
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRAssemblyIdentityManager
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRAssemblyIdentityManager
helpviewer_keywords: ICLRAssemblyIdentityManager interface [.NET Framework hosting]
ms.assetid: 6a81c6fe-cc22-4062-ae27-d6eeee03a7b9
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8d7fe632941c4cf0c20841ece390d2f41f28337d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="iclrassemblyidentitymanager-interface"></a>Interfaccia ICLRAssemblyIdentityManager
Fornisce metodi che supportano la comunicazione tra l'host e common language runtime (CLR) sugli assembly.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[GetBindingIdentityFromFile (metodo)](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromfile-method.md)|Ottiene l'identità dell'assembly di associazione dati per l'assembly nel percorso del file specificato.|  
|[GetBindingIdentityFromStream (metodo)](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromstream-method.md)|Ottiene i dati di identità assembly canonica per l'assembly nel flusso specificato.|  
|[GetCLRAssemblyReferenceList (metodo)](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md)|Ottiene un [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) istanza dall'elenco fornito di identità di assembly parziali.|  
|[GetProbingAssembliesFromReference (metodo)](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md)|Ottiene un [ICLRProbingAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md) enumeratore per le identità di assembly a cui fa riferimento l'assembly con l'identità specificata.|  
|[Metodo GetReferencedAssembliesFromFile](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getreferencedassembliesfromfile-method.md)|Ottiene un [ICLRReferenceAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md) istanza che contiene un elenco di assembly a cui fa riferimento l'assembly nel percorso del file specificato.|  
|[GetReferencedAssembliesFromStream (metodo)](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getreferencedassembliesfromstream-method.md)|Ottiene un puntatore a un `ICLRReferenceAssemblyEnum` oggetto che contiene i dati di identità di assembly per gli assembly a cui fa riferimento l'assembly nel flusso specificato.|  
|[IsStronglyNamed (metodo)](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-isstronglynamed-method.md)|Ottiene un valore che indica se l'assembly specificato è un nome sicuro.|  
  
## <a name="remarks"></a>Note  
 Utilizzare `ICLRAssemblyIdentityManager` per ottenere le istanze di `ICLRAssemblyReferenceList` ed enumerare le identità di assembly.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Mscoree. H  
  
 **Libreria:** inclusa come risorsa in MSCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [ICLRAssemblyReferenceList (interfaccia)](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [ICLRProbingAssemblyEnum (interfaccia)](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md)  
 [Interfacce di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
