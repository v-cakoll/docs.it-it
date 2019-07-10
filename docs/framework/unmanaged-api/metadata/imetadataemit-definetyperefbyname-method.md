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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f005ee9d3d9d4b8977cd6a1838fe46015e604df5
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777476"
---
# <a name="imetadataemitdefinetyperefbyname-method"></a>Metodo IMetaDataEmit::DefineTypeRefByName
Ottiene i metadati di un token per un tipo definito nell'ambito specificato, che non rientrano nell'ambito corrente.  
  
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
 [in] Il token che specifica l'ambito di risoluzione. I tipi di token seguenti sono validi:  
  
- `mdModuleRef`, se il tipo è definito nello stesso assembly in cui è definito il chiamante.  
  
- `mdAssemblyRef`, se il tipo è definito in un assembly diverso da quello in cui è definito il chiamante.  
  
- `mdTypeRef`, se il tipo è un tipo annidato.  
  
- `mdModule`, se il tipo è definito nello stesso modulo in cui è definito il chiamante.  
  
- Null se il tipo è definito a livello globale.  
  
 `szName`  
 [in] Il nome del tipo di destinazione in formato Unicode.  
  
 `ptr`  
 [out] Un puntatore al `mdTypeRef` token assegnato al tipo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [Interfaccia IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
