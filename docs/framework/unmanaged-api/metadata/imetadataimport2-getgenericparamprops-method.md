---
title: Metodo IMetaDataImport2::GetGenericParamProps
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.GetGenericParamProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::GetGenericParamProps
helpviewer_keywords:
- IMetaDataImport2::GetGenericParamProps method [.NET Framework metadata]
- GetGenericParamProps method [.NET Framework metadata]
ms.assetid: dbb21e67-712b-49e7-a27c-a1e73ffd46c5
topic_type:
- apiref
ms.openlocfilehash: a8c5dd263401002deaee3d21f1e41b41a29faec2
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427305"
---
# <a name="imetadataimport2getgenericparamprops-method"></a>Metodo IMetaDataImport2::GetGenericParamProps
Ottiene i metadati associati al parametro generico rappresentato dal token specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetGenericParamProps (  
   [in]  mdGenericParam  gp,  
   [out] ULONG           *pulParamSeq,  
   [out] DWORD           *pdwParamFlags,  
   [out] mdToken         *ptOwner,  
   [out] DWORD           *reserved,  
   [out] LPWSTR          wzName,  
   [in]  ULONG           cchName,  
   [out] ULONG           *pchName  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `gp`  
 in Token che rappresenta il parametro generico per il quale restituire i metadati.  
  
 `pulParamSeq`  
 out Posizione ordinale del parametro `Type` nel costruttore o nel metodo padre.  
  
 `pdwParamFlags`  
 out Valore dell'enumerazione [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) che descrive la `Type` per il parametro generico.  
  
 `ptOwner`  
 out Token TypeDef o MethodDef che rappresenta il proprietario del parametro.  
  
 `reserved`  
 out Riservato per l'estendibilità futura.  
  
 `wzName`  
 out Nome del parametro generico.  
  
 `cchName`  
 in Dimensioni del buffer `wzName`.  
  
 `pchName`  
 out Dimensioni restituite del nome, in caratteri wide.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in MsCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [Interfaccia IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
