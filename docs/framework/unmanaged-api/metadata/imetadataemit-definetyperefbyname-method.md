---
title: Metodo IMetaDataEmit::DefineTypeRefByName
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.DefineTypeRefByName
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::DefineTypeRefByName
helpviewer_keywords:
- DefineTypeRefByName method [.NET Framework metadata]
- IMetaDataEmit::DefineTypeRefByName method [.NET Framework metadata]
ms.assetid: c30a4ce3-2d3e-411a-98df-e62ac4a5dd50
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 46b9fe83a5beb031d4ac21deb903060e2f788e1a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitdefinetyperefbyname-method"></a>Metodo IMetaDataEmit::DefineTypeRefByName
Ottiene i metadati di un token per un tipo definito nell'ambito specificato, che è esterno all'ambito corrente.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT DefineTypeRefByName (   
    [in]  mdToken     tkResolutionScope,   
    [in]  LPCWSTR     szName,   
    [out] mdTypeRef   *ptr   
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `tkResolutionScope`  
 [in] Il token che specifica l'ambito di risoluzione. I tipi di token seguenti sono validi:  
  
-   `mdModuleRef`, se il tipo è definito nello stesso assembly in cui è definito il chiamante.  
  
-   `mdAssemblyRef`, se il tipo è definito in un assembly diverso da quello in cui è definito il chiamante.  
  
-   `mdTypeRef`, se il tipo è un tipo annidato.  
  
-   `mdModule`, se il tipo è definito nello stesso modulo in cui è definito il chiamante.  
  
-   Null se il tipo è definito a livello globale.  
  
 `szName`  
 [in] Il nome del tipo di destinazione in formato Unicode.  
  
 `ptr`  
 [out] Un puntatore al `mdTypeRef` token assegnato al tipo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** usata come risorsa in MSCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [Interfaccia IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
