---
title: Metodo IMetaDataEmit::DefineEvent
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.DefineEvent
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::DefineEvent
helpviewer_keywords:
- IMetaDataEmit::DefineEvent method [.NET Framework metadata]
- DefineEvent method [.NET Framework metadata]
ms.assetid: cf064bac-9a9f-41c5-9e1d-108ff7af3afe
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: bf790ce270565abaf1d91e54c9e3569a50ab3435
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitdefineevent-method"></a>Metodo IMetaDataEmit::DefineEvent
Crea una definizione per un evento con la firma dei metadati specificati e ottiene un token per tale definizione di evento.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT DefineEvent (   
    [in]  mdTypeDef    td,   
    [in]  LPCWSTR      szEvent,   
    [in]  DWORD        dwEventFlags,   
    [in]  mdToken      tkEventType,   
    [in]  mdMethodDef  mdAddOn,   
    [in]  mdMethodDef  mdRemoveOn,   
    [in]  mdMethodDef  mdFire,   
    [in]  mdMethodDef  rmdOtherMethods[],   
    [out] mdEvent      *pmdEvent   
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `td`  
 [in] Il token per la classe di destinazione o l'interfaccia. Questo è un `mdTypeDef` o `mdTypeDefNil` token.  
  
 `szEvent`  
 [in] Il nome dell'evento.  
  
 `dwEventFlags`  
 [in] Flag di evento.  
  
 `tkEventType`  
 [in] Il token per la classe di evento. Si tratta di un `mdTypeDef`, `mdTypeRef`, o un `mdTokenNil` token.  
  
 `mdAddOn`  
 [in] Il metodo utilizzato per sottoscrivere l'evento, o null.  
  
 `mdRemoveOn`  
 [in] Il metodo utilizzato per annullare la sottoscrizione per l'evento, o null.  
  
 `mdFire`  
 [in] Il metodo utilizzato (da una classe derivata) per generare l'evento.  
  
 `rmdOtherMethods[]`  
 [in] Matrice di token per gli altri metodi associati all'evento. La matrice viene terminata con un `mdMethodDefNil` token.  
  
 `pmdEvent`  
 [out] Il token di metadati assegnato all'evento.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** usata come risorsa in MSCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [IMetaDataEmit (interfaccia)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [Interfaccia IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
