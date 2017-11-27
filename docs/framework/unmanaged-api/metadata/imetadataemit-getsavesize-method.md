---
title: Metodo IMetaDataEmit::GetSaveSize
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.GetSaveSize
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::GetSaveSize
helpviewer_keywords:
- IMetaDataEmit::GetSaveSize method [.NET Framework metadata]
- GetSaveSize method [.NET Framework metadata]
ms.assetid: 8aea2e2c-23a3-4cda-9a06-e19f97383830
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 9686e8e2c4e8276e725852cb58fac7ed1973778b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitgetsavesize-method"></a>Metodo IMetaDataEmit::GetSaveSize
Ottiene le dimensioni stimate binaria dell'assembly e i relativi metadati nell'ambito corrente.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetSaveSize (  
    [in]  CorSaveSize fSave,  
    [out] DWORD       *pdwSaveSize  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `fSave`  
 [in] Il valore di [CorSaveSize](../../../../docs/framework/unmanaged-api/metadata/corsavesize-enumeration.md) enumerazione che specifica se ottenere le dimensioni precisa o approssimativa. Sono validi solo tre valori: cssAccurate, cssQuick e cssDiscardTransientCAs:  
  
-   cssAccurate restituisce la dimensione di salvataggio, ma richiede più tempo per il calcolo.  
  
-   cssQuick restituisce una dimensione, vengono aggiunti per sicurezza, ma richiede meno tempo per il calcolo.  
  
-   cssDiscardTransientCAs indica `GetSaveSize` che possono essere generate da subito scaricabile attributi personalizzati.  
  
 `pdwSaveSize`  
 [out] Puntatore alle dimensioni necessarie per salvare il file.  
  
## <a name="remarks"></a>Note  
 `GetSaveSize`Calcola lo spazio, espressa in byte, necessario per salvare l'assembly e tutti i relativi metadati nell'ambito corrente. (Una chiamata al [IMetaDataEmit:: SaveToStream](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetostream-method.md) metodo genererebbe questo numero di byte.)  
  
 Se il chiamante implementa il [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) interfaccia (tramite [IMetaDataEmit:: SetHandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) o [IMetaDataEmit:: Merge](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md)), `GetSaveSize` eseguirà due passaggi sui metadati per ottimizzare e la compressione. In caso contrario, non vengono eseguite ottimizzazioni.  
  
 Se viene eseguita l'ottimizzazione, il primo passaggio ordina semplicemente le strutture di metadati per ottimizzare le prestazioni delle ricerche in fase di importazione. Questo passaggio in genere comporta lo spostamento di record, con un effetto secondario che non vengono invalidati token mantenuti dallo strumento per riferimento futuro. I metadati non informare il chiamante di queste modifiche token fino a dopo il secondo passaggio, tuttavia. Nel secondo passaggio, vengono eseguite diverse ottimizzazioni allo scopo di ridurre la dimensione complessiva dei metadati, ad esempio ottimizzazione (associazione anticipata) `mdTypeRef` e `mdMemberRef` token se il riferimento a un tipo o un membro dichiarato nel ambito dei metadati corrente. In questo passaggio, si verifica un altro round mapping dei token. Dopo questo passaggio, il motore dei metadati notifica al chiamante, tramite il relativo `IMapToken` interfaccia, di qualsiasi modificato i valori del token.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** usata come risorsa in MSCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [IMetaDataEmit (interfaccia)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [Interfaccia IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
