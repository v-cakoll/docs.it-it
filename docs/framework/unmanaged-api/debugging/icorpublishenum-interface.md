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
ms.openlocfilehash: acbc37d0f49af21c60ff6989932c5d341673512b
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421176"
---
# <a name="icorpublishenum-interface"></a>Interfaccia ICorPublishEnum
Funge da interfaccia di base astratta per gli enumeratori utilizzati nella pubblicazione di informazioni sui processi e sui domini dell'applicazione.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo Clone](icorpublishenum-clone-method.md)|Crea una copia dell'oggetto `ICorPublishEnum`.|  
|[Metodo GetCount](icorpublishenum-getcount-method.md)|Ottiene il numero di elementi nell'enumerazione.|  
|[Metodo Reset](icorpublishenum-reset-method.md)|Sposta il cursore di all'inizio dell'enumerazione.|  
|[Metodo Skip](icorpublishenum-skip-method.md)|Sposta il cursore verso l'interno dell'enumerazione in base al numero di elementi specificato.|  
  
## <a name="remarks"></a>Osservazioni  
 Gli enumeratori seguenti derivano da `ICorPublishEnum` :  
  
- [ICorPublishAppDomainEnum](icorpublishappdomainenum-interface.md)  
  
- [ICorPublishProcessEnum](icorpublishprocessenum-interface.md)  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorPub. idl, CorPub. h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Coclasse CorpubPublish](corpubpublish-coclass.md)
- [Interfacce di debug](debugging-interfaces.md)
