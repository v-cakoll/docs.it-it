---
title: Metodo IMetaDataImport2::EnumGenericParamConstraints
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.EnumGenericParamConstraints
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::EnumGenericParamConstraints
helpviewer_keywords:
- EnumGenericParamConstraints method [.NET Framework metadata]
- IMetaDataImport2::EnumGenericParamConstraints method [.NET Framework metadata]
ms.assetid: 8a7d4e40-28fe-4e14-b801-4049880130e7
topic_type:
- apiref
ms.openlocfilehash: af226f9317b67b23e03d06614ed5b9c956939c22
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503419"
---
# <a name="imetadataimport2enumgenericparamconstraints-method"></a>Metodo IMetaDataImport2::EnumGenericParamConstraints
Ottiene un enumeratore per una matrice di vincoli di parametri generici associati al parametro generico rappresentato dal token specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT EnumGenericParamConstraints (  
    [in, out] HCORENUM                *phEnum,  
    [in]  mdGenericParam              tk,  
    [out] mdGenericParamConstraint    rGenericParamConstraints[],  
    [in]  ULONG                       cMax,  
    [out] ULONG                       *pcGenericParamConstraints  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `phEnum`  
 [in, out] Puntatore all'enumeratore.  
  
 `tk`  
 in   Token che rappresenta il parametro generico i cui vincoli devono essere enumerati.  
  
 `rGenericParamConstraints`  
 out Matrice di vincoli di parametro generico da enumerare.  
  
 `cMax`  
 in   Numero massimo di token richiesto da inserire in `rGenericParamConstraints` .  
  
 `pcGenericParamConstraints`  
 out Puntatore al numero di token inseriti in `rGenericParamConstraints` .  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|`S_OK`|`EnumGenericParameterConstraints`la restituzione è riuscita.|  
|`S_FALSE`|`phEnum`non contiene elementi Member. In questo caso, `pcGenericParameterConstraints` è impostato su 0 (zero).|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in MsCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataImport2](imetadataimport2-interface.md)
- [Interfaccia IMetaDataImport](imetadataimport-interface.md)
