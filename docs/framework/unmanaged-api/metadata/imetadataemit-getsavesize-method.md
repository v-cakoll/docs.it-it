---
title: Metodo IMetaDataEmit::GetSaveSize
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.GetSaveSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::GetSaveSize
helpviewer_keywords:
- IMetaDataEmit::GetSaveSize method [.NET Framework metadata]
- GetSaveSize method [.NET Framework metadata]
ms.assetid: 8aea2e2c-23a3-4cda-9a06-e19f97383830
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d9a65f76aed00e2b848f8603f1fee4d6acc91f99
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
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
 `GetSaveSize` Calcola lo spazio necessario, in byte, per salvare l'assembly e tutti i relativi metadati nell'ambito corrente. (Una chiamata al [IMetaDataEmit:: SaveToStream](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetostream-method.md) metodo genererebbe questo numero di byte.)  
  
 Se il chiamante implementa il [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) interfaccia (tramite [IMetaDataEmit:: SetHandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) o [IMetaDataEmit:: Merge](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md)), `GetSaveSize` eseguirà due passaggi sui metadati per ottimizzare e la compressione. In caso contrario, non vengono eseguite ottimizzazioni.  
  
 Se viene eseguita l'ottimizzazione, il primo passaggio ordina semplicemente le strutture di metadati per ottimizzare le prestazioni delle ricerche in fase di importazione. Questo passaggio in genere comporta lo spostamento di record, con un effetto secondario che non vengono invalidati token mantenuti dallo strumento per riferimento futuro. I metadati non informare il chiamante di queste modifiche token fino a dopo il secondo passaggio, tuttavia. Nel secondo passaggio, vengono eseguite diverse ottimizzazioni allo scopo di ridurre la dimensione complessiva dei metadati, ad esempio ottimizzazione (associazione anticipata) `mdTypeRef` e `mdMemberRef` token se il riferimento a un tipo o un membro dichiarato nel ambito dei metadati corrente. In questo passaggio, si verifica un altro round mapping dei token. Dopo questo passaggio, il motore dei metadati notifica al chiamante, tramite il relativo `IMapToken` interfaccia, di qualsiasi modificato i valori del token.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** usata come risorsa in Mscoree. dll  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [Interfaccia IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
