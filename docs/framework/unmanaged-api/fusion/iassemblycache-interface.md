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
ms.openlocfilehash: 5ed0075da1429c70900750f3f28e8ce36a41fb28
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134545"
---
# <a name="iassemblycache-interface"></a>Interfaccia IAssemblyCache
Rappresenta l'Global Assembly Cache per l'utilizzo da parte della tecnologia Fusion.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo CreateAssemblyCacheItem](iassemblycache-createassemblycacheitem-method.md)|Ottiene un riferimento a un nuovo [IAssemblyCacheItem](iassemblycacheitem-interface.md).|  
|[Metodo CreateAssemblyScavenger](iassemblycache-createassemblyscavenger-method.md)|Riservato per uso interno da parte della tecnologia Fusion.|  
|[Metodo InstallAssembly](iassemblycache-installassembly-method.md)|Installa l'assembly specificato nel Global Assembly Cache.|  
|[Metodo QueryAssemblyInfo](iassemblycache-queryassemblyinfo-method.md)|Ottiene i dati richiesti sull'assembly specificato.|  
|[Metodo UninstallAssembly](iassemblycache-uninstallassembly-method.md)|Disinstalla l'assembly specificato dal Global Assembly Cache.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Fusion. h  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce Fusion](fusion-interfaces.md)
- [Global Assembly Cache](../../app-domains/gac.md)
