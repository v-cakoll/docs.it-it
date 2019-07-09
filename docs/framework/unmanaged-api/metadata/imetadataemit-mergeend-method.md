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
ms.openlocfilehash: 99c1decf27685f027d6baa8412bf20fdf693d161
ms.sourcegitcommit: d6e27023aeaffc4b5a3cb4b88685018d6284ada4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2019
ms.locfileid: "67664013"
---
# <a name="imetadataemitmergeend-method"></a><span data-ttu-id="4e1bd-102">Metodo IMetaDataEmit::MergeEnd</span><span class="sxs-lookup"><span data-stu-id="4e1bd-102">IMetaDataEmit::MergeEnd Method</span></span>

<span data-ttu-id="4e1bd-103">Unisce in corrente ambito tutti gli ambiti di metadati specificati da uno o più chiamate precedenti al [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md).</span><span class="sxs-lookup"><span data-stu-id="4e1bd-103">Merges into the current scope all the metadata scopes specified by one or more prior calls to [IMetaDataEmit::Merge](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md).</span></span>

## <a name="syntax"></a><span data-ttu-id="4e1bd-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4e1bd-104">Syntax</span></span>

```cpp
HRESULT MergeEnd ();
```

## <a name="parameters"></a><span data-ttu-id="4e1bd-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4e1bd-105">Parameters</span></span>

<span data-ttu-id="4e1bd-106">Questo metodo non accetta parametri.</span><span class="sxs-lookup"><span data-stu-id="4e1bd-106">This method takes no parameters.</span></span>

## <a name="remarks"></a><span data-ttu-id="4e1bd-107">Note</span><span class="sxs-lookup"><span data-stu-id="4e1bd-107">Remarks</span></span>

<span data-ttu-id="4e1bd-108">Questa routine genera l'unione effettiva dei metadati, di tutti gli ambiti specificati dalle precedenti chiamate a importare `IMetaDataEmit::Merge`, nell'ambito di output corrente.</span><span class="sxs-lookup"><span data-stu-id="4e1bd-108">This routine triggers the actual merge of metadata, of all import scopes specified by preceding calls to `IMetaDataEmit::Merge`, into the current output scope.</span></span>

<span data-ttu-id="4e1bd-109">Per l'unione si applicano condizioni speciali seguenti:</span><span class="sxs-lookup"><span data-stu-id="4e1bd-109">The following special conditions apply to the merge:</span></span>

- <span data-ttu-id="4e1bd-110">Un identificatore di versione del modulo (MVID, Module) non viene mai importato, perché è univoco per i metadati nell'ambito di importazione.</span><span class="sxs-lookup"><span data-stu-id="4e1bd-110">A module version identifier (MVID) is never imported, because it is unique to the metadata in the import scope.</span></span>

- <span data-ttu-id="4e1bd-111">Nessuna proprietà a livello di modulo esistente viene sovrascritti.</span><span class="sxs-lookup"><span data-stu-id="4e1bd-111">No existing module-wide properties are overwritten.</span></span>

  <span data-ttu-id="4e1bd-112">Se le proprietà dei moduli sono già state impostate per l'ambito corrente, non le proprietà dei moduli vengono importati.</span><span class="sxs-lookup"><span data-stu-id="4e1bd-112">If module properties were already set for the current scope, no module properties are imported.</span></span> <span data-ttu-id="4e1bd-113">Tuttavia, se le proprietà dei moduli non sono state impostate nell'ambito corrente, vengono importati solo una volta, quando vengono rilevati prima di tutto.</span><span class="sxs-lookup"><span data-stu-id="4e1bd-113">However, if module properties have not been set in the current scope, they are imported only once, when they are first encountered.</span></span> <span data-ttu-id="4e1bd-114">Se le proprietà del modulo vengono rilevati anche in questo caso, vengono duplicati.</span><span class="sxs-lookup"><span data-stu-id="4e1bd-114">If those module properties are encountered again, they are duplicates.</span></span> <span data-ttu-id="4e1bd-115">Se vengono confrontati i valori di tutte le proprietà di modulo (eccetto MVID) e non vengono trovati duplicati, viene generato un errore.</span><span class="sxs-lookup"><span data-stu-id="4e1bd-115">If the values of all module properties (except MVID) are compared and no duplicates are found, an error is raised.</span></span>

