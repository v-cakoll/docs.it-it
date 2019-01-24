---
title: Metodo IMetaDataImport::EnumTypeDefs
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumTypeDefs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumTypeDefs
helpviewer_keywords:
- EnumTypeDefs method [.NET Framework metadata]
- IMetaDataImport::EnumTypeDefs method [.NET Framework metadata]
ms.assetid: 4e508711-da92-4381-aaf8-6803075cdaa2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0e6314a76433276561a8b4b87a852464dae69824
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54656258"
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
 [out] Puntatore al nuovo enumeratore. Per la prima chiamata di questo metodo deve essere NULL.  
  
 `rTypeDefs`  
 [in] Matrice utilizzata per archiviare i token TypeDef.  
  
 `cMax`  
 [in] Dimensione massima della matrice `rTypeDefs`.  
  
 `pcTypeDefs`  
 [out] Il numero di token TypeDef restituiti in `rTypeDefs`.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|`S_OK`|`EnumTypeDefs` stato restituito correttamente.|  
|`S_FALSE`|Non sono presenti token da enumerare. In tal caso, `pcTypeDefs` è uguale a zero.|  
  
## <a name="remarks"></a>Note  
 Il token TypeDef rappresenta un tipo, ad esempio una classe o un'interfaccia, nonché qualsiasi tipo aggiunto tramite un meccanismo di estendibilità.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Interfaccia IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
