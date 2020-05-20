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
ms.openlocfilehash: 4390f379e5092cc59d123631f5e6d8da82e2bd7f
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703901"
---
# <a name="iclrruntimeinfobindaslegacyv2runtime-method"></a>Metodo ICLRRuntimeInfo::BindAsLegacyV2Runtime
Associa il runtime corrente per tutte le decisioni relative ai criteri di attivazione della versione 2 di Common Language Runtime legacy (CLR).  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT BindAsLegacyV2Runtime ();  
```  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce i valori HRESULT specifici seguenti:  
  
|HRESULT|Description|  
|-------------|-----------------|  
|S_OK|Associazione riuscita oppure il runtime è già stato associato come runtime legacy dei criteri di attivazione di CLR versione 2.|  
|CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND|Un runtime diverso era già associato ai criteri di attivazione di CLR versione 2 Legacy.|  
  
## <a name="remarks"></a>Osservazioni  
 Se il runtime corrente è già associato a tutte le decisioni relative ai criteri di attivazione di CLR versione 2 (ad esempio, usando l' `useLegacyV2RuntimeActivationPolicy` attributo nell' [ \< elemento> di avvio](../../configure-apps/file-schema/startup/startup-element.md) nel file di configurazione), questo metodo non restituisce un risultato di errore, ma il risultato è S_OK, così come sarebbe se il metodo avesse associato correttamente i criteri di attivazione legacy.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Metahost. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRRuntimeInfo](iclrruntimeinfo-interface.md)
- [Interfacce di hosting](hosting-interfaces.md)
- [Hosting](index.md)
- [\<Elemento> di avvio](../../configure-apps/file-schema/startup/startup-element.md)
