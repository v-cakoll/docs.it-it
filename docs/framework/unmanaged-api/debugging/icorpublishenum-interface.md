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
ms.openlocfilehash: 7d083655326333f18ee98f8e84fff2ed182dde6d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73103458"
---
# <a name="icorpublishenum-interface"></a>Interfaccia ICorPublishEnum
Funge da interfaccia di base astratta per gli enumeratori utilizzati nella pubblicazione di informazioni sui processi e sui domini dell'applicazione.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo Clone](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-clone-method.md)|Crea una copia di questo oggetto `ICorPublishEnum`.|  
|[Metodo GetCount](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-getcount-method.md)|Ottiene il numero di elementi nell'enumerazione.|  
|[Metodo Reset](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-reset-method.md)|Sposta il cursore di all'inizio dell'enumerazione.|  
|[Metodo Skip](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-skip-method.md)|Sposta il cursore verso l'interno dell'enumerazione in base al numero di elementi specificato.|  
  
## <a name="remarks"></a>Note  
 Gli enumeratori seguenti derivano da `ICorPublishEnum`:  
  
- [ICorPublishAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)  
  
- [ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md)  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorPub. idl, CorPub. h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Coclasse CorpubPublish](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
