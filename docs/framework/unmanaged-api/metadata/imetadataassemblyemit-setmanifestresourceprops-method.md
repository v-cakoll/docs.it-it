---
title: Metodo IMetaDataAssemblyEmit::SetManifestResourceProps
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.SetManifestResourceProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::SetManifestResourceProps
helpviewer_keywords:
- SetManifestResourceProps method [.NET Framework metadata]
- IMetaDataAssemblyEmit::SetManifestResourceProps method [.NET Framework metadata]
ms.assetid: ef77efd1-849c-4e51-ba92-7ee3d2bf0339
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2d3dabd48ed63a023e830e1c2b8c983ef3af4519
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57481713"
---
# <a name="imetadataassemblyemitsetmanifestresourceprops-method"></a>Metodo IMetaDataAssemblyEmit::SetManifestResourceProps
Modifica la struttura dei metadati `ManifestResource` specificata.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT SetManifestResourceProps (  
    [in] mdManifestResource  mr,  
    [in] mdToken             tkImplementation,   
    [in] DWORD               dwOffset,  
    [in] DWORD               dwResourceFlags  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `mr`  
 [in] Il token che specifica il `ManifestResource` modifica della struttura dei metadati.  
  
 `tkImplementation`  
 [in] Il token, di tipo `File` o `AssemblyRef`, che esegue il mapping al provider di risorse.  
  
 `dwOffset`  
 [in] L'offset all'inizio della risorsa all'interno del file.  
  
 `dwResourceFlags`  
 [in] Combinazione bit per bit dei valori di flag che specificano gli attributi della risorsa.  
  
## <a name="remarks"></a>Note  
 Per creare un `ManifestResource` struttura dei metadati, usare il [DefineManifestResource](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md) (metodo).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
