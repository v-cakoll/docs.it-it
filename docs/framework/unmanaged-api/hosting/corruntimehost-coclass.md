---
title: Coclasse CorRuntimeHost
ms.date: 03/30/2017
api_name:
- CorRuntimeHost Coclass
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorRuntimeHost
helpviewer_keywords:
- CoRuntimeHost coclass [.NET Framework hosting]
ms.assetid: 5833740b-7d67-44b4-865c-b5bf45e291e3
topic_type:
- apiref
ms.openlocfilehash: 512009e053605e2018f1fcbafa422c1a36ddecc1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136901"
---
# <a name="corruntimehost-coclass"></a>Coclasse CorRuntimeHost
Fornisce interfacce per la gestione delle applicazioni eseguite dal Common Language Runtime.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
coclass CorRuntimeHost {  
    [default] interface ICorRuntimeHost;  
    interface IGCHost;  
    interface ICorConfiguration;  
    interface IValidator;  
    interface IDebuggerInfo;  
};  
```  
  
## <a name="interfaces"></a>Interfacce  
  
|Interfaccia|Descrizione|  
|---------------|-----------------|  
|[Interfaccia ICorConfiguration](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)|Fornisce metodi per la configurazione del Common Language Runtime (CLR).|  
|[Interfaccia ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)|Fornisce metodi che consentono all'host di avviare e arrestare il Common Language Runtime in modo esplicito, di creare e configurare i domini applicazione, di accedere al dominio predefinito e di enumerare tutti i domini in esecuzione nel processo.|  
|[Interfaccia IDebuggerInfo](../../../../docs/framework/unmanaged-api/hosting/idebuggerinfo-interface.md)|Fornisce metodi per ottenere informazioni sullo stato dei servizi di debug.|  
|[Interfaccia IGCHost](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)|Fornisce metodi per ottenere informazioni sul sistema Garbage Collection e per controllare alcuni aspetti di Garbage Collection.|  
|IValidator|Fornisce metodi per la convalida di immagini eseguibili portabili e report dettagliati degli errori di convalida.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. idl  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Coclassi di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)
