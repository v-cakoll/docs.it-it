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
ms.openlocfilehash: 7fbe0cf3e93d75749fa3f463f3f97dbd1bfe27a0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176539"
---
# <a name="clrcreatemanagedinstance-function"></a>Funzione ClrCreateManagedInstance
Crea un'istanza del tipo gestito specificato.  
  
 Questa funzione è stata deprecata in .NET Framework 4. Utilizzare l'attivazione COM per creare un'istanza del tipo gestito oppure utilizzare l'hosting (vedere Interfacce di [hosting CLR aggiunte in .NET Framework 4 e 4.5).](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)  
  
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
 [in] Puntatore al nome del tipo di istanza richiesto.  
  
 `riid`  
 [in] Oggetto `IID` del tipo di istanza richiesto.  
  
 `ppObject`  
 [fuori] Puntatore a un puntatore a un'istanza del tipo gestito richiesto dal chiamante.  
  
## <a name="remarks"></a>Osservazioni  
 Common Language Runtime deve essere già caricato in un processo. Ad esempio, può essere caricato utilizzando una chiamata alla funzione `ClrCreateManagedInstance` [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) prima che venga chiamata la funzione. Se il runtime non `ClrCreateManagedInstance` viene caricato, si tenta innanzitutto di caricare v1.0.3705 del runtime. Se l'operazione non riesce, tenta di caricare la versione più recente del runtime.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE.h  
  
 **Biblioteca:** Mscoree  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Funzioni di hosting CLR deprecate](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
- [Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md)
