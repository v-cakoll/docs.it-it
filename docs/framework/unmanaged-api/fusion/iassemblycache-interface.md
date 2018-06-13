---
title: Interfaccia IAssemblyCache
ms.date: 03/30/2017
api_name:
- IAssemblyCache
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCache
helpviewer_keywords:
- IAssemblyCache interface [.NET Framework fusion]
ms.assetid: 71ea170f-872d-4fc5-81b6-27da1dec9b19
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4302a73f9f077c2e1bf4f66c2b80ab025ae4a62c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33430583"
---
# <a name="iassemblycache-interface"></a>Interfaccia IAssemblyCache
Rappresenta la global assembly cache per l'utilizzo dalla tecnologia fusion.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo CreateAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-createassemblycacheitem-method.md)|Ottiene un riferimento a un nuovo [IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md).|  
|[Metodo CreateAssemblyScavenger](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-createassemblyscavenger-method.md)|Riservato per uso interno dalla tecnologia fusion.|  
|[Metodo InstallAssembly](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-installassembly-method.md)|Installa l'assembly specificato nella global assembly cache.|  
|[Metodo QueryAssemblyInfo](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-queryassemblyinfo-method.md)|Ottiene i dati richiesti sull'assembly specificato.|  
|[Metodo UninstallAssembly](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-uninstallassembly-method.md)|Disinstalla l'assembly specificato dalla global assembly cache.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Fusion. h  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfacce Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)  
 [Global Assembly Cache](../../../../docs/framework/app-domains/gac.md)
