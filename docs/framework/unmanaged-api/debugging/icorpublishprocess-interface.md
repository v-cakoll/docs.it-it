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
ms.openlocfilehash: 04f6a088c5bbe96e3909ba600aa8ffab937abe2d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140406"
---
# <a name="icorpublishprocess-interface"></a>Interfaccia ICorPublishProcess
Fornisce metodi che accedono alle informazioni da visualizzare su un processo.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo EnumAppDomains](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-enumappdomains-method.md)|Ottiene un'istanza di [ICorPublishAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md) che contiene i domini applicazione nel processo a cui fa riferimento questo `ICorPublishProcess`.|  
|[Metodo GetDisplayName](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-getdisplayname-method.md)|Ottiene il percorso completo dell'eseguibile per il processo a cui fa riferimento questo `ICorPublishProcess`.|  
|[Metodo GetProcessID](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-getprocessid-method.md)|Ottiene l'identificatore del sistema operativo per il processo a cui fa riferimento questo `ICorPublishProcess`.|  
|[Metodo IsManaged](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-ismanaged-method.md)|Ottiene un valore che indica se il processo a cui viene fatto riferimento da questo `ICorPublishProcess` è noto per l'esecuzione di codice gestito.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorPub. idl, CorPub. h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Coclasse CorpubPublish](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
