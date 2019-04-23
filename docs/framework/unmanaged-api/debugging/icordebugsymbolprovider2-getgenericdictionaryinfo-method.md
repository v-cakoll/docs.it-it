---
title: Metodo ICorDebugSymbolProvider2::GetGenericDictionaryInfo
ms.date: 03/30/2017
ms.assetid: ba28fe4e-5491-4670-bff7-7fde572d7593
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f171af8dbfa4e812711e95e5587b314753cd9350
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59216821"
---
# <a name="icordebugsymbolprovider2getgenericdictionaryinfo-method"></a><span data-ttu-id="7ac30-102">Metodo ICorDebugSymbolProvider2::GetGenericDictionaryInfo</span><span class="sxs-lookup"><span data-stu-id="7ac30-102">ICorDebugSymbolProvider2::GetGenericDictionaryInfo Method</span></span>
<span data-ttu-id="7ac30-103">Recupera una mappa di dizionari generici.</span><span class="sxs-lookup"><span data-stu-id="7ac30-103">Retrieves a generic dictionary map.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ac30-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7ac30-104">Syntax</span></span>  
  
```  
HRESULT GetGenericDictionaryInfo(  
   [out] ICorDebugMemoryBuffer** ppMemoryBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7ac30-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7ac30-105">Parameters</span></span>  
 `ppMemoryBuffer`  
 <span data-ttu-id="7ac30-106">[out] Un puntatore all'indirizzo di un [ICorDebugMemoryBuffer](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md) oggetto contenente la mappa di dizionari generici.</span><span class="sxs-lookup"><span data-stu-id="7ac30-106">[out] A pointer to the address of an [ICorDebugMemoryBuffer](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md) object containing the generic dictionary map.</span></span> <span data-ttu-id="7ac30-107">Per altre informazioni, vedere la sezione Osservazioni.</span><span class="sxs-lookup"><span data-stu-id="7ac30-107">See the Remarks section for more information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7ac30-108">Note</span><span class="sxs-lookup"><span data-stu-id="7ac30-108">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7ac30-109">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="7ac30-109">This method is available with .NET Native only.</span></span>  
  
 <span data-ttu-id="7ac30-110">La mappa è costituita da due sezioni di primo livello:</span><span class="sxs-lookup"><span data-stu-id="7ac30-110">The map consists of two top-level sections:</span></span>  
  
-   <span data-ttu-id="7ac30-111">Oggetto [directory](#Directory) contenente gli indirizzi virtuali relativi (RVA) di tutti i dizionari inclusi nella mappa.</span><span class="sxs-lookup"><span data-stu-id="7ac30-111">A [directory](#Directory) containing the relative virtual addresses (RVA) of all dictionaries included in this map.</span></span>  
  
-   <span data-ttu-id="7ac30-112">Un byte allineato [heap](#Heap) che contiene informazioni sulle creazione di istanze di oggetti.</span><span class="sxs-lookup"><span data-stu-id="7ac30-112">A byte-aligned [heap](#Heap) that contains object instantiation information.</span></span> <span data-ttu-id="7ac30-113">Viene avviato immediatamente dopo l'ultima voce di directory.</span><span class="sxs-lookup"><span data-stu-id="7ac30-113">It starts immediately after the last directory entry.</span></span>  
  
<a name="Directory"></a>   
## <a name="the-directory"></a><span data-ttu-id="7ac30-114">Directory</span><span class="sxs-lookup"><span data-stu-id="7ac30-114">The Directory</span></span>  
 <span data-ttu-id="7ac30-115">Ogni voce nella directory fa riferimento a un offset all'interno dell'heap, ovvero un offset relativo all'inizio dell'heap.</span><span class="sxs-lookup"><span data-stu-id="7ac30-115">Each entry in the directory refers to an offset inside the heap; that is, it is an offset that is relative to the start of the heap.</span></span> <span data-ttu-id="7ac30-116">Il valore delle singole voci non è necessariamente univoco. Più voci di directory possono puntare allo stesso offset nell'heap.</span><span class="sxs-lookup"><span data-stu-id="7ac30-116">The value of individual entries is not necessarily unique; it is possible for multiple directory entries to point to the same offset in the heap.</span></span>  
  
 <span data-ttu-id="7ac30-117">La parte directory della mappa di dizionari generici presenta la struttura seguente:</span><span class="sxs-lookup"><span data-stu-id="7ac30-117">The directory portion of the generic dictionary map has the following structure:</span></span>  
  
-   <span data-ttu-id="7ac30-118">I primi 4 byte contengono il numero di voci del dizionario, cioè il numero di indirizzi RVA (Relative Virtual Address) presenti nel dizionario.</span><span class="sxs-lookup"><span data-stu-id="7ac30-118">The first 4 bytes contains the number of dictionary entries (that is, the number of relative virtual addresses in the dictionary).</span></span> <span data-ttu-id="7ac30-119">Si farà riferimento a questo valore come *N*. Se viene impostato il bit significativo, le voci vengono organizzate in base all'indirizzo RVA (Relative Virtual Address) in ordine crescente.</span><span class="sxs-lookup"><span data-stu-id="7ac30-119">We will refer to this value as *N*. If the high bit is set, the entries are sorted by relative virtual address in ascending order.</span></span>  
  
-   <span data-ttu-id="7ac30-120">Il *N* seguono le voci di directory.</span><span class="sxs-lookup"><span data-stu-id="7ac30-120">The *N* directory entries follow.</span></span> <span data-ttu-id="7ac30-121">Ogni voce è costituita da 8 byte in due segmenti di 4 byte:</span><span class="sxs-lookup"><span data-stu-id="7ac30-121">Each entry consists of 8 bytes, in two 4-byte segments:</span></span>  
  
    -   <span data-ttu-id="7ac30-122">Byte 0 a 3: RVA; indirizzo virtuale relativo del dizionario.</span><span class="sxs-lookup"><span data-stu-id="7ac30-122">Bytes 0-3: RVA; the dictionary's relative virtual address.</span></span>  
  
    -   <span data-ttu-id="7ac30-123">Byte 4-7: Offset; un offset rispetto all'inizio dell'heap.</span><span class="sxs-lookup"><span data-stu-id="7ac30-123">Bytes 4-7: Offset; an offset relative to the start of the heap.</span></span>  
  
<a name="Heap"></a>   
## <a name="the-heap"></a><span data-ttu-id="7ac30-124">Heap</span><span class="sxs-lookup"><span data-stu-id="7ac30-124">The Heap</span></span>  
 <span data-ttu-id="7ac30-125">È possibile calcolare le dimensioni dell'heap tramite un lettore del flusso, sottraendo la lunghezza del flusso dalle dimensioni della directory + 4.</span><span class="sxs-lookup"><span data-stu-id="7ac30-125">The heap’s size can be computed by a stream reader by subtracting the length of the stream from the directory size + 4.</span></span> <span data-ttu-id="7ac30-126">In altre parole:</span><span class="sxs-lookup"><span data-stu-id="7ac30-126">In other words:</span></span>  
  
```  
Heap Size = Stream.Length – (Directory Size + 4)  
```  
  
 <span data-ttu-id="7ac30-127">dove le dimensioni della directory corrispondono a `N * 8`.</span><span class="sxs-lookup"><span data-stu-id="7ac30-127">where the directory size is `N * 8`.</span></span>  
  
 <span data-ttu-id="7ac30-128">Il formato di ogni elemento delle informazioni sull'heap è il seguente:</span><span class="sxs-lookup"><span data-stu-id="7ac30-128">The format for each instantiation information item on the heap is:</span></span>  
  
-   <span data-ttu-id="7ac30-129">Lunghezza in byte di questo elemento di informazioni sulla creazione di un'istanza, nel formato di metadati ECMA compresso.</span><span class="sxs-lookup"><span data-stu-id="7ac30-129">The length of this instantiation information item in bytes in compressed ECMA metadata format.</span></span> <span data-ttu-id="7ac30-130">Il valore esclude le informazioni sulla lunghezza.</span><span class="sxs-lookup"><span data-stu-id="7ac30-130">The value excludes this length information.</span></span>  
  
-   <span data-ttu-id="7ac30-131">Il numero di tipi di istanza generica, oppure *T*, nel formato di metadati ECMA compresso.</span><span class="sxs-lookup"><span data-stu-id="7ac30-131">The number of generic instantiation types, or *T*, in compressed ECMA metadata format.</span></span>  
  
-   <span data-ttu-id="7ac30-132">*T* tipi, ognuno rappresentato nel formato di firma di tipo ECMA.</span><span class="sxs-lookup"><span data-stu-id="7ac30-132">*T* types, each represented in ECMA type signature format.</span></span>  
  
 <span data-ttu-id="7ac30-133">L'inclusione della lunghezza per ogni elemento dell'heap consente un ordinamento semplice della sezione della directory senza influire sull'heap.</span><span class="sxs-lookup"><span data-stu-id="7ac30-133">The inclusion of the length for each heap element enables simple sorting of the directory section without affecting the heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ac30-134">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7ac30-134">Requirements</span></span>  
 <span data-ttu-id="7ac30-135">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7ac30-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ac30-136">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7ac30-136">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7ac30-137">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7ac30-137">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7ac30-138">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ac30-138">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ac30-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7ac30-139">See also</span></span>

- [<span data-ttu-id="7ac30-140">Interfaccia ICorDebugSymbolProvider2</span><span class="sxs-lookup"><span data-stu-id="7ac30-140">ICorDebugSymbolProvider2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider2-interface.md)
- [<span data-ttu-id="7ac30-141">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="7ac30-141">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
