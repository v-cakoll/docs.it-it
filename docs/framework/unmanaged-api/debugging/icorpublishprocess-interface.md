---
title: Interfaccia ICorPublishProcess
ms.date: 03/30/2017
api_name:
- ICorPublishProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess
helpviewer_keywords:
- ICorPublishProcess interface [.NET Framework debugging]
ms.assetid: 6d1dc41b-8aa2-4889-bb00-1cbccc00c123
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 08dfa3ddbfd9cffdb0cb88d0325e5703a854668a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59182962"
---
# <a name="icorpublishprocess-interface"></a>Interfaccia ICorPublishProcess
Fornisce metodi che accedono alle informazioni da visualizzare su un processo.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo EnumAppDomains](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-enumappdomains-method.md)|Ottiene un' [ICorPublishAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md) istanza che contiene i domini applicazione nel processo di cui fa riferimento questo `ICorPublishProcess`.|  
|[Metodo GetDisplayName](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-getdisplayname-method.md)|Ottiene il percorso completo del file eseguibile per il processo a cui fa riferimento `ICorPublishProcess`.|  
|[Metodo GetProcessID](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-getprocessid-method.md)|Ottiene l'identificatore del sistema operativo per il processo a cui fa riferimento `ICorPublishProcess`.|  
|[Metodo IsManaged](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-ismanaged-method.md)|Ottiene un valore che indica se il processo fa riferimento questo `ICorPublishProcess` è noto per essere in esecuzione il codice gestito.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorPub.idl, CorPub.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Coclasse CorpubPublish](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
