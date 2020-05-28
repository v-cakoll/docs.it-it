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
ms.openlocfilehash: feb81b86190f953b50f43f244f4e58a0a482f86e
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84003919"
---
# <a name="imetadataemitmergeend-method"></a>Metodo IMetaDataEmit::MergeEnd

Esegue il merge nell'ambito corrente di tutti gli ambiti dei metadati specificati da una o più chiamate precedenti a [IMetaDataEmit:: merge](imetadataemit-merge-method.md).

## <a name="syntax"></a>Sintassi

```cppcpp
HRESULT MergeEnd ();
```

## <a name="parameters"></a>Parametri

Questo metodo non accetta parametri.

## <a name="remarks"></a>Commenti

Questa routine attiva il merge effettivo dei metadati, di tutti gli ambiti di importazione specificati dalle chiamate precedenti a `IMetaDataEmit::Merge` , nell'ambito di output corrente.

Per l'Unione si applicano le seguenti condizioni speciali:

- Un identificatore della versione del modulo (MVID) non viene mai importato, perché è univoco per i metadati nell'ambito di importazione.

- Nessuna proprietà esistente a livello di modulo viene sovrascritta.

  Se le proprietà del modulo sono già state impostate per l'ambito corrente, non vengono importate proprietà del modulo. Tuttavia, se le proprietà del modulo non sono state impostate nell'ambito corrente, vengono importate una sola volta, quando vengono rilevate per la prima volta. Se le proprietà del modulo vengono rilevate, si tratta di duplicati. Se vengono confrontati i valori di tutte le proprietà del modulo (ad eccezione di MVID) e non viene trovato alcun duplicato, viene generato un errore.

- Per le definizioni di tipo ( `TypeDef` ), nessun duplicato viene unito nell'ambito corrente. `TypeDef`viene verificata la presenza di duplicati in base al numero di versione GUID del *nome di oggetto completo*  +  *GUID*  +  *version number*. Se esiste una corrispondenza con il nome o il GUID e uno degli altri due elementi è diverso, viene generato un errore. In caso contrario, se tutti e tre gli elementi corrispondono, `MergeEnd` esegue un controllo cursore per verificare che le voci siano effettivamente duplicate; in caso contrario, viene generato un errore. Questo controllo cursore Cerca:

  - Stesse dichiarazioni di membri, che si verificano nello stesso ordine. I membri contrassegnati come `mdPrivateScope` (vedere l'enumerazione [CorMethodAttr](cormethodattr-enumeration.md) ) non sono inclusi in questo controllo. vengono uniti in modo specifico.

  - Lo stesso layout di classe.

  Ciò significa che un `TypeDef` oggetto deve essere sempre definito in modo completo e coerente in ogni ambito di metadati in cui è dichiarato. se le relative implementazioni dei membri (per una classe) sono distribuite tra più unità di compilazione, la definizione completa si presuppone che sia presente in ogni ambito e non incrementale per ogni ambito. Se, ad esempio, i nomi dei parametri sono rilevanti per il contratto, è necessario emetterli nello stesso modo in ogni ambito. Se non sono rilevanti, non devono essere emesse nei metadati.

  L'eccezione è che un `TypeDef` oggetto può avere membri incrementali contrassegnati come `mdPrivateScope` . Quando si verificano questi elementi, `MergeEnd` li aggiunge all'ambito corrente senza considerare i duplicati. Poiché il compilatore riconosce l'ambito privato, il compilatore deve essere responsabile dell'applicazione di regole.

- Gli indirizzi virtuali relativi (RVA) non vengono importati o Uniti; si prevede che il compilatore emetta nuovamente queste informazioni.

- Gli attributi personalizzati vengono uniti solo quando l'elemento a cui sono collegati viene Unito. Ad esempio, gli attributi personalizzati associati a una classe vengono uniti quando la classe viene rilevata per la prima volta. Se gli attributi personalizzati sono associati a un oggetto `TypeDef` o `MemberDef` specifico dell'unità di compilazione, ad esempio il timestamp di una compilazione di un membro, non vengono Uniti e il compilatore deve rimuovere o aggiornare tali metadati.

## <a name="requirements"></a>Requisiti

**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).

**Intestazione:** Cor. h

**Libreria:** Usato come risorsa in MSCorEE. dll

**Versioni .NET Framework:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]

## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataEmit](imetadataemit-interface.md)
- [Interfaccia IMetaDataEmit2](imetadataemit2-interface.md)
