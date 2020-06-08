---
title: Metodo IMetaDataImport2::GetGenericParamConstraintProps
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.GetGenericParamConstraintProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::GetGenericParamConstraintProps
helpviewer_keywords:
- IMetaDataImport2::GetGenericParamConstraintProps method [.NET Framework metadata]
- GetGenericParamConstraintProps method [.NET Framework metadata]
ms.assetid: c5fee4a0-b132-4e5e-8730-e586ce314b9a
topic_type:
- apiref
ms.openlocfilehash: 8a1cdff313dae73e3f5e8918ff2ef395c80b115d
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84490627"
---
# <a name="imetadataimport2getgenericparamconstraintprops-method"></a>Metodo IMetaDataImport2::GetGenericParamConstraintProps
Ottiene i metadati associati al vincolo del parametro generico rappresentato dal token di vincolo specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetGenericParamConstraintProps (  
   [in]  mdGenericParamConstraint  gpc,  
   [out] mdGenericParam            *ptGenericParam,  
   [out] mdToken                   *ptkConstraintType  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `gpc`  
 in Token per il vincolo di parametro generico per il quale restituire i metadati.  
  
 `ptGenericParam`  
 out Puntatore al token che rappresenta il parametro generico che è vincolato.  
  
 `ptkConstraintType`  
 out Puntatore a un token TypeDef, TypeRef o TypeSpec che rappresenta un vincolo in `ptGenericParam` .  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in MsCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataImport2](imetadataimport2-interface.md)
- [Interfaccia IMetaDataImport](imetadataimport-interface.md)
