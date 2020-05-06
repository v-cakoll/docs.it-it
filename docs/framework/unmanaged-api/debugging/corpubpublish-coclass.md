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
ms.openlocfilehash: e33029e8244fdfa180a79aa4a5b05b07f594d928
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860903"
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
  
## <a name="remarks"></a>Osservazioni  
 Uno scenario di pubblicazione tipico prevede lo sviluppatore che desidera eseguire il debug di codice gestito in esecuzione in un computer all'interno di un dominio dell'applicazione. L'ambiente host può eseguire più di un dominio applicazione all'interno di un processo. Lo sviluppatore desidera utilizzare un'interfaccia utente grafica o un altro mezzo per elencare tutti i processi in esecuzione nel computer e selezionare un processo specifico. L'elenco deve includere tutti i domini applicazione all'interno dei processi che eseguono codice gestito. Lo sviluppatore può quindi identificare il dominio dell'applicazione specifico e alleghiare un debugger a tale dominio.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorPub. idl  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Debug](index.md)
