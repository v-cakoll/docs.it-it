---
title: Metodo IMetaDataImport::EnumMembersWithName
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMembersWithName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMembersWithName
helpviewer_keywords:
- IMetaDataImport::EnumMembersWithName method [.NET Framework metadata]
- EnumMembersWithName method [.NET Framework metadata]
ms.assetid: 7c9e9120-3104-42f0-86ce-19a025f20dcc
topic_type:
- apiref
ms.openlocfilehash: ed193aab8beb0de1321aa1d52ec9f963b08b316c
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74441658"
---
# <a name="imetadataimportenummemberswithname-method"></a>Metodo IMetaDataImport::EnumMembersWithName
Enumera i token MemberDef che rappresentano i membri del tipo specificato con il nome specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT EnumMembersWithName (  
   [in, out] HCORENUM    *phEnum,   
   [in]      mdTypeDef   cl,   
   [in]      LPCWSTR     szName,   
   [out]     mdToken     rMembers[],   
   [in]      ULONG       cMax,   
   [out]     ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `phEnum`  
 [in, out] Puntatore all'enumeratore.  
  
 `cl`  
 in Token TypeDef che rappresenta il tipo con i membri da enumerare.  
  
 `szName`  
 in Nome del membro che limita l'ambito dell'enumeratore.  
  
 `rMembers`  
 out Matrice utilizzata per archiviare i token MemberDef.  
  
 `cMax`  
 [in] Dimensione massima della matrice `rMembers`.  
  
 `pcTokens`  
 out Numero effettivo di token MemberDef restituiti in `rMembers`.  
  
## <a name="remarks"></a>Osservazioni  
 Questo metodo enumera i campi e i metodi, ma non le proprietà o gli eventi. A differenza di [IMetaDataImport:: EnumMembers](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enummembers-method.md), `EnumMembersWithName` Elimina tutti i token dei campi e dei membri che non hanno il nome specificato.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|description|  
|-------------|-----------------|  
|`S_OK`|`EnumTypeDefs` ha restituito un esito positivo.|  
|`S_FALSE`|Nessun token MemberDef da enumerare. In tal caso, `pcTokens` è zero.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Incluso come risorsa in MsCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Interfaccia IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
