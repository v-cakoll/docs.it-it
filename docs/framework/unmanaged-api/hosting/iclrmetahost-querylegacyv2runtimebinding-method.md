---
title: Metodo ICLRMetaHost::QueryLegacyV2RuntimeBinding
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.RequestRuntimeLoadedNotification
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::QueryLegacyV2RuntimeBinding
helpviewer_keywords:
- QueryLegacyV2RuntimeBinding method [.NET Framework hosting]
- ICLRMetaHost::QueryLegacyV2RuntimeBinding method [.NET Framework hosting]
ms.assetid: 9929817e-acc9-40b7-960c-598664e04b60
topic_type:
- apiref
ms.openlocfilehash: b9a51a85bd17e527d4c04b69ca65100a7069607f
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703707"
---
# <a name="iclrmetahostquerylegacyv2runtimebinding-method"></a>Metodo ICLRMetaHost::QueryLegacyV2RuntimeBinding
Restituisce un'interfaccia che rappresenta un runtime a cui sono stati associati i criteri di attivazione legacy, ad esempio usando l' `useLegacyV2RuntimeActivationPolicy` attributo nella voce del file di configurazione dell' [ \< elemento> di avvio](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) , mediante l'uso diretto delle API di attivazione legacy oppure chiamando il metodo [ICLRRuntimeInfo:: BindAsLegacyV2Runtime](iclrruntimeinfo-bindaslegacyv2runtime-method.md) .  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT QueryLegacyV2RuntimeBinding (  
    [in] REFIID riid,  
    [out, iid_is(riid), retval] LPVOID *ppUnk);  
```  
  
## <a name="parameters"></a>Parametri  
 `riid`  
 in Obbligatorio. attualmente l'unico valore valido per questo parametro è `IID_ICLRRuntimeInfo` .  
  
 `ppUnk`  
 [out] Obbligatorio. Quando termina, questo metodo contiene un puntatore all'interfaccia [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) che rappresenta un runtime che è stato associato ai criteri di attivazione legacy.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.  
  
|HRESULT|Description|  
|-------------|-----------------|  
|S_OK|Il metodo ha completato correttamente e restituito un runtime che era associato ai criteri dell'attivazione legacy.|  
|S_FALSE|Il metodo ha completato correttamente, ma un runtime legacy non è stato ancora associato.|  
|E_NOINTERFACE|Il metodo ha trovato un runtime associato ai criteri dell'attivazione legacy, ma `riid` non è supportato da quel runtime.|  
  
## <a name="remarks"></a>Osservazioni  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Metahost. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRMetaHost](iclrmetahost-interface.md)
- [Hosting](index.md)
