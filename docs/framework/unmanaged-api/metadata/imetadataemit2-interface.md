---
title: Interfaccia IMetaDataEmit2
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2
helpviewer_keywords:
- IMetaDataEmit2 interface [.NET Framework metadata]
ms.assetid: 866dc96b-bbfc-4c0f-80c2-38ce93072106
topic_type:
- apiref
ms.openlocfilehash: 5a232f30da8812c6f3bd94647d74151312a8593b
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84493039"
---
# <a name="imetadataemit2-interface"></a><span data-ttu-id="dae10-102">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="dae10-102">IMetaDataEmit2 Interface</span></span>
<span data-ttu-id="dae10-103">Estende l'interfaccia [IMetaDataEmit](imetadataemit-interface.md) principalmente per consentire l'utilizzo di tipi generici.</span><span class="sxs-lookup"><span data-stu-id="dae10-103">Extends the [IMetaDataEmit](imetadataemit-interface.md) interface primarily to provide the ability to work with generic types.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="dae10-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="dae10-104">Methods</span></span>  
  
|<span data-ttu-id="dae10-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="dae10-105">Method</span></span>|<span data-ttu-id="dae10-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dae10-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="dae10-107">Metodo DefineGenericParam</span><span class="sxs-lookup"><span data-stu-id="dae10-107">DefineGenericParam Method</span></span>](imetadataemit2-definegenericparam-method.md)|<span data-ttu-id="dae10-108">Crea una definizione per un parametro di tipo generico e ottiene un token per il parametro di tipo generico.</span><span class="sxs-lookup"><span data-stu-id="dae10-108">Creates a definition for a generic type parameter, and gets a token to that generic type parameter.</span></span>|  
|[<span data-ttu-id="dae10-109">Metodo DefineMethodSpec</span><span class="sxs-lookup"><span data-stu-id="dae10-109">DefineMethodSpec Method</span></span>](imetadataemit2-definemethodspec-method.md)|<span data-ttu-id="dae10-110">Crea un'istanza generica di un metodo e ottiene un token per la definizione.</span><span class="sxs-lookup"><span data-stu-id="dae10-110">Creates a generic instance of a method, and gets a token to the definition.</span></span>|  
|[<span data-ttu-id="dae10-111">Metodo GetDeltaSaveSize</span><span class="sxs-lookup"><span data-stu-id="dae10-111">GetDeltaSaveSize Method</span></span>](imetadataemit2-getdeltasavesize-method.md)|<span data-ttu-id="dae10-112">Ottiene un valore che indica la differenza tra le dimensioni dei dati necessari per esprimere le modifiche per la sessione di modifica e continuazione corrente.</span><span class="sxs-lookup"><span data-stu-id="dae10-112">Gets a value indicating the difference in size of the data that is required to express the changes for the current edit-and-continue session.</span></span>|  
|[<span data-ttu-id="dae10-113">Metodo ResetENCLog</span><span class="sxs-lookup"><span data-stu-id="dae10-113">ResetENCLog Method</span></span>](imetadataemit2-resetenclog-method.md)|<span data-ttu-id="dae10-114">Reimposta il log di modifica e continuazione e avvia una nuova sessione.</span><span class="sxs-lookup"><span data-stu-id="dae10-114">Resets the edit-and-continue log and starts a new session.</span></span>|  
|[<span data-ttu-id="dae10-115">Metodo SaveDelta</span><span class="sxs-lookup"><span data-stu-id="dae10-115">SaveDelta Method</span></span>](imetadataemit2-savedelta-method.md)|<span data-ttu-id="dae10-116">Salva le modifiche dalla sessione di modifica e continuazione corrente nel file specificato.</span><span class="sxs-lookup"><span data-stu-id="dae10-116">Saves changes from the current edit-and-continue session to the specified file.</span></span>|  
|[<span data-ttu-id="dae10-117">Metodo SaveDeltaToMemory</span><span class="sxs-lookup"><span data-stu-id="dae10-117">SaveDeltaToMemory Method</span></span>](imetadataemit2-savedeltatomemory-method.md)|<span data-ttu-id="dae10-118">Salva le modifiche dalla sessione di modifica e continuazione corrente alla memoria.</span><span class="sxs-lookup"><span data-stu-id="dae10-118">Saves changes from the current edit-and-continue session to memory.</span></span>|  
|[<span data-ttu-id="dae10-119">Metodo SaveDeltaToStream</span><span class="sxs-lookup"><span data-stu-id="dae10-119">SaveDeltaToStream Method</span></span>](imetadataemit2-savedeltatostream-method.md)|<span data-ttu-id="dae10-120">Salva le modifiche dalla sessione di modifica e continuazione corrente nel flusso specificato.</span><span class="sxs-lookup"><span data-stu-id="dae10-120">Saves changes from the current edit-and-continue session to the specified stream.</span></span>|  
|[<span data-ttu-id="dae10-121">Metodo SetGenericParamProps</span><span class="sxs-lookup"><span data-stu-id="dae10-121">SetGenericParamProps Method</span></span>](imetadataemit2-setgenericparamprops-method.md)|<span data-ttu-id="dae10-122">Imposta i valori delle proprietà per la definizione di parametro generico a cui fa riferimento il token specificato.</span><span class="sxs-lookup"><span data-stu-id="dae10-122">Sets property values for the generic parameter definition referenced by the specified token.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="dae10-123">Requisiti</span><span class="sxs-lookup"><span data-stu-id="dae10-123">Requirements</span></span>  
 <span data-ttu-id="dae10-124">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dae10-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dae10-125">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="dae10-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="dae10-126">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="dae10-126">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="dae10-127">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dae10-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dae10-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dae10-128">See also</span></span>

- [<span data-ttu-id="dae10-129">Interfacce di metadati</span><span class="sxs-lookup"><span data-stu-id="dae10-129">Metadata Interfaces</span></span>](metadata-interfaces.md)
- [<span data-ttu-id="dae10-130">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="dae10-130">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
