---
title: Metodo IMetaDataImport::EnumPermissionSets
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumPermissionSets
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumPermissionSets
helpviewer_keywords:
- EnumPermissionSets method [.NET Framework metadata]
- IMetaDataImport::EnumPermissionSets method [.NET Framework metadata]
ms.assetid: 347d7e5c-c90f-45ad-bd1e-2c7912b0b19c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 28e6ad309af808638400fc27255acdee381b4c6e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59196697"
---
# <a name="imetadataimportenumpermissionsets-method"></a>Metodo IMetaDataImport::EnumPermissionSets
Enumera le autorizzazioni per gli oggetti in un ambito dei metadati specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT EnumPermissionSets  
   [in, out] HCORENUM      *phEnum,   
   [in]      mdToken       tk,   
   [in]      DWORD         dwActions,  
   [out]     mdPermission  rPermission[],  
   [in]      ULONG         cMax,  
   [out]     ULONG         *pcTokens  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `phEnum`  
 [in, out] Un puntatore all'enumeratore. Per la prima chiamata di questo metodo deve essere NULL.  
  
 `tk`  
 [in] Token di metadati che limita l'ambito della ricerca, o NULL per la ricerca nell'ambito più ampio possibile.  
  
 `dwActions`  
 [in] Flag che rappresenta il <xref:System.Security.Permissions.SecurityAction> valori da includere in `rPermission`, oppure zero per restituire tutte le azioni.  
  
 `rPermission`  
 [out] Matrice utilizzata per archiviare i token di autorizzazione.  
  
 `cMax`  
 [in] Dimensione massima della matrice `rPermission`.  
  
 `pcTokens`  
 [out] Il numero di token di autorizzazione restituiti in `rPermission`.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|`S_OK`|`EnumPermissionSets` stato restituito correttamente.|  
|`S_FALSE`|Non sono presenti token da enumerare. In tal caso, `pcTokens` è uguale a zero.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Interfaccia IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
