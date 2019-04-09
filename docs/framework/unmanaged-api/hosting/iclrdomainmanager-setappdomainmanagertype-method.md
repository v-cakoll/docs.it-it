---
title: Metodo ICLRDomainManager::SetAppDomainManagerType
ms.date: 03/30/2017
api_name:
- ICLRDomainManager.SetAppDomainManagerType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDomainManager::SetAppDomainManagerType
helpviewer_keywords:
- SetAppDomainManagerType method, ICLRDomainManager interface [.NET Framework hosting]
- ICLRDomainManager::SetAppDomainManagerType method [.NET Framework hosting]
ms.assetid: ee91abb0-cb74-41dd-927b-e117fb8ffdf4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6cfef7d929d40996716a02a4db51630827011a68
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59183248"
---
# <a name="iclrdomainmanagersetappdomainmanagertype-method"></a>Metodo ICLRDomainManager::SetAppDomainManagerType
Specifica il tipo, derivato dal <xref:System.AppDomainManager?displayProperty=nameWithType> (classe), l'applicazione del gestore del dominio che verrà usato per inizializzare il dominio applicazione predefinito.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT SetAppDomainManagerType(  
    [in] LPCWSTR wszAppDomainManagerAssembly,  
    [in] LPCWSTR wszAppDomainManagerType,  
    [in] EInitializeNewDomainFlags dwInitializeDomainFlags  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `wszAppDomainManagerAssembly`  
 [in] Il nome visualizzato dell'assembly che contiene il tipo di gestione del dominio applicazione; Per esempio: "AdMgrExample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6856bccf150f00b3".  
  
 `wszAppDomainManagerType`  
 [in] Il nome del tipo del gestore di dominio dell'applicazione, incluso lo spazio dei nomi.  
  
 `dwInitializeDomainFlags`  
 [in] Una combinazione di [EInitializeNewDomainFlags](../../../../docs/framework/unmanaged-api/hosting/einitializenewdomainflags-enumeration.md) valori di enumerazione che forniscono informazioni sulla gestione dominio applicazione.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|Metodo completato correttamente.|  
|HOST_E_CLRNOTAVAILABLE|Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.|  
  
## <a name="remarks"></a>Note  
 Attualmente, l'unico valore definito per `dwInitializeDomainFlags` viene `eInitializeNewDomainFlags_NoSecurityChanges`, indicherà che il gestore del dominio applicazione non modifica le impostazioni di sicurezza durante l'esecuzione di common language runtime (CLR) di <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> (metodo). In questo modo Common Language Runtime ottimizzare il caricamento degli assembly con il parametro condizionale <xref:System.Security.AllowPartiallyTrustedCallersAttribute> attributo (APTCA). Se la chiusura transitiva di questo set di assembly è grande, ciò può comportare un miglioramento significativo nel tempo di avvio.  
  
> [!IMPORTANT]
>  Se l'host specifica `eInitializeNewDomainFlags_NoSecurityChanges` per il gestore del dominio dell'applicazione, un <xref:System.InvalidOperationException> viene generata un'eccezione se viene eseguito un tentativo di modificare la sicurezza del dominio dell'applicazione.  
  
 Chiama il [ICLRControl](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)metodo è equivalente alla chiamata `ICLRDomainManager::SetAppDomainManagerType` con `eInitializeNewDomainFlags_None`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MetaHost.h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md)
- [Interfaccia ICLRDomainManager](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-interface.md)
- [Enumerazione EInitializeNewDomainFlags](../../../../docs/framework/unmanaged-api/hosting/einitializenewdomainflags-enumeration.md)
