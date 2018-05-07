---
title: Metodo IMetaDataImport::EnumMembers
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMembers
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMembers
helpviewer_keywords:
- IMetaDataImport::EnumMembers method [.NET Framework metadata]
- EnumMembers method [.NET Framework metadata]
ms.assetid: 3fb8e178-342b-4c89-9bcf-f7f834e6cb77
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 46ee8c62861a62ac044f295f7da082756d87347b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="imetadataimportenummembers-method"></a>Metodo IMetaDataImport::EnumMembers
Enumera i token MemberDef che rappresentano i membri del tipo specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT EnumMembers (   
   [in, out]  HCORENUM    *phEnum,   
   [in]  mdTypeDef   cl,   
   [out] mdToken     rMembers[],   
   [in]  ULONG       cMax,   
   [out] ULONG       *pcTokens  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `phEnum`  
 [in, out] Un puntatore all'enumeratore.  
  
 `cl`  
 [in] Token TypeDef che rappresenta il tipo i cui membri sono da enumerare.  
  
 `rMembers`  
 [out] Matrice utilizzata per contenere i token MemberDef.  
  
 `cMax`  
 [in] Dimensione massima della matrice `rMembers`.  
  
 `pcTokens`  
 [out] Il numero effettivo di token MemberDef restituiti in `rMembers`.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|`S_OK`|`EnumMembers` stato restituito correttamente.|  
|`S_FALSE`|Non sono presenti token MemberDef da enumerare. In tal caso, `pcTokens` è zero.|  
  
## <a name="remarks"></a>Note  
 Durante l'enumerazione di raccolte di membri per una classe, `EnumMembers` restituisce solo i membri definiti direttamente sulla classe. Non restituisce i membri che eredita la classe, anche se la classe fornisce un'implementazione per i membri ereditati. Per enumerare i membri ereditati, il chiamante deve verificare in modo esplicito la catena di ereditarietà. Si noti che le regole per la catena di ereditarietà possono variare a seconda del linguaggio o del compilatore che ha creato i metadati originali.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [Interfaccia IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
