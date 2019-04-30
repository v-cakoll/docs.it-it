---
title: Interfaccia ICorPublishAppDomainEnum
ms.date: 03/30/2017
api_name:
- ICorPublishAppDomainEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishAppDomainEnum
helpviewer_keywords:
- ICorPublishAppDomainEnum interface [.NET Framework debugging]
ms.assetid: bb798c56-042e-475d-a245-b6fac36d0c07
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0f6d4af7c01f91dff77d6ba715ef845f523c7fb6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61993551"
---
# <a name="icorpublishappdomainenum-interface"></a>Interfaccia ICorPublishAppDomainEnum
Una sottoclasse di [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) interfaccia che fornisce metodi che scorrono una raccolta di [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md) oggetti attualmente presenti all'interno di un processo.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo Next](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-next-method.md)|Ottiene il numero specificato di `ICorPublishAppDomain` istanze dalla raccolta, a partire dalla posizione corrente.|  
  
## <a name="remarks"></a>Note  
 Il `ICorPublishAppDomainEnum` interface implementa i metodi dell'interfaccia astratta [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorPub.idl, CorPub.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Coclasse CorpubPublish](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
