---
title: Metodo IAssemblyName::SetProperty
ms.date: 03/30/2017
api_name:
- IAssemblyName.SetProperty
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::SetProperty
helpviewer_keywords:
- IAssemblyName::SetProperty method [.NET Framework fusion]
- SetProperty method [.NET Framework fusion]
ms.assetid: 496c3add-f60b-4073-943f-d1bcf33330cb
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ca2d7fe73fc749296f76e18ecce75b7fdd0795d3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54585591"
---
# <a name="iassemblynamesetproperty-method"></a>Metodo IAssemblyName::SetProperty
Imposta il valore della proprietà fa riferimento l'identificatore della proprietà specificata.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT SetProperty (  
    [in] DWORD  PropertyId,  
    [in] LPVOID pvProperty,  
    [in] DWORD  cbProperty  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `PropertyId`  
 [in] Identificatore univoco della proprietà il cui valore verrà impostato.  
  
 `pvProperty`  
 [in] Il valore su cui impostare la proprietà fa `PropertyId`.  
  
 `cbProperty`  
 [in] Le dimensioni, in byte, di `pvProperty`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Fusion. h  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
