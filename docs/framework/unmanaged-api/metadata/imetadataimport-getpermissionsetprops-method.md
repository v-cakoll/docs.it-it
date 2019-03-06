---
title: Metodo IMetaDataImport::GetPermissionSetProps
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetPermissionSetProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetPermissionSetProps
helpviewer_keywords:
- GetPermissionSetProps method [.NET Framework metadata]
- IMetaDataImport::GetPermissionSetProps method [.NET Framework metadata]
ms.assetid: 9855f0e4-12c0-4d3d-ab5d-d6bc52d25eae
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 806f1ebcacb9e7ad27b7370f9976b3341bf64f8c
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57466934"
---
# <a name="imetadataimportgetpermissionsetprops-method"></a>Metodo IMetaDataImport::GetPermissionSetProps
Ottiene i metadati associati il <xref:System.Security.PermissionSet?displayProperty=nameWithType> rappresentato dal token Permission specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetPermissionSetProps (  
   [in]  mdPermission      pm,  
   [out] DWORD             *pdwAction,   
   [out] void const        **ppvPermission,   
   [out] ULONG             *pcbPermission  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pm`  
 [in] Il token di metadati di autorizzazione che rappresenta l'autorizzazione impostata per ottenere le proprietà dei metadati.  
  
 `pdwAction`  
 [out] Puntatore al set di autorizzazioni.  
  
 `ppvPermission`  
 [out] Un puntatore per la firma binaria dei metadati del set di autorizzazioni.  
  
 `pcbPermission`  
 [out] La dimensione in byte di `ppvPermission`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Security.PermissionSet>
- [Interfaccia IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Interfaccia IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
