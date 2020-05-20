---
title: Interfaccia ICLRGCManager2
ms.date: 03/30/2017
api_name:
- ICLRGCManager2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRGCManager2
helpviewer_keywords:
- ICLRGCManager2 interface [.NET Framework hosting]
ms.assetid: 4b5ffd7b-9ad7-41cd-9bba-34030ae3da7e
topic_type:
- apiref
ms.openlocfilehash: 0f3ecc0d497eaee937647df47ba0956335a2fe41
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703952"
---
# <a name="iclrgcmanager2-interface"></a>Interfaccia ICLRGCManager2
Fornisce metodi che consentono a un host di interagire con il sistema di Garbage Collection del Common Language Runtime.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo SetGCStartupLimitsEx](iclrgcmanager2-setgcstartuplimitsex-method.md)|Imposta la dimensione di un segmento di Garbage Collection e la dimensione massima della generazione 0 del sistema Garbage Collection. Abilita la generazione 0 e le dimensioni dei segmenti maggiori di `DWORD` .|  
  
## <a name="remarks"></a>Osservazioni  
 Questa interfaccia eredita dall' [Interfaccia ICLRGCManager](iclrgcmanager-interface.md).  
  
 Il Common Language Runtime (CLR) implementa il meccanismo Garbage Collection con il <xref:System.GC> tipo gestito. Per ulteriori informazioni sul sistema di Garbage Collection, vedere [Garbage Collection](../../../standard/garbage-collection/index.md).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Gestione automatica della memoria](../../../standard/automatic-memory-management.md)
- [Struttura COR_GC_STATS](cor-gc-stats-structure.md)
- [Interfaccia ICLRControl](iclrcontrol-interface.md)
- [Interfacce di hosting CLR aggiunte in .NET Framework 4 e 4.5](clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)
- [Interfacce di hosting](hosting-interfaces.md)
- [Hosting](index.md)
