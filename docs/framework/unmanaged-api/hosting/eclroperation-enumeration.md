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
ms.openlocfilehash: 4b18c89cee0c3f5088a9978e448a0d61de1b9848
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33434245"
---
# <a name="eclroperation-enumeration"></a>Enumerazione EClrOperation
Viene descritto il set di operazioni per il quale un host può applicare le azioni dei criteri.  
  
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
  
|Membro|Descrizione|  
|------------|-----------------|  
|`OPR_AppDomainRudeUnload`|L'host può specificare le azioni dei criteri da eseguire quando un <xref:System.AppDomain> viene scaricato in un non normale modo.|  
|`OPR_AppDomainUnload`|L'host può specificare le azioni dei criteri da eseguire quando un <xref:System.AppDomain> viene scaricato.|  
|`OPR_FinalizerRun`|L'host può specificare le azioni da intraprendere quando esegue i finalizzatori dei criteri.|  
|`OPR_ProcessExit`|L'host può specificare le azioni dei criteri da eseguire quando il processo viene chiuso.|  
|`OPR_ThreadAbort`|L'host può specificare le azioni dei criteri da eseguire quando un thread viene interrotto.|  
|`OPR_ThreadRudeAbortInCriticalRegion`|L'host può specificare le azioni da intraprendere quando si verifica un'interruzione del thread in modo irregolare in un'area critica del codice dei criteri.|  
|`OPR_ThreadRudeAbortInNonCriticalRegion`|L'host può specificare le azioni dei criteri da eseguire quando si verifica un'interruzione del thread in modo irregolare in un'area critica del codice.|  
  
## <a name="remarks"></a>Note  
 L'infrastruttura di affidabilità di common language runtime (CLR) viene fatta distinzione tra le interruzioni e risorse errori di allocazione che si verificano in aree critiche del codice e quelli che si verificano in aree non critici del codice. Questa distinzione è progettata per consentire agli host di impostare criteri diversi a seconda di dove si verifica un errore nel codice.  
  
 Oggetto *area critica del codice* è qualsiasi spazio in Common Language Runtime non è possibile garantire che l'interruzione di un'attività o il mancato completamento di una richiesta di risorse influirà solo l'attività corrente. Ad esempio, se un'attività contenente un blocco e riceve un HRESULT che indica un errore durante l'inoltro di una richiesta di allocazione della memoria, è sufficiente semplicemente interrompere l'attività per garantire la stabilità del <xref:System.AppDomain>, in quanto il <xref:System.AppDomain> potrebbe contenere altri attività in attesa del blocco stesso. Abbandono corrente attività potrebbe causare altre attività di blocco (o di blocco) per un periodo illimitato. In tal caso, l'host deve essere in grado di scaricare l'intero <xref:System.AppDomain> anziché instabilità a rischio.  
  
 Oggetto *area critica di codice*, d'altra parte, è un'area in cui il CLR è in grado di garantire che un'interruzione o un errore influirà solo l'attività che si verifica l'errore.  
  
 Common Language Runtime distingue anche tra normale e non regolari interruzioni (RudeAbort). In generale, interruzione di una normale o normale cercherà di eseguire routine di gestione delle eccezioni e finalizzatori prima di annullare un'attività, mentre un'interruzione irregolare alcuna garanzia di questo tipo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Mscoree. H  
  
 **Libreria:** Mscoree. dll  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Enumerazione EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)  
 [Enumerazione EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)  
 [Interfaccia ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 [Interfaccia IHostPolicyManager](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)  
 [Enumerazioni di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
