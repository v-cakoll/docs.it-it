---
title: Enumerazione EClrOperation
ms.date: 03/30/2017
api_name:
- EClrOperation
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EClrOperation
helpviewer_keywords:
- EClrOperation enumeration [.NET Framework hosting]
ms.assetid: 5aef6808-5aac-4b2f-a2c7-fee1575c55ed
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7d5f24d7415ff7ecceba6b0a5fbd3098d70dcd0f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59190353"
---
# <a name="eclroperation-enumeration"></a>Enumerazione EClrOperation
Descrive il set di operazioni per il quale un host è possibile applicare azioni dei criteri.  
  
## <a name="syntax"></a>Sintassi  
  
```  
typedef enum {  
    OPR_ThreadAbort,  
    OPR_ThreadRudeAbortInNonCriticalRegion,  
    OPR_ThreadRudeAbortInCriticalRegion,  
    OPR_AppDomainUnload,  
    OPR_AppDomainRudeUnload,  
    OPR_ProcessExit,  
    OPR_FinalizerRun  
} EClrOperation;  
```  
  
## <a name="members"></a>Membri  
  
|Member|Descrizione|  
|------------|-----------------|  
|`OPR_AppDomainRudeUnload`|L'host può specificare le azioni dei criteri da eseguire quando un <xref:System.AppDomain> viene scaricato in modo non regolare (non applicabili).|  
|`OPR_AppDomainUnload`|L'host può specificare le azioni dei criteri da eseguire quando un <xref:System.AppDomain> viene scaricato.|  
|`OPR_FinalizerRun`|L'host può specificare azioni dei criteri da eseguire quando esegue i finalizzatori.|  
|`OPR_ProcessExit`|L'host può specificare le azioni dei criteri da eseguire quando il processo viene chiuso.|  
|`OPR_ThreadAbort`|L'host può specificare le azioni dei criteri da eseguire quando un thread viene interrotto.|  
|`OPR_ThreadRudeAbortInCriticalRegion`|L'host può specificare le azioni dei criteri da eseguire quando si verifica un'interruzione del thread non applicabili in un'area critica del codice.|  
|`OPR_ThreadRudeAbortInNonCriticalRegion`|L'host può specificare criteri le azioni da intraprendere quando si verifica un'interruzione del thread non applicabili in un'area critica del codice.|  
  
## <a name="remarks"></a>Note  
 L'infrastruttura di affidabilità di common language runtime (CLR) distingue tra risorse e le interruzioni di errori di allocazione che si verificano nelle aree critiche di codice e quelli che si verificano in aree non critici del codice. Questa distinzione è progettata per consentire agli host di impostare criteri diversi a seconda di dove si verifica un errore nel codice.  
  
 Oggetto *area critica del codice* qualsiasi spazio in cui CLR non può garantire che l'interruzione di un'attività o riesce a completare una richiesta di risorse influirà solo l'attività corrente. Ad esempio, se un'attività è bloccata da un blocco e riceve un valore HRESULT indicante un errore durante l'inoltro di una richiesta di allocazione della memoria, è sufficiente semplicemente interrompere l'attività per garantire la stabilità del <xref:System.AppDomain>, in quanto il <xref:System.AppDomain> potrebbe contenere altri attività in attesa per lo stesso blocco. Abbandonare corrente attività potrebbe causare altre attività di blocco (o un blocco) per un periodo illimitato. In tal caso, l'host deve essere in grado di scaricare l'intero <xref:System.AppDomain> invece di instabilità potenziali rischi.  
  
 Oggetto *area critica del codice*, d'altra parte, è un'area in cui CLR è in grado di garantire che un'interruzione o un errore interesserà solo l'attività su cui si verifica l'errore.  
  
 CLR consente di distinguere anche tra interruzioni (non applicabili) normali e non normali. In generale, un'interruzione normali o irregolari si impegna per eseguire routine di gestione delle eccezioni e i finalizzatori prima dell'interruzione di un'attività, anche se questo tipo garantisce in alcun modo di un'interruzione non applicabili.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE.h  
  
 **Libreria:** MSCorEE.dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazione EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [Enumerazione EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [Interfaccia ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [Interfaccia IHostPolicyManager](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
- [Enumerazioni di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
