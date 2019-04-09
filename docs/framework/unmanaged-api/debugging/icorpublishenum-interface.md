---
title: Interfaccia ICorPublishEnum
ms.date: 03/30/2017
api_name:
- ICorPublishEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishEnum
helpviewer_keywords:
- ICorPublishEnum interface [.NET Framework debugging]
ms.assetid: 76a136b5-e444-417a-8ade-f1596d597dc7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1eac0b9fe252e476f8ff781f2181a203886d3beb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59160135"
---
# <a name="icorpublishenum-interface"></a>Interfaccia ICorPublishEnum
Funge da interfaccia di base astratta per gli enumeratori utilizzati in sulla pubblicazione delle informazioni sui processi e domini dell'applicazione.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo Clone](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-clone-method.md)|Crea una copia di questo `ICorPublishEnum` oggetto.|  
|[Metodo GetCount](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-getcount-method.md)|Ottiene il numero di elementi nell'enumerazione.|  
|[Metodo Reset](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-reset-method.md)|Sposta il cursore all'inizio dell'enumerazione.|  
|[Metodo Skip](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-skip-method.md)|Sposta in avanti il cursore nell'enumerazione per il numero specificato di elementi.|  
  
## <a name="remarks"></a>Note  
 Gli enumeratori seguenti derivano da `ICorPublishEnum`:  
  
-   [ICorPublishAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)  
  
-   [ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md)  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorPub.idl, CorPub.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Coclasse CorpubPublish](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
