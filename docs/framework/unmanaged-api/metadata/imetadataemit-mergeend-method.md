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
ms.openlocfilehash: 34ecfc2f01f22971e135358806adeea632e02f8b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448034"
---
# <a name="imetadataemitmergeend-method"></a><span data-ttu-id="6c646-102">Metodo IMetaDataEmit::MergeEnd</span><span class="sxs-lookup"><span data-stu-id="6c646-102">IMetaDataEmit::MergeEnd Method</span></span>

<span data-ttu-id="6c646-103">Esegue il merge nell'ambito corrente di tutti gli ambiti dei metadati specificati da una o più chiamate precedenti a [IMetaDataEmit:: merge](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md).</span><span class="sxs-lookup"><span data-stu-id="6c646-103">Merges into the current scope all the metadata scopes specified by one or more prior calls to [IMetaDataEmit::Merge](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md).</span></span>

## <a name="syntax"></a><span data-ttu-id="6c646-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6c646-104">Syntax</span></span>

```cppcpp
HRESULT MergeEnd ();
```

## <a name="parameters"></a><span data-ttu-id="6c646-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6c646-105">Parameters</span></span>

<span data-ttu-id="6c646-106">Questo metodo non accetta parametri.</span><span class="sxs-lookup"><span data-stu-id="6c646-106">This method takes no parameters.</span></span>

## <a name="remarks"></a><span data-ttu-id="6c646-107">Note</span><span class="sxs-lookup"><span data-stu-id="6c646-107">Remarks</span></span>

<span data-ttu-id="6c646-108">Questa routine attiva il merge effettivo dei metadati, di tutti gli ambiti di importazione specificati dalle chiamate precedenti a `IMetaDataEmit::Merge`nell'ambito di output corrente.</span><span class="sxs-lookup"><span data-stu-id="6c646-108">This routine triggers the actual merge of metadata, of all import scopes specified by preceding calls to `IMetaDataEmit::Merge`, into the current output scope.</span></span>

<span data-ttu-id="6c646-109">Per l'Unione si applicano le seguenti condizioni speciali:</span><span class="sxs-lookup"><span data-stu-id="6c646-109">The following special conditions apply to the merge:</span></span>

- <span data-ttu-id="6c646-110">Un identificatore della versione del modulo (MVID) non viene mai importato, perché è univoco per i metadati nell'ambito di importazione.</span><span class="sxs-lookup"><span data-stu-id="6c646-110">A module version identifier (MVID) is never imported, because it is unique to the metadata in the import scope.</span></span>

- <span data-ttu-id="6c646-111">Nessuna proprietà esistente a livello di modulo viene sovrascritta.</span><span class="sxs-lookup"><span data-stu-id="6c646-111">No existing module-wide properties are overwritten.</span></span>

  <span data-ttu-id="6c646-112">Se le proprietà del modulo sono già state impostate per l'ambito corrente, non vengono importate proprietà del modulo.</span><span class="sxs-lookup"><span data-stu-id="6c646-112">If module properties were already set for the current scope, no module properties are imported.</span></span> <span data-ttu-id="6c646-113">Tuttavia, se le proprietà del modulo non sono state impostate nell'ambito corrente, vengono importate una sola volta, quando vengono rilevate per la prima volta.</span><span class="sxs-lookup"><span data-stu-id="6c646-113">However, if module properties have not been set in the current scope, they are imported only once, when they are first encountered.</span></span> <span data-ttu-id="6c646-114">Se le proprietà del modulo vengono rilevate, si tratta di duplicati.</span><span class="sxs-lookup"><span data-stu-id="6c646-114">If those module properties are encountered again, they are duplicates.</span></span> <span data-ttu-id="6c646-115">Se vengono confrontati i valori di tutte le proprietà del modulo (ad eccezione di MVID) e non viene trovato alcun duplicato, viene generato un errore.</span><span class="sxs-lookup"><span data-stu-id="6c646-115">If the values of all module properties (except MVID) are compared and no duplicates are found, an error is raised.</span></span>