- <span data-ttu-id="4e1bd-116">Per le definizioni dei tipi (`TypeDef`), duplicati non vengono uniti nell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="4e1bd-116">For type definitions (`TypeDef`), no duplicates are merged into the current scope.</span></span> <span data-ttu-id="4e1bd-117">`TypeDef` gli oggetti vengono controllati per rilevare eventuali duplicati *nome completo dell'oggetto* + *GUID* + *numero di versione*.</span><span class="sxs-lookup"><span data-stu-id="4e1bd-117">`TypeDef` objects are checked for duplicates against each *fully-qualified object name* + *GUID* + *version number*.</span></span> <span data-ttu-id="4e1bd-118">Se viene trovata una corrispondenza nel nome o GUID e uno degli altri due elementi è diverso, viene generato un errore.</span><span class="sxs-lookup"><span data-stu-id="4e1bd-118">If there is a match on either name or GUID, and any of the other two elements is different, an error is raised.</span></span> <span data-ttu-id="4e1bd-119">In caso contrario, se corrisponde a tutti i tre elementi, `MergeEnd` esegue un controllo superficiale per assicurarsi che le voci sono effettivamente duplicati; in caso contrario, viene generato un errore.</span><span class="sxs-lookup"><span data-stu-id="4e1bd-119">Otherwise, if all three items match, `MergeEnd` does a cursory check to ensure the entries are indeed duplicates; if not, an error is raised.</span></span> <span data-ttu-id="4e1bd-120">Questo controllo superficiale Cerca:</span><span class="sxs-lookup"><span data-stu-id="4e1bd-120">This cursory check looks for:</span></span>

  - <span data-ttu-id="4e1bd-121">Le stesse dichiarazioni di membro, che si verificano nello stesso ordine.</span><span class="sxs-lookup"><span data-stu-id="4e1bd-121">The same member declarations, occurring in the same order.</span></span> <span data-ttu-id="4e1bd-122">I membri contrassegnati come `mdPrivateScope` (vedere la [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) enumerazione) non sono inclusi in questo controllo; vengono unite in modo speciale.</span><span class="sxs-lookup"><span data-stu-id="4e1bd-122">Members that are flagged as `mdPrivateScope` (see the [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) enumeration) are not included in this check; they are merged specially.</span></span>

  - <span data-ttu-id="4e1bd-123">Il layout della classe stessa.</span><span class="sxs-lookup"><span data-stu-id="4e1bd-123">The same class layout.</span></span>

  <span data-ttu-id="4e1bd-124">Ciò significa che un `TypeDef` oggetto deve essere sempre completamente e coerente definito in tutti gli ambiti di metadati in cui è dichiarata; se le implementazioni di membri (per una classe) vengono distribuite tra più unità di compilazione, la definizione completa viene considerato uguale a presente in tutti gli ambiti e non incrementale per ogni ambito.</span><span class="sxs-lookup"><span data-stu-id="4e1bd-124">This means that a `TypeDef` object must always be fully and consistently defined in every metadata scope in which it is declared; if its member implementations (for a class) are spread across multiple compilation units, the full definition is assumed to be present in every scope and not incremental to each scope.</span></span> <span data-ttu-id="4e1bd-125">Ad esempio, se i nomi dei parametri sono rilevanti per il contratto, essi devono essere inviati allo stesso modo in ogni ambito. Se non sono rilevanti, essi non deve essere generati nei metadati.</span><span class="sxs-lookup"><span data-stu-id="4e1bd-125">For example, if parameter names are relevant to the contract, they must be emitted the same way into every scope; if they are not relevant, they should not be emitted into metadata.</span></span>

  <span data-ttu-id="4e1bd-126">L'eccezione è che un `TypeDef` oggetto può avere membri incrementali contrassegnati come `mdPrivateScope`.</span><span class="sxs-lookup"><span data-stu-id="4e1bd-126">The exception is that a `TypeDef` object can have incremental members flagged as `mdPrivateScope`.</span></span> <span data-ttu-id="4e1bd-127">Quando viene rilevato, `MergeEnd` in modo incrementale li aggiunge all'ambito corrente senza tener conto per i duplicati.</span><span class="sxs-lookup"><span data-stu-id="4e1bd-127">On encountering these, `MergeEnd` incrementally adds them to the current scope without regard for duplicates.</span></span> <span data-ttu-id="4e1bd-128">Poiché il compilatore riconosce l'ambito privato, il compilatore deve essere responsabile per l'applicazione di regole.</span><span class="sxs-lookup"><span data-stu-id="4e1bd-128">Because the compiler understands the private scope, the compiler must be responsible for enforcing rules.</span></span>

- <span data-ttu-id="4e1bd-129">Indirizzi virtuali relativi (RVA) non vengono importati o uniti. è previsto il compilatore di generare nuovamente tali informazioni.</span><span class="sxs-lookup"><span data-stu-id="4e1bd-129">Relative virtual addresses (RVAs) are not imported or merged; the compiler is expected to re-emit this information.</span></span>

- <span data-ttu-id="4e1bd-130">Gli attributi personalizzati vengono uniti solo quando l'elemento a cui sono associati viene unito.</span><span class="sxs-lookup"><span data-stu-id="4e1bd-130">Custom attributes are merged only when the item to which they are attached is merged.</span></span> <span data-ttu-id="4e1bd-131">Attributi personalizzati associati a una classe vengono uniti, ad esempio, quando la classe viene prima rilevata.</span><span class="sxs-lookup"><span data-stu-id="4e1bd-131">For example, custom attributes associated with a class are merged when the class is first encountered.</span></span> <span data-ttu-id="4e1bd-132">Se gli attributi personalizzati sono associati a un `TypeDef` o `MemberDef` specifico all'unità di compilazione (ad esempio, il timestamp di una compilazione di membri), non vengono unite e spetta al compilatore di rimuovere o aggiornare tali metadati.</span><span class="sxs-lookup"><span data-stu-id="4e1bd-132">If custom attributes are associated with a `TypeDef` or `MemberDef` that is specific to the compilation unit (such as the time stamp of a member compile), they are not merged and it is up to the compiler to remove or update such metadata.</span></span>

## <a name="requirements"></a><span data-ttu-id="4e1bd-133">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4e1bd-133">Requirements</span></span>

<span data-ttu-id="4e1bd-134">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4e1bd-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="4e1bd-135">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="4e1bd-135">**Header:** Cor.h</span></span>

<span data-ttu-id="4e1bd-136">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="4e1bd-136">**Library:** Used as a resource in MSCorEE.dll</span></span>

<span data-ttu-id="4e1bd-137">**Versioni di .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4e1bd-137">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="4e1bd-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4e1bd-138">See also</span></span>

- [<span data-ttu-id="4e1bd-139">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="4e1bd-139">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="4e1bd-140">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="4e1bd-140">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
