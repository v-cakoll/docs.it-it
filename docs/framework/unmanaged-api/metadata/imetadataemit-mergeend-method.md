---
title: Metodo IMetaDataEmit::MergeEnd
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.MergeEnd
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::MergeEnd
helpviewer_keywords:
- MergeEnd method [.NET Framework metadata]
- IMetaDataEmit::MergeEnd method [.NET Framework metadata]
ms.assetid: 2d64315a-1af1-4c60-aedf-f8a781914aea
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b794a62a0ac0d253f1431be29b43101816dc7233
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33449442"
---
# <a name="imetadataemitmergeend-method"></a>Metodo IMetaDataEmit::MergeEnd
Unisce in corrente ambito tutti gli ambiti dei metadati specificati da uno o più chiamate precedenti a [IMetaDataEmit:: Merge](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md).  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT MergeEnd ();  
```  
  
#### <a name="parameters"></a>Parametri  
 Questo metodo non accetta parametri.  
  
## <a name="remarks"></a>Note  
 Questa routine genera l'effettiva unione dei metadati, di tutti gli ambiti specificati dalle precedenti chiamate a di importazione `IMetaDataEmit::Merge`, nell'ambito di output corrente.  
  
 Le condizioni speciali seguenti si applicano all'unione:  
  
-   Un identificatore di versione del modulo (MVID, Module) non viene mai importato, poiché è univoco per i metadati nell'ambito di importazione.  
  
-   Nessuna proprietà a livello di modulo esistente viene sovrascritti.  
  
     Se le proprietà dei moduli sono già state impostate per l'ambito corrente, non le proprietà dei moduli vengono importati. Tuttavia, se il modulo non è stato impostato nell'ambito corrente, vengono importati solo una volta, quando vengono rilevati prima. Se le proprietà del modulo vengono rilevate nuovamente, sono duplicati. Se vengono confrontati i valori di tutte le proprietà, tranne MVID, module e non vengono trovati duplicati, viene generato un errore.  
  
-   Per le definizioni di tipo (`TypeDef`), nessun duplicato viene unito all'ambito corrente. `TypeDef` per rilevare eventuali duplicati vengono controllati gli oggetti *nome completo dell'oggetto* + *GUID* + *numero di versione*. Se viene trovata una corrispondenza nel nome o il GUID e uno degli altri due elementi è diverso, viene generato un errore. In caso contrario, se tutti e tre gli elementi corrispondono, `MergeEnd` esegue un controllo superficiale per verificare che le voci siano veramente duplicati; in caso contrario, viene generato un errore. Cerca di questo controllo superficiale:  
  
    -   Le stesse dichiarazioni di membri, che si verificano nello stesso ordine. I membri contrassegnati come `mdPrivateScope` (vedere il [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) enumerazione) non sono inclusi in questo controllo, vengono unite in modo speciale.  
  
    -   Il layout della classe stessa.  
  
     Ciò significa che un `TypeDef` oggetto deve sempre essere completo e coerente definito in ogni ambito dei metadati in cui è dichiarata; se le implementazioni di membro (per una classe) sono suddivisi in più unità di compilazione, la definizione completa è considerato uguale a presente in tutti gli ambiti e non incrementale per ogni ambito. Ad esempio, se i nomi dei parametri sono rilevanti per il contratto, essi devono essere inviati allo stesso modo in ogni ambito. Se non sono rilevanti, essi non deve essere generati nei metadati.  
  
     L'eccezione è che un `TypeDef` oggetto può avere membri incrementali contrassegnati come `mdPrivateScope`. Quando viene rilevato, `MergeEnd` aggiunge in modo incrementale all'ambito corrente senza tenere conto dei duplicati. Poiché il compilatore riconosce l'ambito privato, il compilatore deve essere responsabile dell'applicazione delle regole.  
  
-   Indirizzi virtuali relativi (RVA) non vengono importati o uniti. è previsto che il compilatore generi nuovamente tali informazioni.  
  
-   Gli attributi personalizzati sono uniti solo quando l'elemento a cui sono associati viene unito. Attributi personalizzati associati a una classe, ad esempio, vengono uniti quando la classe viene prima rilevata. Se gli attributi personalizzati sono associati un `TypeDef` o `MemberDef` che è specifico dell'unità di compilazione (ad esempio, il timestamp di una compilazione di membri), non verranno uniti e in questo caso, il compilatore per rimuovere o aggiornare tali metadati.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** usata come risorsa in Mscoree. dll  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [Interfaccia IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
