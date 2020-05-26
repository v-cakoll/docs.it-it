---
title: Interfaccia IHostControl
ms.date: 03/30/2017
api_name:
- IHostControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostControl
helpviewer_keywords:
- IHostControl interface [.NET Framework hosting]
ms.assetid: a4ae0d1f-ade9-4b0a-a122-93ed11a5e6b3
topic_type:
- apiref
ms.openlocfilehash: 9dd89abb332853b966aa81dc506099b7af6ca3b2
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804925"
---
# <a name="ihostcontrol-interface"></a>Interfaccia IHostControl
Fornisce metodi per la configurazione del caricamento di assembly e per la determinazione delle interfacce di hosting supportate dall'host.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo GetHostManager](ihostcontrol-gethostmanager-method.md)|Ottiene un puntatore di interfaccia all'implementazione dell'host dell'interfaccia con l'oggetto specificato `IID` .|  
|[Metodo SetAppDomainManager](ihostcontrol-setappdomainmanager-method.md)|Notifica all'host che è stato creato un dominio dell'applicazione.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.AppDomainManager>
- [Interfaccia ICLRRuntimeHost](iclrruntimehost-interface.md)
- [Interfaccia ICLRControl](iclrcontrol-interface.md)
- [Interfacce di hosting](hosting-interfaces.md)
