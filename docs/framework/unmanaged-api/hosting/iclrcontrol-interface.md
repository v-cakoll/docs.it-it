---
title: Interfaccia ICLRControl
ms.date: 03/30/2017
api_name:
- ICLRControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRControl
helpviewer_keywords:
- ICLRControl interface [.NET Framework hosting]
ms.assetid: a24fd905-1fa6-45a0-ad65-e9e2ee58861e
topic_type:
- apiref
ms.openlocfilehash: 54748fdeaf911591c21f4495335e54c777878f04
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615839"
---
# <a name="iclrcontrol-interface"></a>Interfaccia ICLRControl
Fornisce metodi che consentono a un host di ottenere riferimenti e configurare aspetti di, il Common Language Runtime (CLR).  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo GetCLRManager](iclrcontrol-getclrmanager-method.md)|Ottiene un puntatore a interfaccia a un'istanza di uno dei tipi di gestione che l'host può utilizzare per configurare CLR.|  
|[Metodo SetAppDomainManagerType](iclrcontrol-setappdomainmanagertype-method.md)|Imposta un tipo derivato da <xref:System.AppDomainManager> come tipo per i gestori del dominio dell'applicazione.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRAssemblyIdentityManager](iclrassemblyidentitymanager-interface.md)
- [Interfaccia ICLRDebugManager](iclrdebugmanager-interface.md)
- [Interfaccia ICLRGCManager](iclrgcmanager-interface.md)
- [Interfaccia ICLRHostBindingPolicyManager](iclrhostbindingpolicymanager-interface.md)
- [Interfaccia ICLRHostProtectionManager](iclrhostprotectionmanager-interface.md)
- [Interfaccia ICLROnEventManager](iclroneventmanager-interface.md)
- [Interfaccia ICLRPolicyManager](iclrpolicymanager-interface.md)
- [Interfaccia IHostControl](ihostcontrol-interface.md)
- [Interfacce di hosting](hosting-interfaces.md)
