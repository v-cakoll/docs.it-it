---
title: Metodo IMetaDataImport::EnumTypeDefs
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.EnumTypeDefs
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::EnumTypeDefs
helpviewer_keywords:
- EnumTypeDefs method [.NET Framework metadata]
- IMetaDataImport::EnumTypeDefs method [.NET Framework metadata]
ms.assetid: 4e508711-da92-4381-aaf8-6803075cdaa2
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a07d9ff237e6d3838fffb068e3a9ebf9febf66fc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportenumtypedefs-method"></a>Metodo IMetaDataImport::EnumTypeDefs
Enumera i token TypeDef che rappresentano tutti i tipi all'interno dell'ambito corrente.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT EnumTypeDefs (  
   [out] HCORENUM   *phEnum,   
   [in]  mdTypeDef  rTypeDefs[],  
   [in]  ULONG      cMax,   
   [out] ULONG      *pcTypeDefs  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `phEnum`  
 [out] Un puntatore per il nuovo enumeratore. Per la prima chiamata di questo metodo deve essere NULL.  
  
 `rTypeDefs`  
 [in] Matrice utilizzata per archiviare i token TypeDef.  
  
 `cMax`  
 [in] Dimensione massima della matrice `rTypeDefs`.  
  
 `pcTypeDefs`  
 [out] Il numero di token TypeDef restituiti in `rTypeDefs`.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|`S_OK`|`EnumTypeDefs`stato restituito correttamente.|  
|`S_FALSE`|Non sono presenti token da enumerare. In tal caso, `pcTypeDefs` è zero.|  
  
## <a name="remarks"></a>Note  
 Il token TypeDef rappresenta un tipo, ad esempio una classe o un'interfaccia, come qualsiasi tipo aggiunto tramite un meccanismo di extensibility.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** inclusa come risorsa in MsCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [IMetaDataImport (interfaccia)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [IMetaDataImport2 (interfaccia)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
