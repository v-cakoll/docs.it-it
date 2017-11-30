---
title: Metodo IMetaDataImport::EnumUserStrings
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.EnumUserStrings
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::EnumUserStrings
helpviewer_keywords:
- IMetaDataImport::EnumUserStrings method [.NET Framework metadata]
- EnumUserStrings method [.NET Framework metadata]
ms.assetid: 2b1f1418-4be8-4cdb-b418-b3abccc527a7
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 48ec44d993c5cdc2c545125bf8b4bcb80e413f95
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportenumuserstrings-method"></a>Metodo IMetaDataImport::EnumUserStrings
Enumera i token String che rappresentano le stringhe specificate a livello di codice (hard-coded) nell'ambito dei metadati corrente.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT EnumUserStrings (  
   [in, out]  HCORENUM    *phEnum,  
   [out]  mdString        rStrings[],  
   [in]   ULONG           cMax,  
   [out]  ULONG           *pcStrings  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `phEnum`  
 [in, out] Un puntatore all'enumeratore. Per la prima chiamata di questo metodo deve essere NULL.  
  
 `rStrings`  
 [out] Matrice utilizzata per archiviare i token di stringa.  
  
 `cMax`  
 [in] Dimensione massima della matrice `rStrings`.  
  
 `pcStrings`  
 [out] Il numero di token di stringa restituiti in `rStrings`.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|`S_OK`|`EnumUserStrings`stato restituito correttamente.|  
|`S_FALSE`|Non sono presenti token da enumerare. In tal caso, `pcStrings` è zero.|  
  
## <a name="remarks"></a>Note  
 Vengono creati i token di stringa di [IMetaDataEmit:: DefineUserString](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md) metodo. Questo metodo è progettato per essere utilizzato da un Visualizzatore metadati anziché da un compilatore.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** inclusa come risorsa in MsCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [IMetaDataImport (interfaccia)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [IMetaDataImport2 (interfaccia)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
