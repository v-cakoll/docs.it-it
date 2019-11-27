---
title: Metodo IMetaDataImport::EnumMethodsWithName
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMethodsWithName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMethodsWithName
helpviewer_keywords:
- IMetaDataImport::EnumMethodsWithName method [.NET Framework metadata]
- EnumMethodsWithName method [.NET Framework metadata]
ms.assetid: a8624913-2e23-46ad-a0c1-bb8eccbbf20f
topic_type:
- apiref
ms.openlocfilehash: b0817288040550b5f4c3c4ec063f6a7fdb004137
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450055"
---
# <a name="imetadataimportenummethodswithname-method"></a>Metodo IMetaDataImport::EnumMethodsWithName
Enumera i metodi che hanno il nome specificato e che sono definiti dal tipo a cui fa riferimento il token TypeDef specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT EnumMethodsWithName (  
   [in, out] HCORENUM    *phEnum,  
   [in]  mdTypeDef       cl,  
   [in]  LPCWSTR         szName,  
   [out] mdMethodDef     rMethods[],  
   [in]  ULONG           cMax,  
   [out] ULONG           *pcTokens  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `phEnum`  
 [in, out] Puntatore all'enumeratore. Deve essere NULL per la prima chiamata di questo metodo.  
  
 `cl`  
 in Token TypeDef che rappresenta il tipo di cui si desidera enumerare i metodi.  
  
 `szName`  
 in Nome che limita l'ambito dell'enumerazione.  
  
 `rMethods`  
 out Matrice utilizzata per archiviare i token MethodDef.  
  
 `cMax`  
 [in] Dimensione massima della matrice `rMethods`.  
  
 `pcTokens`  
 out Numero di token MethodDef restituiti in `rMethods`.  
  
## <a name="remarks"></a>Osservazioni  
 Questo metodo enumera i campi e i metodi, ma non le proprietà o gli eventi. A differenza di [IMetaDataImport:: EnumMethods](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enummethods-method.md), `EnumMethodsWithName` Elimina tutti i token di metodo che non hanno il nome specificato.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|description|  
|-------------|-----------------|  
|`S_OK`|`EnumMethodsWithName` ha restituito un esito positivo.|  
|`S_FALSE`|Nessun token da enumerare. In tal caso, `pcTokens` è zero.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Incluso come risorsa in MsCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Interfaccia IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
