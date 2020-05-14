---
title: Interfaccia ICorPublish
ms.date: 03/30/2017
api_name:
- ICorPublish
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublish
helpviewer_keywords:
- ICorPublish interface [.NET Framework debugging]
ms.assetid: 87c4fcb2-7703-4a2e-afb6-42973381b960
topic_type:
- apiref
ms.openlocfilehash: 1bd2f537cfa6a27c24ba91ea7caa29dc9e71a74e
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396317"
---
# <a name="icorpublish-interface"></a>Interfaccia ICorPublish
Funge da interfaccia generale per la pubblicazione di informazioni sui processi e sulle informazioni sui domini applicazione in tali processi.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo EnumProcesses](icorpublish-enumprocesses-method.md)|Ottiene un'istanza di [ICorPublishProcessEnum](icorpublishprocessenum-interface.md) che contiene i processi gestiti in esecuzione nel computer.|  
|[Metodo GetProcess](icorpublish-getprocess-method.md)|Ottiene un'istanza di [ICorPublishProcess](icorpublishprocess-interface.md) che rappresenta il processo con l'identificatore specificato.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorPub. idl, CorPub. h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedi anche

- [Interfacce di debug](debugging-interfaces.md)
- [Coclasse CorpubPublish](corpubpublish-coclass.md)
