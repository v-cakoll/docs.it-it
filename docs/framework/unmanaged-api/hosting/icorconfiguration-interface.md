---
title: Interfaccia ICorConfiguration
ms.date: 03/30/2017
api_name:
- ICorConfiguration
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorConfiguration
helpviewer_keywords:
- ICorConfiguration interface [.NET Framework hosting]
ms.assetid: aaf96116-372b-4538-afb1-9e0fcdac1f98
topic_type:
- apiref
ms.openlocfilehash: 3b8c9421dea4040a9f183b886f1ad8575cace780
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762429"
---
# <a name="icorconfiguration-interface"></a>Interfaccia ICorConfiguration
Fornisce metodi per la configurazione del Common Language Runtime (CLR).  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo AddDebuggerSpecialThread](icorconfiguration-adddebuggerspecialthread-method.md)|Indica ai servizi di debug che un determinato thread deve essere in grado di continuare l'esecuzione mentre nel debugger è stata arrestata un'applicazione durante gli scenari di debug gestiti o non gestiti.|  
|[Metodo SetDebuggerThreadControl](icorconfiguration-setdebuggerthreadcontrol-method.md)|Imposta l'interfaccia di callback che i servizi di debug chiameranno come thread CLR vengono bloccati e sbloccati per il debug.|  
|[Metodo SetGCHostControl](icorconfiguration-setgchostcontrol-method.md)|Imposta l'interfaccia di callback che deve essere utilizzata dal Garbage Collector per richiedere all'host di modificare i limiti della memoria virtuale.|  
|[Metodo SetGCThreadControl](icorconfiguration-setgcthreadcontrol-method.md)|Imposta l'interfaccia di callback per la pianificazione di thread per le attività non di runtime che altrimenti verrebbero bloccate per un Garbage Collection.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di hosting](hosting-interfaces.md)
- [Coclasse CorRuntimeHost](corruntimehost-coclass.md)
