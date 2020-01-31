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
ms.openlocfilehash: 3ae48df9e66890161c1aef944d37b0a279939d56
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790547"
---
# <a name="icorpublishprocess-interface"></a>Interfaccia ICorPublishProcess
Fornisce metodi che accedono alle informazioni da visualizzare su un processo.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo EnumAppDomains](icorpublishprocess-enumappdomains-method.md)|Ottiene un'istanza di [ICorPublishAppDomainEnum](icorpublishappdomainenum-interface.md) che contiene i domini applicazione nel processo a cui fa riferimento questo `ICorPublishProcess`.|  
|[Metodo GetDisplayName](icorpublishprocess-getdisplayname-method.md)|Ottiene il percorso completo dell'eseguibile per il processo a cui fa riferimento questo `ICorPublishProcess`.|  
|[Metodo GetProcessID](icorpublishprocess-getprocessid-method.md)|Ottiene l'identificatore del sistema operativo per il processo a cui fa riferimento questo `ICorPublishProcess`.|  
|[Metodo IsManaged](icorpublishprocess-ismanaged-method.md)|Ottiene un valore che indica se il processo a cui viene fatto riferimento da questo `ICorPublishProcess` è noto per l'esecuzione di codice gestito.|  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorPub. idl, CorPub. h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](debugging-interfaces.md)
- [Coclasse CorpubPublish](corpubpublish-coclass.md)
