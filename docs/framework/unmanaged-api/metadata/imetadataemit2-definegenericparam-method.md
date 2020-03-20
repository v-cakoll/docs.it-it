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
ms.openlocfilehash: 1868d13a9dbb73dbdf64e49c395bdbff02ce89d4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177447"
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
 [in] Un `mdTypeDef` `mdMethodDef` o token che rappresenta il metodo o il costruttore per il quale definire un parametro generico.  
  
 `ulParamSeq`  
 [in] Indice del parametro generico.  
  
 `dwParamFlags`  
 [in] Valore dell'enumerazione [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) che descrive il tipo per il parametro generico.  
  
 `szname`  
 [in] Nome del parametro.  
  
 `reserved`  
 [in] Questo parametro è riservato per l'estensibilità futura.  
  
 `rtkConstraints`  
 [in] Matrice con terminazione zero di vincoli di tipo. I membri della `mdTypeDef` `mdTypeRef`matrice `mdTypeSpec` devono essere un token , o di metadati.  
  
 `pgp`  
 [fuori] Token che rappresenta il parametro generico.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor.h  
  
 **Biblioteca:** Utilizzato come risorsa in MsCorEE.dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [Interfaccia IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
