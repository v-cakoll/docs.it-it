---
title: Interfaccia IAssemblyName
ms.date: 03/30/2017
api_name:
- IAssemblyName
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName
helpviewer_keywords:
- IAssemblyName interface [.NET Framework fusion]
ms.assetid: f7f8e605-6b67-4151-936f-f04ecd671d90
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0d8d59ef282818dd9852d0ff8d2ec2abd40986d0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59097135"
---
# <a name="iassemblyname-interface"></a>Interfaccia IAssemblyName
Fornisce metodi per la descrizione e l'utilizzo di identità univoca di un assembly.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo Clone](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-clone-method.md)|Crea una copia superficiale dell'oggetto `IAssemblyName` oggetto.|  
|[Metodo Finalize](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-finalize-method.md)|Consente questo `IAssemblyName` oggetto rilasciare risorse ed eseguire altre operazioni di pulizia prima che venga chiamato il relativo distruttore.|  
|[Metodo GetDisplayName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-getdisplayname-method.md)|Ottiene il nome leggibile dell'assembly a cui fa riferimento `IAssemblyName` oggetto.|  
|[Metodo GetName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-getname-method.md)|Ottiene il nome semplice e non crittografato dell'assembly a cui fa riferimento `IAssemblyName` oggetto.|  
|[Metodo GetProperty](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-getproperty-method.md)|Ottiene un puntatore per la proprietà fa riferimento l'oggetto specificato `PropertyId`.|  
|[Metodo GetVersion](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-getversion-method.md)|Ottiene le informazioni sulla versione per l'assembly fa riferimento questo `IAssemblyName` oggetto.|  
|[Metodo IsEqual](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-isequal-method.md)|Determina se un oggetto specificato `IAssemblyName` è uguale all'oggetto `IAssemblyName`, in base al flag di confronto specificati.|  
|[Metodo SetProperty](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-setproperty-method.md)|Imposta il valore della proprietà specificato fa riferimento `PropertyId`.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Fusion. h  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
- [Interfaccia IAssemblyEnum](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md)
