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
ms.openlocfilehash: 79b1493d262288c1d85a56538810e35a73441595
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84491761"
---
# <a name="imetadataimportenumpermissionsets-method"></a>Metodo IMetaDataImport::EnumPermissionSets
Enumera le autorizzazioni per gli oggetti in un ambito dei metadati specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
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
 [in, out] Puntatore all'enumeratore. Deve essere NULL per la prima chiamata di questo metodo.  
  
 `tk`  
 in Token di metadati che limita l'ambito della ricerca o NULL per eseguire la ricerca nell'ambito più ampio possibile.  
  
 `dwActions`  
 in Flag che rappresentano i <xref:System.Security.Permissions.SecurityAction> valori da includere in `rPermission` o zero per restituire tutte le azioni.  
  
 `rPermission`  
 out Matrice utilizzata per archiviare i token di autorizzazione.  
  
 `cMax`  
 [in] Dimensione massima della matrice `rPermission`.  
  
 `pcTokens`  
 out Numero di token di autorizzazione restituiti in `rPermission` .  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|`S_OK`|`EnumPermissionSets`la restituzione è riuscita.|  
|`S_FALSE`|Nessun token da enumerare. In tal caso, `pcTokens` è zero.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Incluso come risorsa in MsCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataImport](imetadataimport-interface.md)
- [Interfaccia IMetaDataImport2](imetadataimport2-interface.md)
