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
ms.openlocfilehash: 0a283c837e23ab1aafd3545df1dfe8a267de0557
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501287"
---
# <a name="imetadataemitgetsavesize-method"></a>Metodo IMetaDataEmit::GetSaveSize
Ottiene la dimensione binaria stimata dell'assembly e i relativi metadati nell'ambito corrente.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetSaveSize (  
    [in]  CorSaveSize fSave,  
    [out] DWORD       *pdwSaveSize  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `fSave`  
 in Valore dell'enumerazione [CorSaveSize](corsavesize-enumeration.md) che specifica se ottenere una dimensione accurata o approssimativa. Sono validi solo tre valori: cssAccurate, cssQuick e cssDiscardTransientCAs:  
  
- cssAccurate restituisce le dimensioni esatte del salvataggio, ma richiede più tempo per il calcolo.  
  
- cssQuick restituisce una dimensione, riempita per la sicurezza, ma richiede meno tempo per il calcolo.  
  
- cssDiscardTransientCAs indica `GetSaveSize` che è possibile eliminare gli attributi personalizzati scartabili.  
  
 `pdwSaveSize`  
 out Un puntatore alla dimensione necessaria per salvare il file.  
  
## <a name="remarks"></a>Osservazioni  
 `GetSaveSize`calcola lo spazio necessario, in byte, per salvare l'assembly e tutti i relativi metadati nell'ambito corrente. Una chiamata al metodo [IMetaDataEmit:: SaveToStream](imetadataemit-savetostream-method.md) emetterebbe questo numero di byte.  
  
 Se il chiamante implementa l'interfaccia [IMapToken](imaptoken-interface.md) (tramite [IMetaDataEmit:: FileHandler](imetadataemit-sethandler-method.md) o [IMetaDataEmit:: merge](imetadataemit-merge-method.md)), eseguirà `GetSaveSize` due passaggi sui metadati per ottimizzarlo e comprimerlo. In caso contrario, non viene eseguita alcuna ottimizzazione.  
  
 Se viene eseguita l'ottimizzazione, il primo passaggio Ordina semplicemente le strutture dei metadati per ottimizzare le prestazioni delle ricerche in fase di importazione. Questo passaggio comporta in genere lo spostamento dei record, con l'effetto collaterale che i token conservati dallo strumento per riferimento futuro vengono invalidati. I metadati non informano il chiamante di queste modifiche del token fino a dopo il secondo passaggio, tuttavia. Nel secondo passaggio vengono eseguite diverse ottimizzazioni destinate a ridurre le dimensioni complessive dei metadati, ad esempio l'ottimizzazione (associazione anticipata) `mdTypeRef` e `mdMemberRef` i token quando il riferimento è a un tipo o a un membro dichiarato nell'ambito dei metadati corrente. In questo passaggio viene eseguito un altro ciclo di mapping dei token. Dopo questo passaggio, il motore dei metadati invia una notifica al chiamante, tramite la relativa `IMapToken` interfaccia, di tutti i valori di token modificati.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataEmit](imetadataemit-interface.md)
- [Interfaccia IMetaDataEmit2](imetadataemit2-interface.md)
