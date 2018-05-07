---
title: Metodo IMetaDataImport2::EnumMethodSpecs
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.EnumMethodSpecs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::EnumMethodSpecs
helpviewer_keywords:
- IMetaDataImport2::EnumMethodSpecs method [.NET Framework metadata]
- EnumMethodSpecs method [.NET Framework metadata]
ms.assetid: b3fc1e6c-bcb6-4915-baf8-7dc0a31b8724
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6c2122c06c6e4f1137173f02e37fb0982864e7ec
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="imetadataimport2enummethodspecs-method"></a>Metodo IMetaDataImport2::EnumMethodSpecs
Ottiene un enumeratore per una matrice di MethodSpec token associato al specificato MethodDef o MemberRef token.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT EnumMethodSpecs (  
    [in, out] HCORENUM      *phEnum,   
    [in]      mdToken       tk,  
    [out]     mdMethodSpec  rMethodSpecs[],  
    [in]      ULONG         cMax,  
    [out]     ULONG         *pcMethodSpecs  
);   
```  
  
#### <a name="parameters"></a>Parametri  
 `phEnum`  
 [in, out] Un puntatore all'enumeratore per `rMethodSpecs`.  
  
 `tk`  
 [in] Il token di MemberRef o MethodDef che rappresenta il metodo di cui i token MethodSpec da enumerare. Se il valore di `tk` è 0 (zero), verranno enumerati tutti i token MethodSpec nell'ambito.  
  
 `rMethodSpecs`  
 [out] Matrice di token MethodSpec da enumerare.  
  
 `cMax`  
 [in] Il numero massimo di richiesto di token da inserire `rMethodSpecs`.  
  
 `pcMethodSpecs`  
 [out] Il numero restituito di token inseriti in `rMethodSpecs`.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|`S_OK`|`EnumMethodSpecs` stato restituito correttamente.|  
|`S_FALSE`|`phEnum` non ha membro elementi. In questo caso, `pcMethodSpecs` è impostato su 0 (zero).|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** usata come risorsa in Mscoree. dll  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)  
 [Interfaccia IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
