---
title: Metodo ICLRRuntimeInfo::BindAsLegacyV2Runtime
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.BindAsLegacyV2Runtime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::BindAsLegacyV2Runtime
helpviewer_keywords:
- ICLRRuntimeInfo::BindAsLegacyV2Runtime method [.NET Framework hosting]
- BindAsLegacyV2Runtime method [.NET Framework hosting]
ms.assetid: 65fd55ac-4a24-4479-9384-a2e8013bfb2b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6c85888e9d29e7b3ae6ad76d1e534e08a4603ed2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54499025"
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
|CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND|Un runtime diverso era già associato ai criteri di attivazione 2 versione CLR legacy.|  
  
## <a name="remarks"></a>Note  
 Se il runtime corrente è già associato per tutti i precedenti CLR versione 2 attivazione decisioni relative ai criteri (ad esempio, tramite il `useLegacyV2RuntimeActivationPolicy` attributo la [ \<avvio > elemento](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) nel file di configurazione), questo metodo non restituisce un risultato di errore. al contrario, il risultato è S_OK, semplicemente come lo sarebbe se il metodo ha associato correttamente i criteri di attivazione legacy.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MetaHost.h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [Interfacce di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md)
- [Elemento \<startup](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)
