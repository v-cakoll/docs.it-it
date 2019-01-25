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
ms.openlocfilehash: 164cdc5c04a55e9c33dda51e10dfb37f38ec1b6d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54746544"
---
# <a name="imetadataemitgetsavesize-method"></a>Metodo IMetaDataEmit::GetSaveSize
Ottiene la dimensione stimata binaria dell'assembly e i relativi metadati nell'ambito corrente.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetSaveSize (  
    [in]  CorSaveSize fSave,  
    [out] DWORD       *pdwSaveSize  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `fSave`  
 [in] Valore di [CorSaveSize](../../../../docs/framework/unmanaged-api/metadata/corsavesize-enumeration.md) enumerazione che specifica se si desidera ottenere le dimensioni accurate o approssimative. Solo tre valori sono validi: cssAccurate, cssQuick cssDiscardTransientCAs e:  
  
-   cssAccurate restituisce l'esatta dimensione di salvataggio, ma richiede più tempo per il calcolo.  
  
-   cssQuick restituisce una dimensione, vengono aggiunti per sicurezza, ma richiede meno tempo per il calcolo.  
  
-   indica a cssDiscardTransientCAs `GetSaveSize` che possono essere generate da subito gli attributi personalizzati annullabile.  
  
 `pdwSaveSize`  
 [out] Un puntatore alla dimensione necessaria per salvare il file.  
  
## <a name="remarks"></a>Note  
 `GetSaveSize` Calcola lo spazio necessario, in byte, per salvare l'assembly e tutti i relativi metadati nell'ambito corrente. (Una chiamata per il [SaveToStream](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetostream-method.md) metodo genererebbe il numero di byte.)  
  
 Se il chiamante implementa il [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) interfaccia (tramite [SetHandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) oppure [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md)), `GetSaveSize` eseguirà due passaggi su tutti i metadati per ottimizzare e comprimerlo. In caso contrario, non verranno eseguite ottimizzazioni.  
  
 Se l'ottimizzazione viene eseguita, il primo passaggio di ordina semplicemente le strutture di metadati per ottimizzare le prestazioni delle ricerche in fase di importazione. Questo passaggio determina in genere lo spostamento di record, con l'effetto collaterale che non sono più validi i token conservati dallo strumento per riferimento futuro. I metadati non informare il chiamante di queste modifiche dei token fino a dopo il secondo passaggio, tuttavia. Nel secondo passaggio, vengono eseguite diverse ottimizzazioni che consentono di ridurre le dimensioni complessive dei metadati, ad esempio ottimizzazione (associazione anticipata) `mdTypeRef` e `mdMemberRef` token quando il riferimento è relativo a un tipo o membro dichiarato nel ambito dei metadati corrente. In questo passaggio, si verifica un altro round di mapping dei token. Dopo questo passaggio, il motore di metadati notifica al chiamante, mediante il `IMapToken` interfaccia, di qualsiasi modificato i valori dei token.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [Interfaccia IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
