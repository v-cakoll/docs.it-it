---
title: Metodo IMetaDataEmit::DeletePinvokeMap
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DeletePinvokeMap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DeletePinvokeMap
helpviewer_keywords:
- IMetaDataEmit::DeletePinvokeMap method [.NET Framework metadata]
- DeletePinvokeMap method [.NET Framework metadata]
ms.assetid: 3c4f6b54-5ce7-4a2a-83e1-6dec16441f50
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 64ba852c4bb0ae7b0119876fca4a4b2a107ed934
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777414"
---
# <a name="imetadataemitdeletepinvokemap-method"></a>Metodo IMetaDataEmit::DeletePinvokeMap
Elimina i metadati di mapping PInvoke per l'oggetto fa riferimento il token specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT DeletePinvokeMap (   
    [in]  mdToken     tk   
);  
```  
  
## <a name="parameters"></a>Parametri  
 `tk`  
 [in] Un' `mdFieldDef` o `mdMethodDef` token che rappresenta l'oggetto per cui si desidera eliminare i metadati di mapping di PInvoke.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [Interfaccia IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
