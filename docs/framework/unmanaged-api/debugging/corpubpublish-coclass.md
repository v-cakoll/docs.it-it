---
title: Coclasse CorpubPublish
ms.date: 03/30/2017
api_name:
- CorpubPublish Coclass
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorpubPublish
helpviewer_keywords:
- CorpubPublish coclass [.NET Framework debugging]
ms.assetid: 191015da-f54a-4bac-a28a-1de7ab3c3428
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7d1ca8ea9d00de8a07c67977cf108c50268802e6
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67739350"
---
# <a name="corpubpublish-coclass"></a>Coclasse CorpubPublish
Fornisce interfacce per la pubblicazione di informazioni sui domini dell'applicazione e sui processi.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
coclass CorpubPublish {  
    [default] interface ICorPublish;  
    interface           ICorPublishProcess;  
    interface           ICorPublishAppDomain;  
    interface           ICorPublishProcessEnum;  
    interface           ICorPublishAppDomainEnum;  
};  
```  
  
## <a name="interfaces"></a>Interfacce  
  
|Interfaccia|Descrizione|  
|---------------|-----------------|  
|[Interfaccia ICorPublish](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md)|Fornisce metodi per la pubblicazione delle informazioni sui processi e i domini applicazione tali processi.|  
|[Interfaccia ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)|Rappresenta e fornisce informazioni su un dominio dell'applicazione in un processo.|  
|[Interfaccia ICorPublishAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)|Fornisce metodi che scorrono una raccolta di domini applicazione attualmente esistenti all'interno di un processo.|  
|[Interfaccia ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)|Rappresenta un processo in esecuzione in un computer.|  
|[Interfaccia ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md)|Fornisce metodi che scorrono una raccolta di processi in esecuzione in un computer.|  
  
## <a name="remarks"></a>Note  
 Un tipico scenario di pubblicazione comporta uno sviluppatore che desidera eseguire il debug di codice gestito che è in esecuzione in un computer all'interno di un dominio dell'applicazione. L'ambiente di hosting potrebbe essere più di un dominio applicazione all'interno di un processo in esecuzione. Lo sviluppatore desidera utilizzare un'interfaccia utente grafica o in altro modo per elencare tutti i processi in esecuzione nel computer e scegliere un processo specifico. L'elenco dovrebbe includere tutti i domini dell'applicazione all'interno di processi che eseguono il codice gestito. Lo sviluppatore può quindi identificare il dominio applicazione specifica e collegare un debugger per tale dominio.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorPub.idl  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Debug](../../../../docs/framework/unmanaged-api/debugging/index.md)
