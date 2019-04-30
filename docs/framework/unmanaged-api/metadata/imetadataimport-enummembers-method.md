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
ms.openlocfilehash: e8d871f2ecbd96d5bda781b2ae11b94efd409442
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62049921"
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
  
## <a name="parameters"></a>Parametri  
 `phEnum`  
 [in, out] Un puntatore all'enumeratore.  
  
 `cl`  
 [in] Token TypeDef che rappresenta il tipo i cui membri sono da enumerare.  
  
 `rMembers`  
 [out] Matrice usata per contenere i token MemberDef.  
  
 `cMax`  
 [in] Dimensione massima della matrice `rMembers`.  
  
 `pcTokens`  
 [out] Il numero effettivo di token MemberDef restituiti in `rMembers`.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|`S_OK`|`EnumMembers` stato restituito correttamente.|  
|`S_FALSE`|Non sono presenti token MemberDef per enumerare. In tal caso, `pcTokens` è uguale a zero.|  
  
## <a name="remarks"></a>Note  
 Durante l'enumerazione delle raccolte di membri per una classe `EnumMembers` restituisce solo i membri (campi e metodi, ma **non** eventi o proprietà) definiti direttamente nella classe. Non restituisce tutti i membri che eredita la classe, anche se la classe fornisce un'implementazione per i membri ereditati. Per enumerare i membri ereditati, il chiamante deve verificare in modo esplicito la catena di ereditarietà. Si noti che le regole per la catena di ereditarietà possono variare a seconda del linguaggio o un compilatore che ha creato i metadati originali.
 
 Proprietà ed eventi non sono enumerati dal `EnumMembers`. Per enumerare quelli, usare [EnumProperties](imetadataimport-enumproperties-method.md) oppure [EnumEvents](imetadataimport-enumevents-method.md).
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Interfaccia IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
