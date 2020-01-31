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
ms.openlocfilehash: 24d245bbb0f9ac86e321491e0af3b66b1e011baa
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789211"
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
|[Interfaccia ICorPublish](icorpublish-interface.md)|Fornisce metodi per la pubblicazione di informazioni sui processi e sui domini applicazione in tali processi.|  
|[Interfaccia ICorPublishAppDomain](icorpublishappdomain-interface.md)|Rappresenta e fornisce informazioni su un dominio applicazione in un processo.|  
|[Interfaccia ICorPublishAppDomainEnum](icorpublishappdomainenum-interface.md)|Fornisce metodi che attraversano una raccolta di domini applicazione attualmente presenti all'interno di un processo.|  
|[Interfaccia ICorPublishProcess](icorpublishprocess-interface.md)|Rappresenta un processo in esecuzione in un computer.|  
|[Interfaccia ICorPublishProcessEnum](icorpublishprocessenum-interface.md)|Fornisce metodi che attraversano una raccolta di processi in esecuzione in un computer.|  
  
## <a name="remarks"></a>Note  
 Uno scenario di pubblicazione tipico prevede lo sviluppatore che desidera eseguire il debug di codice gestito in esecuzione in un computer all'interno di un dominio dell'applicazione. L'ambiente host può eseguire più di un dominio applicazione all'interno di un processo. Lo sviluppatore desidera utilizzare un'interfaccia utente grafica o un altro mezzo per elencare tutti i processi in esecuzione nel computer e selezionare un processo specifico. L'elenco deve includere tutti i domini applicazione all'interno dei processi che eseguono codice gestito. Lo sviluppatore può quindi identificare il dominio dell'applicazione specifico e alleghiare un debugger a tale dominio.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorPub. idl  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Debug](index.md)
