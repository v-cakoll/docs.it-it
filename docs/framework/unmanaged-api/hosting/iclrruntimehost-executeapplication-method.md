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
ms.openlocfilehash: 924d032c42dca95b253acea167d55dd6e2b811e5
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703331"
---
# <a name="iclrruntimehostexecuteapplication-method"></a>Metodo ICLRRuntimeHost::ExecuteApplication
Utilizzato negli scenari di distribuzione ClickOnce basati su manifesto per specificare l'applicazione da attivare in un nuovo dominio. Per ulteriori informazioni su questi scenari, vedere [sicurezza e distribuzione di ClickOnce](/visualstudio/deployment/clickonce-security-and-deployment).  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
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
 in Nome completo dell'applicazione, come definito per <xref:System.ApplicationIdentity> .  
  
 `dwManifestPaths`  
 in Numero di stringhe contenute nella `ppwzManifestPaths` matrice.  
  
 `ppwzManifestPaths`  
 [in] Facoltativo. Matrice di stringhe che contiene i percorsi dei manifesti per l'applicazione.  
  
 `dwActivationData`  
 in Numero di stringhe contenute nella `ppwzActivationData` matrice.  
  
 `ppwzActivationData`  
 [in] Facoltativo. Matrice di stringhe che contiene i dati di attivazione dell'applicazione, ad esempio la parte della stringa di query dell'URL per le applicazioni distribuite sul Web.  
  
 `pReturnValue`  
 out Valore restituito dal punto di ingresso dell'applicazione.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Description|  
|-------------|-----------------|  
|S_OK|`ExecuteApplication`la restituzione è riuscita.|  
|HOST_E_CLRNOTAVAILABLE|Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non è il proprietario del blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Se un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Osservazioni  
 `ExecuteApplication`viene usato per attivare le applicazioni ClickOnce in un dominio applicazione appena creato.  
  
 Il `pReturnValue` parametro di output viene impostato sul valore restituito dall'applicazione. Se si fornisce un valore null per, non ha `pReturnValue` `ExecuteApplication` esito negativo, ma non restituisce alcun valore.  
  
> [!IMPORTANT]
> Non chiamare il metodo [Start](iclrruntimehost-start-method.md) del metodo prima di chiamare il `ExecuteApplication` metodo per attivare un'applicazione basata su manifesto. Se il `Start` metodo viene chiamato per primo, la `ExecuteApplication` chiamata al metodo avrà esito negativo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ActivationContext>
- <xref:System.AppDomainManager>
- <xref:System.ApplicationIdentity>
- [Interfaccia ICLRRuntimeHost](iclrruntimehost-interface.md)
- [Metodo SetAppDomainManager](ihostcontrol-setappdomainmanager-method.md)
- [Procedura dettagliata: download di assembly su richiesta con l'API della distribuzione ClickOnce tramite la finestra di progettazione](/visualstudio/deployment/walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api-using-the-designer)
