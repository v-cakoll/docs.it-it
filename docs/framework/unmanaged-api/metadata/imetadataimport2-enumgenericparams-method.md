---
title: Metodo IMetaDataImport2::EnumGenericParams
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport2.EnumGenericParams
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport2::EnumGenericParams
helpviewer_keywords:
- EnumGenericParams method [.NET Framework metadata]
- IMetaDataImport2::EnumGenericParams method [.NET Framework metadata]
ms.assetid: b50488a5-3cf0-483c-82dc-2892a3ec61ac
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 0e6a5dc6cd1d82a3ccd46b09e301a84f90a3f429
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimport2enumgenericparams-method"></a>Metodo IMetaDataImport2::EnumGenericParams
Ottiene un enumeratore per una matrice di token di parametri generici associati il TypeDef o MethodDef specificato token.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT EnumGenericParams (  
   [in, out] HCORENUM     *phEnum,   
   [in]  mdToken          tk,  
   [out] mdGenericParam   rGenericParams[],   
   [in]  ULONG            cMax,   
   [out] ULONG            *pcGenericParams  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `phEnum`  
 [in, out] Un puntatore all'enumeratore.  
  
 `tk`  
 [in] Il token TypeDef o MethodDef i cui parametri generici sono da enumerare.  
  
 `rGenericParams`  
 [out] Matrice di parametri generici da enumerare.  
  
 `cMax`  
 [in] Il numero massimo di richiesto di token da inserire `rGenericParams`.  
  
 `pcGenericParams`  
 [out] Il numero restituito di token inseriti in `rGenericParams`.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|`S_OK`|`EnumGenericParams`stato restituito correttamente.|  
|`S_FALSE`|`phEnum`non sono membri. In questo caso, `pcGenericParams` è impostato su 0 (zero).|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** usata come risorsa in MsCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [IMetaDataImport2 (interfaccia)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)  
 [IMetaDataImport (interfaccia)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
