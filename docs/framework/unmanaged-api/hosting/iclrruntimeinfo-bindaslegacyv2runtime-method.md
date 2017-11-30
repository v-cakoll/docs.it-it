---
title: Metodo ICLRRuntimeInfo::BindAsLegacyV2Runtime
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeInfo.BindAsLegacyV2Runtime
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRRuntimeInfo::BindAsLegacyV2Runtime
helpviewer_keywords:
- ICLRRuntimeInfo::BindAsLegacyV2Runtime method [.NET Framework hosting]
- BindAsLegacyV2Runtime method [.NET Framework hosting]
ms.assetid: 65fd55ac-4a24-4479-9384-a2e8013bfb2b
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 229c5483c02357054f3d2821d8e024c78887e839
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="iclrruntimeinfobindaslegacyv2runtime-method"></a>Metodo ICLRRuntimeInfo::BindAsLegacyV2Runtime
Associa il runtime corrente per tutti i legacy common language runtime (CLR) versione 2 attivazione decisioni relative ai criteri.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT BindAsLegacyV2Runtime ();  
```  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce gli HRESULT specifici seguenti:  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|L'associazione ha avuto esito positivo o questo runtime già associato come il runtime criteri 2 attivazione della versione CLR legacy.|  
|CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND|Un runtime diverso è già associato ai criteri di attivazione 2 versione CLR legacy.|  
  
## <a name="remarks"></a>Note  
 Se il runtime corrente è già associato per tutti i precedenti CLR versione 2 attivazione decisioni relative ai criteri (ad esempio, tramite il `useLegacyV2RuntimeActivationPolicy` attributo la [ \<avvio > elemento](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) nel file di configurazione), questo metodo non restituisce un risultato di errore. al contrario, il risultato è S_OK, così come lo sarebbe se il metodo avesse associato correttamente i criteri di attivazione legacy.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Metahost. H  
  
 **Libreria:** inclusa come risorsa in MSCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [ICLRRuntimeInfo (interfaccia)](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 [Interfacce di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md)  
 [\<avvio > elemento](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)
