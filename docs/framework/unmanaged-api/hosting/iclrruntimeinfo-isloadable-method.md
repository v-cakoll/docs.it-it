---
title: Metodo ICLRRuntimeInfo::IsLoadable
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.IsLoadable
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::IsLoadable
helpviewer_keywords:
- IsLoadable method [.NET Framework hosting]
- ICLRRuntimeInfo::IsLoadable method [.NET Framework hosting]
ms.assetid: 205ca53b-e78e-49b2-9a46-2a7823e96b8c
topic_type:
- apiref
ms.openlocfilehash: 9339bb974c261e62502c760dfaf45651573cbe1a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136367"
---
# <a name="iclrruntimeinfoisloadable-method"></a>Metodo ICLRRuntimeInfo::IsLoadable
Indica se il runtime associato a questa interfaccia può essere caricato nel processo corrente, tenendo conto di altri runtime che potrebbero essere già stati caricati nel processo.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT IsLoadable(  
        [out, retval] BOOL *pbLoadable);  
```  
  
## <a name="parameters"></a>Parametri  
 `pbLoadable`  
 [out] `true` se il runtime può essere caricato nel processo corrente; in caso contrario, `false`.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|Metodo completato correttamente.|  
|E_POINTER|`pbLoadable` è null.|  
  
## <a name="remarks"></a>Note  
 Se un altro runtime è già caricato nel processo e il runtime associato a questa interfaccia può essere caricato per l'esecuzione side-by-side in-process, `pbLoadable` restituisce `true`. Se i due runtime non possono essere eseguiti side-by-side in-process, `pbLoadable` restituisce `false`. Ad esempio, il Common Language Runtime (CLR) versione 4 può essere eseguito side-by-side nello stesso processo con CLR versione 2,0 o CLR versione 1,1. Tuttavia, la versione CLR 1,1 e la versione 2,0 CLR non possono essere eseguite side-by-side in-process.  
  
 Se nel processo non sono stati caricati Runtime, questo metodo restituisce sempre `true`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Metahost. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [Interfacce di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md)
