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
ms.openlocfilehash: a48e20413f466e25a9145e9dbf1ba93d90155770
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "83397037"
---
# <a name="icorpublishappdomainenum-interface"></a>Interfaccia ICorPublishAppDomainEnum
Sottoclasse dell'interfaccia [ICorPublishEnum](icorpublishenum-interface.md) che fornisce i metodi per attraversare una raccolta di oggetti [ICorPublishAppDomain](icorpublishappdomain-interface.md) attualmente presenti all'interno di un processo.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo Next](icorpublishappdomainenum-next-method.md)|Ottiene il numero specificato di `ICorPublishAppDomain` istanze dalla raccolta, a partire dalla posizione corrente.|  
  
## <a name="remarks"></a>Commenti  
 L' `ICorPublishAppDomainEnum` interfaccia implementa i metodi dell'interfaccia astratta, [ICorPublishEnum](icorpublishenum-interface.md).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorPub. idl, CorPub. h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedi anche

- [Interfacce di debug](debugging-interfaces.md)
- [Coclasse CorpubPublish](corpubpublish-coclass.md)
