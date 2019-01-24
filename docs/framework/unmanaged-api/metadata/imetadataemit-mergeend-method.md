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
ms.openlocfilehash: 45d85be4e4987e5a5234ca2d57c85a56f9f544bc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54657025"
---
# <a name="imetadataemitmergeend-method"></a>Metodo IMetaDataEmit::MergeEnd
Unisce in corrente ambito tutti gli ambiti di metadati specificati da uno o più chiamate precedenti al [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md).  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT MergeEnd ();  
```  
  
#### <a name="parameters"></a>Parametri  
 Questo metodo non accetta parametri.  
  
## <a name="remarks"></a>Note  
 Questa routine genera l'unione effettiva dei metadati, di tutti gli ambiti specificati dalle precedenti chiamate a importare `IMetaDataEmit::Merge`, nell'ambito di output corrente.  
  
 Per l'unione si applicano condizioni speciali seguenti:  
  
-   Un identificatore di versione del modulo (MVID, Module) non viene mai importato, perché è univoco per i metadati nell'ambito di importazione.  
  
-   Nessuna proprietà a livello di modulo esistente viene sovrascritti.  
  
     Se le proprietà dei moduli sono già state impostate per l'ambito corrente, non le proprietà dei moduli vengono importati. Tuttavia, se le proprietà dei moduli non sono state impostate nell'ambito corrente, vengono importati solo una volta, quando vengono rilevati prima di tutto. Se le proprietà del modulo vengono rilevati anche in questo caso, vengono duplicati. Se vengono confrontati i valori di tutte le proprietà di modulo (eccetto MVID) e non vengono trovati duplicati, viene generato un errore.  
  
-   Per le definizioni dei tipi (`TypeDef`), duplicati non vengono uniti nell'ambito corrente. `TypeDef` gli oggetti vengono controllati per rilevare eventuali duplicati *nome completo dell'oggetto* + *GUID* + *numero di versione*. Se viene trovata una corrispondenza nel nome o GUID e uno degli altri due elementi è diverso, viene generato un errore. In caso contrario, se corrisponde a tutti i tre elementi, `MergeEnd` esegue un controllo superficiale per assicurarsi che le voci sono effettivamente duplicati; in caso contrario, viene generato un errore. Questo controllo superficiale Cerca:  
  
    -   Le stesse dichiarazioni di membro, che si verificano nello stesso ordine. I membri contrassegnati come `mdPrivateScope` (vedere la [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) enumerazione) non sono inclusi in questo controllo; vengono unite in modo speciale.  
  
    -   Il layout della classe stessa.  
  
     Ciò significa che un `TypeDef` oggetto deve essere sempre completamente e coerente definito in tutti gli ambiti di metadati in cui è dichiarata; se le implementazioni di membri (per una classe) vengono distribuite tra più unità di compilazione, la definizione completa viene considerato uguale a presente in tutti gli ambiti e non incrementale per ogni ambito. Ad esempio, se i nomi dei parametri sono rilevanti per il contratto, essi devono essere inviati allo stesso modo in ogni ambito. Se non sono rilevanti, essi non deve essere generati nei metadati.  
  
     L'eccezione è che un `TypeDef` oggetto può avere membri incrementali contrassegnati come `mdPrivateScope`. Quando viene rilevato, `MergeEnd` in modo incrementale li aggiunge all'ambito corrente senza tener conto per i duplicati. Poiché il compilatore riconosce l'ambito privato, il compilatore deve essere responsabile per l'applicazione di regole.  
  
-   Indirizzi virtuali relativi (RVA) non vengono importati o uniti. è previsto il compilatore di generare nuovamente tali informazioni.  
  
-   Gli attributi personalizzati vengono uniti solo quando l'elemento a cui sono associati viene unito. Attributi personalizzati associati a una classe vengono uniti, ad esempio, quando la classe viene prima rilevata. Se gli attributi personalizzati sono associati a un `TypeDef` o `MemberDef` specifico all'unità di compilazione (ad esempio, il timestamp di una compilazione di membri), non vengono unite e spetta al compilatore di rimuovere o aggiornare tali metadati.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [Interfaccia IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
