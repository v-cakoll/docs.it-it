---
title: Metodo IMetaDataEmit::DefineMemberRef
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.DefineMemberRef
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::DefineMemberRef
helpviewer_keywords:
- DefineMemberRef method [.NET Framework metadata]
- IMetaDataEmit::DefineMemberRef method [.NET Framework metadata]
ms.assetid: 21b5bcb8-ea75-4962-8acc-ad17584061e5
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 4dc4cd317e0e540aaa774cbf9c4c7a2a2ffa40be
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitdefinememberref-method"></a>Metodo IMetaDataEmit::DefineMemberRef
Definisce un riferimento a un membro di un modulo all'esterno dell'ambito corrente e ottiene un token per tale definizione.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT DefineMemberRef (   
    [in]  mdToken           tkImport,   
    [in]  LPCWSTR           szName,   
    [in]  PCCOR_SIGNATURE   pvSigBlob,   
    [in]  ULONG             cbSigBlob,   
    [out] mdMemberRef       *pmr   
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `tkImport`  
 [in] Token per la classe o interfaccia, il membro di destinazione se il membro non è globale. Se il membro è globale, il `mdModuleRef` token per gli altri file.  
  
 `szName`  
 [in] Il nome del membro di destinazione.  
  
 `pvSigBlob`  
 [in] La firma del membro di destinazione.  
  
 `cbSigBlob`  
 [in] Il numero di byte in `pvSigBlob`.  
  
 `pmr`  
 [out] Il `mdMemberRef` token assegnato.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** usata come risorsa in MSCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [IMetaDataEmit (interfaccia)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [Interfaccia IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
