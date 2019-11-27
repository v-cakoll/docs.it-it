---
title: Metodo IMetaDataEmit::DefineTypeRefByName
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineTypeRefByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineTypeRefByName
helpviewer_keywords:
- DefineTypeRefByName method [.NET Framework metadata]
- IMetaDataEmit::DefineTypeRefByName method [.NET Framework metadata]
ms.assetid: c30a4ce3-2d3e-411a-98df-e62ac4a5dd50
topic_type:
- apiref
ms.openlocfilehash: 3dfdd473b01bfe83def52f957c52e0f4d11375ad
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74434378"
---
# <a name="imetadataemitdefinetyperefbyname-method"></a>Metodo IMetaDataEmit::DefineTypeRefByName
Ottiene un token di metadati per un tipo definito nell'ambito specificato, che non è compreso nell'ambito corrente.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT DefineTypeRefByName (   
    [in]  mdToken     tkResolutionScope,   
    [in]  LPCWSTR     szName,   
    [out] mdTypeRef   *ptr   
);  
```  
  
## <a name="parameters"></a>Parametri  
 `tkResolutionScope`  
 in Token che specifica l'ambito di risoluzione. I tipi di token seguenti sono validi:  
  
- `mdModuleRef`, se il tipo è definito nello stesso assembly in cui è definito il chiamante.  
  
- `mdAssemblyRef`, se il tipo è definito in un assembly diverso da quello in cui è definito il chiamante.  
  
- `mdTypeRef`, se il tipo è un tipo annidato.  
  
- `mdModule`, se il tipo è definito nello stesso modulo in cui è definito il chiamante.  
  
- Null, se il tipo è definito globalmente.  
  
 `szName`  
 in Nome del tipo di destinazione in Unicode.  
  
 `ptr`  
 out Puntatore al token `mdTypeRef` assegnato al tipo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in MSCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [Interfaccia IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
