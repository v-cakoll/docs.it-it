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
ms.openlocfilehash: 89b3f9f248a445cc0568236d6a1df14269de4187
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615696"
---
# <a name="iclrdomainmanagersetappdomainmanagertype-method"></a>Metodo ICLRDomainManager::SetAppDomainManagerType
Specifica il tipo, derivato dalla <xref:System.AppDomainManager?displayProperty=nameWithType> classe, del gestore del dominio dell'applicazione che verrà usato per inizializzare il dominio applicazione predefinito.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT SetAppDomainManagerType(  
    [in] LPCWSTR wszAppDomainManagerAssembly,  
    [in] LPCWSTR wszAppDomainManagerType,  
    [in] EInitializeNewDomainFlags dwInitializeDomainFlags  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `wszAppDomainManagerAssembly`  
 in Nome visualizzato dell'assembly che contiene il tipo di gestore di dominio dell'applicazione. ad esempio: "AdMgrExample, Version = 1.0.0.0, Culture = neutral, PublicKeyToken = 6856bccf150f00b3".  
  
 `wszAppDomainManagerType`  
 in Nome del tipo del gestore di dominio dell'applicazione, incluso lo spazio dei nomi.  
  
 `dwInitializeDomainFlags`  
 in Combinazione di valori di enumerazione [EInitializeNewDomainFlags](einitializenewdomainflags-enumeration.md) che forniscono informazioni sul gestore del dominio dell'applicazione.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.  
  
|HRESULT|Description|  
|-------------|-----------------|  
|S_OK|Metodo completato correttamente.|  
|HOST_E_CLRNOTAVAILABLE|Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.|  
  
## <a name="remarks"></a>Osservazioni  
 Attualmente, l'unico valore definito per `dwInitializeDomainFlags` è `eInitializeNewDomainFlags_NoSecurityChanges` , che indica al Common Language Runtime (CLR) che il gestore del dominio dell'applicazione non modificherà le impostazioni di sicurezza durante l'esecuzione del <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> metodo. Questo consente a CLR di ottimizzare il caricamento di assembly con l'attributo condizionale <xref:System.Security.AllowPartiallyTrustedCallersAttribute> (APTCA). Questo può comportare un miglioramento significativo del tempo di avvio se la chiusura transitiva di questo set di assembly è grande.  
  
> [!IMPORTANT]
> Se l'host specifica `eInitializeNewDomainFlags_NoSecurityChanges` per il gestore di dominio dell'applicazione, <xref:System.InvalidOperationException> viene generata un'eccezione se viene effettuato un tentativo di modificare la sicurezza del dominio dell'applicazione.  
  
 La chiamata al metodo [ICLRControl:: SetAppDomainManagerType](iclrcontrol-setappdomainmanagertype-method.md)equivale alla chiamata `ICLRDomainManager::SetAppDomainManagerType` con `eInitializeNewDomainFlags_None` .  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Metahost. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Hosting](index.md)
- [Interfaccia ICLRDomainManager](iclrdomainmanager-interface.md)
- [Enumerazione EInitializeNewDomainFlags](einitializenewdomainflags-enumeration.md)
