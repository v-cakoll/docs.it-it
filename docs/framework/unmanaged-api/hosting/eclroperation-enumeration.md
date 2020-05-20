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
ms.openlocfilehash: e7cb1c2070e760258e548d2f45e3b6ed11e046c4
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616320"
---
# <a name="eclroperation-enumeration"></a>Enumerazione EClrOperation
Descrive il set di operazioni per cui un host può applicare le azioni dei criteri.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
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
  
|Membro|Description|  
|------------|-----------------|  
|`OPR_AppDomainRudeUnload`|L'host può specificare le azioni dei criteri da intraprendere quando un oggetto <xref:System.AppDomain> viene scaricato in modo non normale (rude).|  
|`OPR_AppDomainUnload`|L'host può specificare le azioni dei criteri da intraprendere quando <xref:System.AppDomain> viene scaricato un oggetto.|  
|`OPR_FinalizerRun`|L'host può specificare le azioni dei criteri da intraprendere quando vengono eseguiti i finalizzatori.|  
|`OPR_ProcessExit`|L'host può specificare le azioni dei criteri da intraprendere quando il processo viene chiuso.|  
|`OPR_ThreadAbort`|L'host può specificare le azioni dei criteri da intraprendere quando un thread viene interrotto.|  
|`OPR_ThreadRudeAbortInCriticalRegion`|L'host può specificare le azioni dei criteri da intraprendere quando si verifica un'interruzione di thread rude in un'area critica del codice.|  
|`OPR_ThreadRudeAbortInNonCriticalRegion`|L'host può specificare le azioni dei criteri da intraprendere quando si verifica un'interruzione di thread rude in un'area di codice non critica.|  
  
## <a name="remarks"></a>Osservazioni  
 L'infrastruttura di affidabilità Common Language Runtime (CLR) distingue le interruzioni e gli errori di allocazione delle risorse che si verificano in aree critiche del codice e quelle che si verificano in aree di codice non critiche. Questa distinzione è progettata per consentire agli host di impostare criteri diversi a seconda della posizione in cui si verifica un errore nel codice.  
  
 Un' *area critica del codice* è uno spazio in cui CLR non è in grado di garantire che l'interruzione di un'attività o la mancata esecuzione di una richiesta di risorse influirà solo sull'attività corrente. Se, ad esempio, un'attività mantiene un blocco e riceve un valore HRESULT che indica un errore durante l'esecuzione di una richiesta di allocazione della memoria, non è sufficiente interrompere tale attività per garantire la stabilità di <xref:System.AppDomain> , perché <xref:System.AppDomain> potrebbe contenere altre attività in attesa dello stesso blocco. Per abbandonare l'attività corrente, le altre attività potrebbero smettere di rispondere. In tal caso, l'host deve essere in grado di scaricare l'intero <xref:System.AppDomain> anziché il rischio di instabilità.  
  
 Un' *area di codice non critica*, d'altra parte, è un'area in cui CLR può garantire che un'interruzione o un errore influirà solo sull'attività su cui si verifica l'errore.  
  
 CLR distingue anche tra interruzioni aggraziate e non aggraziate (rude). In generale, un'interruzione normale o normale esegue ogni sforzo per eseguire le routine di gestione delle eccezioni e i finalizzatori prima di interrompere un'attività, mentre un'interruzione rude non rende tali garanzie.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazione EClrFailure](eclrfailure-enumeration.md)
- [Enumerazione EPolicyAction](epolicyaction-enumeration.md)
- [Interfaccia ICLRPolicyManager](iclrpolicymanager-interface.md)
- [Interfaccia IHostPolicyManager](ihostpolicymanager-interface.md)
- [Enumerazioni di hosting](hosting-enumerations.md)
