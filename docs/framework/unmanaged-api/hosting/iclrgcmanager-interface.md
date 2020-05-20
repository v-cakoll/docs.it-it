---
title: Interfaccia ICLRGCManager
ms.date: 03/30/2017
api_name:
- ICLRGCManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRGCManager
helpviewer_keywords:
- ICLRGCManager interface [.NET Framework hosting]
ms.assetid: fb511c9b-3fe4-41b0-822a-6ba4a079d1f5
topic_type:
- apiref
ms.openlocfilehash: 76a50be6da790ed7bd193c489d36e2823cdbe587
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616962"
---
# <a name="iclrgcmanager-interface"></a>Interfaccia ICLRGCManager
Fornisce metodi che consentono a un host di interagire con il sistema di Garbage Collection del Common Language Runtime.  
  
> [!NOTE]
> A partire da .NET Framework 4,5, è possibile usare il metodo [ICLRGCManager2:: SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) per impostare le dimensioni di un segmento di Garbage Collection e le dimensioni massime della generazione 0 del sistema di Garbage Collection su valori maggiori del `DWORD` limite imposto dal metodo [SetGCStartupLimits](iclrgcmanager-setgcstartuplimits-method.md) .  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo Collect](iclrgcmanager-collect-method.md)|Impone un Garbage Collection per la generazione specificata.|  
|[Metodo GetStats](iclrgcmanager-getstats-method.md)|Ottiene un set di statistiche correnti sul sistema di Garbage Collection.|  
|[Metodo SetGCStartupLimits](iclrgcmanager-setgcstartuplimits-method.md)|Imposta la dimensione di un segmento di Garbage Collection e la dimensione massima della generazione 0 del sistema Garbage Collection.|  
  
## <a name="remarks"></a>Osservazioni  
 Il Common Language Runtime (CLR) implementa il meccanismo Garbage Collection con il <xref:System.GC> tipo gestito. Per ulteriori informazioni sul sistema di Garbage Collection, vedere [Garbage Collection](../../../standard/garbage-collection/index.md).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Gestione automatica della memoria](../../../standard/automatic-memory-management.md)
- [Struttura COR_GC_STATS](cor-gc-stats-structure.md)
- [Interfaccia ICLRControl](iclrcontrol-interface.md)
- [Interfacce di hosting CLR](clr-hosting-interfaces.md)
- [Interfacce di hosting](hosting-interfaces.md)
- [Hosting](index.md)
