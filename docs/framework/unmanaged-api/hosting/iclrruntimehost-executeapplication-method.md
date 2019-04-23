---
title: Metodo ICLRRuntimeHost::ExecuteApplication
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.ExecuteApplication
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::ExecuteApplication
helpviewer_keywords:
- ICLRRuntimeHost::ExecuteApplication method [.NET Framework hosting]
- ExecuteApplication method [.NET Framework hosting]
ms.assetid: 5f28cc4e-7176-4e00-aa1f-58ae6ee52fe4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8ce7e9ff4041abd1e89330bd3a565b755875d3b2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59194227"
---
# <a name="iclrruntimehostexecuteapplication-method"></a>Metodo ICLRRuntimeHost::ExecuteApplication
Usato negli scenari di distribuzione ClickOnce basata su manifesto per specificare l'applicazione da attivare in un nuovo dominio. Per altre informazioni su questi scenari, vedere [ClickOnce Security and Deployment](/visualstudio/deployment/clickonce-security-and-deployment).  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT ExecuteApplication(  
    [in] LPCWSTR   pwzAppFullName,  
    [in] DWORD     dwManifestPaths,  
    [in] LPCWSTR   *ppwzManifestPaths,  
    [in] DWORD     dwActivationData,  
    [in] LPCWSTR   *ppwzActivationData,  
    [out] int      *pReturnValue  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pwzAppFullName`  
 [in] Il nome completo dell'applicazione, come definito per <xref:System.ApplicationIdentity>.  
  
 `dwManifestPaths`  
 [in] Il numero di stringhe contenute nel `ppwzManifestPaths` matrice.  
  
 `ppwzManifestPaths`  
 [in] Facoltativo. Matrice di stringhe che contiene i percorsi di manifesto dell'applicazione.  
  
 `dwActivationData`  
 [in] Il numero di stringhe contenute nel `ppwzActivationData` matrice.  
  
 `ppwzActivationData`  
 [in] Facoltativo. Matrice di stringhe che contiene i dati di attivazione dell'applicazione, ad esempio la parte della stringa di query dell'URL per le applicazioni distribuite sul Web.  
  
 `pReturnValue`  
 [out] Il valore restituito dal punto di ingresso dell'applicazione.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|`ExecuteApplication` stato restituito correttamente.|  
|HOST_E_CLRNOTAVAILABLE|Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non possiede il blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Se un metodo viene restituito E_FAIL, CLR non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Note  
 `ExecuteApplication` Consente di attivare le applicazioni ClickOnce in un dominio applicazione appena creata.  
  
 Il `pReturnValue` parametro di output è impostato sul valore restituito dall'applicazione. Se si specifica un valore null per `pReturnValue`, `ExecuteApplication` ha esito positivo, ma non restituisce un valore.  
  
> [!IMPORTANT]
>  Non si chiama il [metodo Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) metodo prima di chiamare il `ExecuteApplication` metodo per attivare un'applicazione basata su manifesto. Se il `Start` viene chiamato prima di tutto la `ExecuteApplication` chiamata al metodo avrà esito negativo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE.h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ActivationContext>
- <xref:System.AppDomainManager>
- <xref:System.ApplicationIdentity>
- [Interfaccia ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
- [Metodo SetAppDomainManager](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-setappdomainmanager-method.md)
- [Procedura dettagliata: Download di assembly su richiesta con l'API della distribuzione ClickOnce tramite la finestra di progettazione](/visualstudio/deployment/walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api-using-the-designer)
