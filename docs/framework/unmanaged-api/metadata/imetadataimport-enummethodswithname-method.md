---
title: Metodo IMetaDataImport::EnumMethodsWithName
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.EnumMethodsWithName
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::EnumMethodsWithName
helpviewer_keywords:
- IMetaDataImport::EnumMethodsWithName method [.NET Framework metadata]
- EnumMethodsWithName method [.NET Framework metadata]
ms.assetid: a8624913-2e23-46ad-a0c1-bb8eccbbf20f
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: dadff8be283160ddc6049d0d2f8b78052e5c8ec5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportenummethodswithname-method"></a>Metodo IMetaDataImport::EnumMethodsWithName
Enumera i metodi che hanno il nome specificato e che sono definiti dal tipo a cui fa riferimento il token TypeDef specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT EnumMethodsWithName (  
   [in, out] HCORENUM    *phEnum,  
   [in]  mdTypeDef       cl,  
   [in]  LPCWSTR         szName,  
   [out] mdMethodDef     rMethods[],  
   [in]  ULONG           cMax,  
   [out] ULONG           *pcTokens  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `phEnum`  
 [in, out] Un puntatore all'enumeratore. Per la prima chiamata di questo metodo deve essere NULL.  
  
 `cl`  
 [in] Token TypeDef che rappresenta il tipo i cui metodi da enumerare.  
  
 `szName`  
 [in] Il nome che limita l'ambito dell'enumerazione.  
  
 `rMethods`  
 [out] Matrice utilizzata per archiviare i token MethodDef.  
  
 `cMax`  
 [in] Dimensione massima della matrice `rMethods`.  
  
 `pcTokens`  
 [out] Il numero di token MethodDef restituiti in `rMethods`.  
  
## <a name="remarks"></a>Note  
 Questo metodo enumera i campi e metodi, ma non a proprietà o eventi. A differenza di [IMetaDataImport:: EnumMethods](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enummethods-method.md), `EnumMethodsWithName` Elimina tutti i token che non contengono il nome specificato.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|`S_OK`|`EnumMethodsWithName`stato restituito correttamente.|  
|`S_FALSE`|Non sono presenti token da enumerare. In tal caso, `pcTokens` è zero.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** inclusa come risorsa in MsCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [IMetaDataImport (interfaccia)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [IMetaDataImport2 (interfaccia)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
