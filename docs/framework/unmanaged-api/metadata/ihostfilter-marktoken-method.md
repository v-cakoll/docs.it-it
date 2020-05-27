---
title: Metodo IHostFilter::MarkToken
ms.date: 03/30/2017
api_name:
- IHostFilter.MarkToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostFilter::MarkToken
helpviewer_keywords:
- MarkToken method, IHostFilter interface [.NET Framework metadata]
- IHostFilter::MarkToken method [.NET Framework metadata]
ms.assetid: d7061343-d0a3-4fd5-b312-61974f98bd62
topic_type:
- apiref
ms.openlocfilehash: 11529ce896f265f2b200fa6e511d4b913e9147c8
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008222"
---
# <a name="ihostfiltermarktoken-method"></a>Metodo IHostFilter::MarkToken
Indica che il token di metadati specificato verrà elaborato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT MarkToken (  
    [in]  mdToken         tk  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `tk`  
 in Token di metadati da elaborare.  
  
## <a name="remarks"></a>Commenti  
 In genere, si desidera che un token venga elaborato se è nell'ambito dei metadati. Il `MarkToken` metodo viene passato al motore dei metadati tramite il metodo [IMetaDataEmit::](imetadataemit-sethandler-method.md) SetValue.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in MsCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di metadati](metadata-interfaces.md)
- [Interfaccia IHostFilter](ihostfilter-interface.md)
