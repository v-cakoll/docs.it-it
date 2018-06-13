---
title: Interfaccia ICLRMetaHostPolicy
ms.date: 03/30/2017
api_name:
- ICLRMetaHostPolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHostPolicy
helpviewer_keywords:
- ICLRMetaHostPolicy interface [.NET Framework hosting]
ms.assetid: 1bdeccb6-0698-4c97-ad69-eae2b69e59f1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f9a70cf0812f84908630f109ef06aafa4b4f7525
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33434422"
---
# <a name="iclrmetahostpolicy-interface"></a>Interfaccia ICLRMetaHostPolicy
Fornisce il [GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) metodo, che restituisce un puntatore a un'interfaccia di runtime (CLR) di linguaggio comune in base a criteri di criteri, gestito al file di configurazione, versione e assembly.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)|Fornisce un'interfaccia CLR preferita in base a criteri di criteri, i file di configurazione, versione e assembly gestiti.|  
  
## <a name="remarks"></a>Note  
 È possibile ottenere un riferimento a questa interfaccia chiamando il [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) funzione come illustrato nel codice seguente:  
  
```  
ICLRMetaHostPolicy *pMetaHostPolicy = NULL;  
HRESULT hr = CLRCreateInstance(CLSID_CLRMetaHostPolicy,  
                   IID_ICLRMetaHostPolicy, (LPVOID*)&pMetaHostPolicy);  
```  
  
> [!NOTE]
>  Questa interfaccia non è effettivamente caricare o attivare il CLR, ma restituisce semplicemente la versione CLR preferita in base alle versioni disponibili che sono installate o caricate.  
  
 Il [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] API di hosting consolida i criteri in modo che gli host con esigenze specifiche possono utilizzare le funzionalità di base senza incorrere in problemi imprevisti. Ad esempio, molte delle esportazioni MSCorEE.dll verrà associato a un CLR specifico, anche se un metodo potrebbe non richiederlo. Il [METAHOST_POLICY_FLAGS](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md) enumerazione fornisce criteri di associazione che sono comuni alla maggior parte degli host.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Metahost. H  
  
 **Libreria:** inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfacce di hosting CLR aggiunte in .NET Framework 4 e 4.5](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)  
 [Interfacce di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md)
