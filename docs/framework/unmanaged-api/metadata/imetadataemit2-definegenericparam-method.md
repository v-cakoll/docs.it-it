---
title: Metodo IMetaDataEmit2::DefineGenericParam
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.DefineGenericParam
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::DefineGenericParam
helpviewer_keywords:
- IMetaDataEmit2::DefineGenericParam method [.NET Framework metadata]
- DefineGenericParam method [.NET Framework metadata]
ms.assetid: 47b2a3b6-907d-43dc-858d-1ae7dca1316a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 027547098edefdca71317b8f885e71f468dc6e77
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777195"
---
# <a name="imetadataemit2definegenericparam-method"></a>Metodo IMetaDataEmit2::DefineGenericParam
Crea una definizione per un parametro di tipo generico e ottiene un token per tale parametro di tipo generico.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT DefineGenericParam (   
    [in]  mdToken         tk,   
    [in]  ULONG           ulParamSeq,   
    [in]  DWORD           dwParamFlags,   
    [in]  LPCWSTR         szname,   
    [in]  DWORD           reserved,   
    [in]  mdToken         rtkConstraints[],   
    [out] mdGenericParam  *pgp  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `tk`  
 [in] Un' `mdTypeDef` o `mdMethodDef` token che rappresenta il metodo o costruttore per cui si desidera definire un parametro generico.  
  
 `ulParamSeq`  
 [in] L'indice del parametro generico.  
  
 `dwParamFlags`  
 [in] Valore di [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) enumerazione che descrive il tipo parametro generico.  
  
 `szname`  
 [in] Il nome del parametro.  
  
 `reserved`  
 [in] Questo parametro è riservato per un'estendibilità futura.  
  
 `rtkConstraints`  
 [in] Una matrice con terminazione zero di vincoli di tipo. I membri della matrice devono essere un' `mdTypeDef`, `mdTypeRef`, o `mdTypeSpec` token di metadati.  
  
 `pgp`  
 [out] Un token che rappresenta il parametro generico.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [Interfaccia IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