- <span data-ttu-id="6c646-116">Per le definizioni di tipo (`TypeDef`), nessun duplicato viene unito nell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="6c646-116">For type definitions (`TypeDef`), no duplicates are merged into the current scope.</span></span> <span data-ttu-id="6c646-117">viene verificata la presenza di duplicati per ogni *nome di oggetto* completo + *GUID* + *numero di versione*. `TypeDef`</span><span class="sxs-lookup"><span data-stu-id="6c646-117">`TypeDef` objects are checked for duplicates against each *fully-qualified object name* + *GUID* + *version number*.</span></span> <span data-ttu-id="6c646-118">Se esiste una corrispondenza con il nome o il GUID e uno degli altri due elementi è diverso, viene generato un errore.</span><span class="sxs-lookup"><span data-stu-id="6c646-118">If there is a match on either name or GUID, and any of the other two elements is different, an error is raised.</span></span> <span data-ttu-id="6c646-119">In caso contrario, se tutti e tre gli elementi corrispondono, `MergeEnd` esegue una verifica del cursore per verificare che le voci siano effettivamente duplicate; in caso contrario, viene generato un errore.</span><span class="sxs-lookup"><span data-stu-id="6c646-119">Otherwise, if all three items match, `MergeEnd` does a cursory check to ensure the entries are indeed duplicates; if not, an error is raised.</span></span> <span data-ttu-id="6c646-120">Questo controllo cursore Cerca:</span><span class="sxs-lookup"><span data-stu-id="6c646-120">This cursory check looks for:</span></span>

  - <span data-ttu-id="6c646-121">Stesse dichiarazioni di membri, che si verificano nello stesso ordine.</span><span class="sxs-lookup"><span data-stu-id="6c646-121">The same member declarations, occurring in the same order.</span></span> <span data-ttu-id="6c646-122">I membri contrassegnati come `mdPrivateScope` (vedere l'enumerazione [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) ) non sono inclusi in questo controllo. vengono uniti in modo specifico.</span><span class="sxs-lookup"><span data-stu-id="6c646-122">Members that are flagged as `mdPrivateScope` (see the [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) enumeration) are not included in this check; they are merged specially.</span></span>

  - <span data-ttu-id="6c646-123">Lo stesso layout di classe.</span><span class="sxs-lookup"><span data-stu-id="6c646-123">The same class layout.</span></span>

  <span data-ttu-id="6c646-124">Ciò significa che un oggetto `TypeDef` deve essere sempre definito in modo completo e coerente in ogni ambito dei metadati in cui è dichiarato; Se le implementazioni dei membri (per una classe) sono distribuite tra più unità di compilazione, si presuppone che la definizione completa sia presente in ogni ambito e non incrementale per ogni ambito.</span><span class="sxs-lookup"><span data-stu-id="6c646-124">This means that a `TypeDef` object must always be fully and consistently defined in every metadata scope in which it is declared; if its member implementations (for a class) are spread across multiple compilation units, the full definition is assumed to be present in every scope and not incremental to each scope.</span></span> <span data-ttu-id="6c646-125">Se, ad esempio, i nomi dei parametri sono rilevanti per il contratto, è necessario emetterli nello stesso modo in ogni ambito. Se non sono rilevanti, non devono essere emesse nei metadati.</span><span class="sxs-lookup"><span data-stu-id="6c646-125">For example, if parameter names are relevant to the contract, they must be emitted the same way into every scope; if they are not relevant, they should not be emitted into metadata.</span></span>

  <span data-ttu-id="6c646-126">L'eccezione è che un oggetto `TypeDef` può avere membri incrementali contrassegnati come `mdPrivateScope`.</span><span class="sxs-lookup"><span data-stu-id="6c646-126">The exception is that a `TypeDef` object can have incremental members flagged as `mdPrivateScope`.</span></span> <span data-ttu-id="6c646-127">In caso di rilevamento di questi elementi, `MergeEnd` aggiungerli in modo incrementale all'ambito corrente senza considerare i duplicati.</span><span class="sxs-lookup"><span data-stu-id="6c646-127">On encountering these, `MergeEnd` incrementally adds them to the current scope without regard for duplicates.</span></span> <span data-ttu-id="6c646-128">Poiché il compilatore riconosce l'ambito privato, il compilatore deve essere responsabile dell'applicazione di regole.</span><span class="sxs-lookup"><span data-stu-id="6c646-128">Because the compiler understands the private scope, the compiler must be responsible for enforcing rules.</span></span>

- <span data-ttu-id="6c646-129">Gli indirizzi virtuali relativi (RVA) non vengono importati o Uniti; si prevede che il compilatore emetta nuovamente queste informazioni.</span><span class="sxs-lookup"><span data-stu-id="6c646-129">Relative virtual addresses (RVAs) are not imported or merged; the compiler is expected to re-emit this information.</span></span>

- <span data-ttu-id="6c646-130">Gli attributi personalizzati vengono uniti solo quando l'elemento a cui sono collegati viene Unito.</span><span class="sxs-lookup"><span data-stu-id="6c646-130">Custom attributes are merged only when the item to which they are attached is merged.</span></span> <span data-ttu-id="6c646-131">Ad esempio, gli attributi personalizzati associati a una classe vengono uniti quando la classe viene rilevata per la prima volta.</span><span class="sxs-lookup"><span data-stu-id="6c646-131">For example, custom attributes associated with a class are merged when the class is first encountered.</span></span> <span data-ttu-id="6c646-132">Se gli attributi personalizzati sono associati a un `TypeDef` o `MemberDef` specifici dell'unità di compilazione, ad esempio il timestamp di una compilazione di un membro, non vengono Uniti e il compilatore deve rimuovere o aggiornare tali metadati.</span><span class="sxs-lookup"><span data-stu-id="6c646-132">If custom attributes are associated with a `TypeDef` or `MemberDef` that is specific to the compilation unit (such as the time stamp of a member compile), they are not merged and it is up to the compiler to remove or update such metadata.</span></span>

## <a name="requirements"></a><span data-ttu-id="6c646-133">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6c646-133">Requirements</span></span>

<span data-ttu-id="6c646-134">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6c646-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="6c646-135">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="6c646-135">**Header:** Cor.h</span></span>

<span data-ttu-id="6c646-136">**Libreria:** Usato come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="6c646-136">**Library:** Used as a resource in MSCorEE.dll</span></span>

<span data-ttu-id="6c646-137">**Versioni di .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6c646-137">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="6c646-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6c646-138">See also</span></span>

- [<span data-ttu-id="6c646-139">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="6c646-139">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="6c646-140">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="6c646-140">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
