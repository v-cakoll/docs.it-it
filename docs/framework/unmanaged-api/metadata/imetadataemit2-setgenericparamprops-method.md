---
title: Metodo IMetaDataEmit2::SetGenericParamProps
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.SetGenericParamProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::SetGenericParamProps
helpviewer_keywords:
- IMetaDataEmit2::SetGenericParamProps method [.NET Framework metadata]
- SetGenericParamProps method [.NET Framework metadata]
ms.assetid: cd93a48d-1fed-4706-bec6-a05dc3b64fbd
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 406a8ea4600c1e5ef55c0d905ff3aa4a30d068e7
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57485213"
---
# <a name="imetadataemit2setgenericparamprops-method"></a>Metodo IMetaDataEmit2::SetGenericParamProps
Imposta i valori di proprietà per la definizione di parametro generico a cui fanno riferimento al token specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT SetGenericParamProps (  
    [in] mdGenericParam   gp,   
    [in] DWORD            dwParamFlags,   
    [in] LPCWSTR          szName,   
    [in] DWORD            reserved,   
    [in] mdToken          rtkConstraints[]  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `gp`  
 [in] Il token per la definizione di parametro generico per il quale impostare i valori.  
  
 `dwParamFlags`  
 [in] Valore di [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) enumerazione che descrive il tipo parametro generico.  
  
 `szName`  
 [in] Facoltativo. Il nome del parametro per cui impostare i valori.  
  
 `reserved`  
 [in] Riservato per un'estendibilità futura.  
  
 `rtkConstraints`  
 [in] Facoltativo. Una matrice con terminazione zero di vincoli di tipo. I membri della matrice devono essere un' `mdTypeDef`, `mdTypeRef`, o `mdTypeSpec` token di metadati.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [Interfaccia IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
