---
title: Metodo IMetaDataImport::EnumInterfaceImpls
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumInterfaceImpls
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumInterfaceImpls
helpviewer_keywords:
- IMetaDataImport::EnumInterfaceImpls method [.NET Framework metadata]
- EnumInterfaceImpls method [.NET Framework metadata]
ms.assetid: ba6e178f-128b-4e47-a13c-b4be73eb106c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 824337a8a87282e59c9fc5df18c71800339e8d7b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="imetadataimportenuminterfaceimpls-method"></a>Metodo IMetaDataImport::EnumInterfaceImpls
Enumera i token MethodDef che rappresentano le implementazioni dell'interfaccia.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT EnumInterfaceImpls (  
   [in, out]  HCORENUM       *phEnum,   
   [in]   mdTypeDef          td,  
   [out]  mdInterfaceImpl    rImpls[],   
   [in]   ULONG              cMax,  
   [out]  ULONG*             pcImpls  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `phEnum`  
 [in, out] Un puntatore all'enumeratore.  
  
 `td`  
 [in] Il token di TypeDef con token MethodDef che rappresentano le implementazioni di interfaccia sono da enumerare.  
  
 `rImpls`  
 [out] Matrice utilizzata per archiviare i token MethodDef.  
  
 `cMax`  
 [in] Dimensione massima della matrice `rImpls`.  
  
 `pcImpls`  
 [out] Il numero effettivo di token restituiti in `rImpls`.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|`S_OK`|`EnumInterfaceImpls` stato restituito correttamente.|  
|`S_FALSE`|Non sono presenti token MethodDef da enumerare. In tal caso, `pcImpls` è impostato su zero.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [Interfaccia IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
