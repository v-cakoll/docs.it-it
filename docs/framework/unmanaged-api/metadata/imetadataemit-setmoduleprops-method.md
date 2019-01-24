---
title: Metodo IMetaDataEmit::SetModuleProps
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetModuleProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetModuleProps
helpviewer_keywords:
- SetModuleProps method [.NET Framework metadata]
- IMetaDataEmit::SetModuleProps method [.NET Framework metadata]
ms.assetid: b74d7629-5f46-458f-8d67-2456a1e7030c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 86cb99023c0abfc70d292427b14986dbcea1d333
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54586163"
---
# <a name="imetadataemitsetmoduleprops-method"></a>Metodo IMetaDataEmit::SetModuleProps
Aggiorna i riferimenti a un modulo definito da una chiamata precedente a [DefineModuleRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md).  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT SetModuleProps (   
    [in]  LPCWSTR     szName  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `szName`  
 [in] Il nome del modulo in formato Unicode. Si tratta solo il nome del file e non il nome e percorso completo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [Interfaccia IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
