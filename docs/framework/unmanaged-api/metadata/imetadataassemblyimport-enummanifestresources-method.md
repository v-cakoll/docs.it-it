---
title: Metodo IMetaDataAssemblyImport::EnumManifestResources
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.EnumManifestResources
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::EnumManifestResources
helpviewer_keywords:
- IMetaDataAssemblyImport::EnumManifestResources method [.NET Framework metadata]
- EnumManifestResources method [.NET Framework metadata]
ms.assetid: 9543b111-5705-40c9-935c-a3ffc7a581aa
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7abcb7b69d0f0f2c53cd236c9b4092a94e0f421c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59110677"
---
# <a name="imetadataassemblyimportenummanifestresources-method"></a>Metodo IMetaDataAssemblyImport::EnumManifestResources
Ottiene un puntatore a un enumeratore per le risorse a cui fa riferimento il manifesto dell'assembly corrente.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT EnumManifestResources (  
    [in, out] HCORENUM         *phEnum,   
    [out] mdManifestResource   rManifestResources[],   
    [in]  ULONG                cMax,   
    [out] ULONG                *pcTokens  
);   
```  
  
## <a name="parameters"></a>Parametri  
 `phEnum`  
 [in, out] Un puntatore all'enumeratore. Deve trattarsi di un valore null valore quando il `EnumManifestResources` viene chiamato per la prima volta.  
  
 `rManifestResources`  
 [out] La matrice utilizzata per archiviare il `mdManifestResource` i token di metadati.  
  
 `cMax`  
 [in] Il numero massimo di `mdManifestResource` i token che possono essere inseriti in `rManifestResources`.  
  
 `pcTokens`  
 [out] I numerosi `mdManifestResource` token effettivamente posizionati nella `rManifestResources`.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|`S_OK`|`EnumManifestResources` stato restituito correttamente.|  
|`S_FALSE`|Non sono presenti token da enumerare. In questo caso, `pcTokens` è impostato su zero.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
