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
ms.openlocfilehash: 79b62a5e2aad9cfcd14ba40c1abf0342bfe57a4b
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703534"
---
# <a name="iclrmetahostpolicy-interface"></a>Interfaccia ICLRMetaHostPolicy
Fornisce il metodo [GetRequestedRuntime](iclrmetahostpolicy-getrequestedruntime-method.md) , che restituisce un puntatore a un'interfaccia Common Language Runtime (CLR) in base a criteri di criteri, assembly gestito, versione e file di configurazione.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo GetRequestedRuntime](iclrmetahostpolicy-getrequestedruntime-method.md)|Fornisce un'interfaccia CLR preferita in base ai criteri, all'assembly gestito, alla versione e al file di configurazione.|  
  
## <a name="remarks"></a>Osservazioni  
 È possibile ottenere un riferimento a questa interfaccia chiamando la funzione [CLRCreateInstance](clrcreateinstance-function.md) , come illustrato nel codice seguente:  
  
```cpp  
ICLRMetaHostPolicy *pMetaHostPolicy = NULL;  
HRESULT hr = CLRCreateInstance(CLSID_CLRMetaHostPolicy,  
                   IID_ICLRMetaHostPolicy, (LPVOID*)&pMetaHostPolicy);  
```  
  
> [!NOTE]
> Questa interfaccia non carica o attiva il CLR, ma restituisce semplicemente la versione CLR preferita in base alle versioni disponibili installate o caricate.  
  
 L'API di hosting di .NET Framework 4 consolida i criteri in modo che gli host con esigenze specifiche possano usare le funzionalità di base senza incorrere in sanzioni impreviste. Molte delle esportazioni MSCorEE. dll, ad esempio, vengono associate a uno specifico CLR, anche se è possibile che un metodo non lo richieda logicamente. L'enumerazione [METAHOST_POLICY_FLAGS](metahost-policy-flags-enumeration.md) fornisce criteri di associazione comuni alla maggior parte degli host.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Metahost. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di hosting CLR aggiunte in .NET Framework 4 e 4.5](clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)
- [Interfacce di hosting](hosting-interfaces.md)
- [Hosting](index.md)
