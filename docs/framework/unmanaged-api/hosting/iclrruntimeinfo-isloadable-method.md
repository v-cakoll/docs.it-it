---
title: Metodo ICLRRuntimeInfo::IsLoadable
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1d3825f8dc529cf9c5fbfc44ae70008695e32054
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="iclrruntimeinfoisloadable-method"></a>Metodo ICLRRuntimeInfo::IsLoadable
Indica se il runtime associato a questa interfaccia può essere caricato nel processo corrente, prendendo in considerazione altri runtime che potrebbero essere già stato caricato nel processo.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT IsLoadable(  
        [out, retval] BOOL *pbLoadable);  
```  
  
#### <a name="parameters"></a>Parametri  
 `pbLoadable`  
 [out] `true` se il runtime può essere caricato nel processo corrente; in caso contrario, `false`.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|Metodo completato correttamente.|  
|E_POINTER|`pbLoadable` è null.|  
  
## <a name="remarks"></a>Note  
 Se un altro runtime è già caricato nel processo e il runtime associato a questa interfaccia può essere caricato per l'esecuzione side-by-side in-process, `pbLoadable` restituisce `true`. Se i due runtime non è possibile eseguire side-by-side in-process, `pbLoadable` restituisce `false`. Ad esempio, common language runtime (CLR) versione 4 è possibile eseguire side-by-side nello stesso processo CLR versione 2.0 o CLR versione 1.1. Tuttavia, CLR versione 1.1 e 2.0 di CLR non è possibile eseguire side-by-side in-process.  
  
 Se non sono presenti runtime vengono caricati nel processo, questo metodo restituisce sempre `true`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Metahost. H  
  
 **Libreria:** inclusa come risorsa in MSCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 [Interfacce di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md)
