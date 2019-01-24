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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a4a1761f088732cf19d55f42d66288bb281885f1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54589451"
---
# <a name="ihostfiltermarktoken-method"></a>Metodo IHostFilter::MarkToken
Indica che il token di metadati specificato verrà elaborato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT MarkToken (  
    [in]  mdToken         tk  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `tk`  
 [in] Il token di metadati da elaborare.  
  
## <a name="remarks"></a>Note  
 In genere, si vuole che un token per l'elaborazione se presente nell'ambito dei metadati. Il `MarkToken` viene passato al motore di metadati tramite il [SetHandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) (metodo).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Interfacce di metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [Interfaccia IHostFilter](../../../../docs/framework/unmanaged-api/metadata/ihostfilter-interface.md)
