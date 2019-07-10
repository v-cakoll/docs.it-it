---
title: Funzione ClrCreateManagedInstance
ms.date: 03/30/2017
api_name:
- ClrCreateManagedInstance
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- ClrCreateManagedInstance
helpviewer_keywords:
- ClrCreateManagedInstance function [.NET Framework hosting]
ms.assetid: 58ba42c0-4857-43bf-a039-73a4dc6544c2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e1ae530b8488dcd375e91058a227316dd38cf4ab
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779166"
---
# <a name="clrcreatemanagedinstance-function"></a>Funzione ClrCreateManagedInstance
Crea un'istanza del tipo gestito specificato.  
  
 Questa funzione è stata deprecata in .NET Framework 4. Utilizzare l'attivazione di COM per creare un'istanza del tipo gestito o utilizzare l'hosting (vedere [CLR Hosting interfacce aggiunte in .NET Framework 4 e 4.5](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)).  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
STDAPI ClrCreateManagedInstance (  
    [in]  LPCWSTR  pTypeName,   
    [in]  REFIID   riid,   
    [out] void     **ppObject  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pTypeName`  
 [in] Un puntatore al nome del tipo di istanza richiesto.  
  
 `riid`  
 [in] Il `IID` del tipo di istanza richiesto.  
  
 `ppObject`  
 [out] Un puntatore a un puntatore a un'istanza del tipo gestito che è stata richiesta dal chiamante.  
  
## <a name="remarks"></a>Note  
 Common language runtime deve già essere caricato in un processo. Ad esempio, possono essere caricato tramite una chiamata ai [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) funzionare prima il `ClrCreateManagedInstance` funzione viene chiamata. Se il runtime non viene caricato, `ClrCreateManagedInstance` innanzitutto tenta di caricare v1.0.3705 del runtime. Se il problema persiste, tenta di caricare la versione più recente del runtime.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE.h  
  
 **Libreria:** MSCorEE.dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Funzioni di hosting CLR deprecate](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
- [Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md)
