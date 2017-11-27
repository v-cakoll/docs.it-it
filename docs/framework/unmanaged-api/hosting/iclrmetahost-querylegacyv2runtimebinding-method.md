---
title: Metodo ICLRMetaHost::QueryLegacyV2RuntimeBinding
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRMetaHost.RequestRuntimeLoadedNotification
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRMetaHost::QueryLegacyV2RuntimeBinding
helpviewer_keywords:
- QueryLegacyV2RuntimeBinding method [.NET Framework hosting]
- ICLRMetaHost::QueryLegacyV2RuntimeBinding method [.NET Framework hosting]
ms.assetid: 9929817e-acc9-40b7-960c-598664e04b60
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c273a1690828e37c8f7fcf5071e42e5bb2c58228
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="iclrmetahostquerylegacyv2runtimebinding-method"></a>Metodo ICLRMetaHost::QueryLegacyV2RuntimeBinding
Restituisce un'interfaccia che rappresenta un runtime a cui sono stati associati i criteri di attivazione legacy, ad esempio, tramite il `useLegacyV2RuntimeActivationPolicy` attributo la [ \<avvio > elemento](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) voce file di configurazione mediante l'utilizzo diretto l'API di attivazione legacy o chiamando il [ICLRRuntimeInfo:: Bindaslegacyv2runtime](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-bindaslegacyv2runtime-method.md) metodo.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT QueryLegacyV2RuntimeBinding (  
    [in] REFIID riid,  
    [out, iid_is(riid), retval] LPVOID *ppUnk);  
```  
  
#### <a name="parameters"></a>Parametri  
 `riid`  
 [in] L'unico valore valido per questo parametro è Required.Currently `IID_ICLRRuntimeInfo`.  
  
 `ppUnk`  
 [out] Obbligatorio. Quando termina, questo metodo contiene un puntatore per il [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interfaccia che rappresenta un runtime che è stato associato ai criteri dell'attivazione legacy.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|Il metodo ha completato correttamente e restituito un runtime che era associato ai criteri dell'attivazione legacy.|  
|S_FALSE|Il metodo ha completato correttamente, ma un runtime legacy non è stato ancora associato.|  
|E_NOINTERFACE|Il metodo ha trovato un runtime associato ai criteri dell'attivazione legacy, ma `riid` non è supportato da quel runtime.|  
  
## <a name="remarks"></a>Note  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Metahost. H  
  
 **Libreria:** inclusa come risorsa in MSCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [ICLRMetaHost (interfaccia)](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)  
 [Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md)
