---
title: Metodo IMetaDataEmit::Merge
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.Merge
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::Merge
helpviewer_keywords:
- IMetaDataEmit::Merge method [.NET Framework metadata]
- Merge method [.NET Framework metadata]
ms.assetid: 7596220c-f699-4b6c-8ae7-c83220610650
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 42ebc188dfecde068ef8e2979970118fee91ec4b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitmerge-method"></a>Metodo IMetaDataEmit::Merge
Aggiunge l'ambito importato specificato all'elenco di ambiti da unire.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT Merge (   
    [in]  IMetaDataImport  *pImport,   
    [in]  IMapToken        *pHostMapToken,   
    [in]  IUnknown         *pHandler   
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `pImport`  
 [in] Un puntatore a un [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) oggetto che identifica l'ambito importato da unire.  
  
 `pIMap`  
 [in] Un puntatore a un [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) oggetto che specifica il nuovo mapping dei token.  
  
 `pHandleer`  
 [in] Un puntatore a un <!--<<!--zzxref:IUnknown --> `IUnknown` >-->  `IUnknown` oggetto che specifica gli errori.  
  
## <a name="remarks"></a>Note  
 Chiamare [IMetaDataEmit:: MergeEnd](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-mergeend-method.md) per attivare l'unione dei metadati in un singolo ambito.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** usata come risorsa in MSCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [IMetaDataEmit (interfaccia)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [Interfaccia IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
