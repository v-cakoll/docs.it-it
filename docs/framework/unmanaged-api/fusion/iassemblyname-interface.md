---
title: Interfaccia IAssemblyName
ms.date: 03/30/2017
api_name:
- IAssemblyName
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName
helpviewer_keywords:
- IAssemblyName interface [.NET Framework fusion]
ms.assetid: f7f8e605-6b67-4151-936f-f04ecd671d90
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: aee9b986c1e26c1b2e34dac7151a00172451bbad
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796556"
---
# <a name="iassemblyname-interface"></a><span data-ttu-id="75403-102">Interfaccia IAssemblyName</span><span class="sxs-lookup"><span data-stu-id="75403-102">IAssemblyName Interface</span></span>
<span data-ttu-id="75403-103">Fornisce metodi per la descrizione e l'utilizzo dell'identità univoca di un assembly.</span><span class="sxs-lookup"><span data-stu-id="75403-103">Provides methods for describing and working with an assembly's unique identity.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="75403-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="75403-104">Methods</span></span>  
  
|<span data-ttu-id="75403-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="75403-105">Method</span></span>|<span data-ttu-id="75403-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="75403-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="75403-107">Metodo Clone</span><span class="sxs-lookup"><span data-stu-id="75403-107">Clone Method</span></span>](iassemblyname-clone-method.md)|<span data-ttu-id="75403-108">Crea una copia superficiale dell' `IAssemblyName` oggetto.</span><span class="sxs-lookup"><span data-stu-id="75403-108">Creates a shallow copy of this `IAssemblyName` object.</span></span>|  
|[<span data-ttu-id="75403-109">Metodo Finalize</span><span class="sxs-lookup"><span data-stu-id="75403-109">Finalize Method</span></span>](iassemblyname-finalize-method.md)|<span data-ttu-id="75403-110">Consente a `IAssemblyName` questo oggetto di rilasciare risorse ed eseguire altre operazioni di pulizia prima che venga chiamato il relativo distruttore.</span><span class="sxs-lookup"><span data-stu-id="75403-110">Allows this `IAssemblyName` object to release resources and perform other cleanup operations before its destructor is called.</span></span>|  
|[<span data-ttu-id="75403-111">Metodo GetDisplayName</span><span class="sxs-lookup"><span data-stu-id="75403-111">GetDisplayName Method</span></span>](iassemblyname-getdisplayname-method.md)|<span data-ttu-id="75403-112">Ottiene il nome leggibile dell'assembly a cui fa riferimento questo `IAssemblyName` oggetto.</span><span class="sxs-lookup"><span data-stu-id="75403-112">Gets the human-readable name of the assembly referenced by this `IAssemblyName` object.</span></span>|  
|[<span data-ttu-id="75403-113">Metodo GetName</span><span class="sxs-lookup"><span data-stu-id="75403-113">GetName Method</span></span>](iassemblyname-getname-method.md)|<span data-ttu-id="75403-114">Ottiene il nome semplice e non crittografato dell'assembly a cui fa riferimento `IAssemblyName` questo oggetto.</span><span class="sxs-lookup"><span data-stu-id="75403-114">Gets the simple, unencrypted name of the assembly referenced by this `IAssemblyName` object.</span></span>|  
|[<span data-ttu-id="75403-115">Metodo GetProperty</span><span class="sxs-lookup"><span data-stu-id="75403-115">GetProperty Method</span></span>](iassemblyname-getproperty-method.md)|<span data-ttu-id="75403-116">Ottiene un puntatore alla proprietà a cui fa riferimento l'oggetto `PropertyId`specificato.</span><span class="sxs-lookup"><span data-stu-id="75403-116">Gets a pointer to the property referenced by the specified `PropertyId`.</span></span>|  
|[<span data-ttu-id="75403-117">Metodo GetVersion</span><span class="sxs-lookup"><span data-stu-id="75403-117">GetVersion Method</span></span>](iassemblyname-getversion-method.md)|<span data-ttu-id="75403-118">Ottiene le informazioni sulla versione per l'assembly a cui fa `IAssemblyName` riferimento questo oggetto.</span><span class="sxs-lookup"><span data-stu-id="75403-118">Gets the version information for the assembly referenced by this `IAssemblyName` object.</span></span>|  
|[<span data-ttu-id="75403-119">Metodo IsEqual</span><span class="sxs-lookup"><span data-stu-id="75403-119">IsEqual Method</span></span>](iassemblyname-isequal-method.md)|<span data-ttu-id="75403-120">Determina se un oggetto `IAssemblyName` specificato è uguale `IAssemblyName`all'oggetto, in base ai flag di confronto specificati.</span><span class="sxs-lookup"><span data-stu-id="75403-120">Determines whether a specified `IAssemblyName` object is equal to this `IAssemblyName`, based on the specified comparison flags.</span></span>|  
|[<span data-ttu-id="75403-121">Metodo SetProperty</span><span class="sxs-lookup"><span data-stu-id="75403-121">SetProperty Method</span></span>](iassemblyname-setproperty-method.md)|<span data-ttu-id="75403-122">Imposta il valore della proprietà a cui fa riferimento l'oggetto `PropertyId`specificato.</span><span class="sxs-lookup"><span data-stu-id="75403-122">Sets the value of the property referenced by the specified `PropertyId`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="75403-123">Requisiti</span><span class="sxs-lookup"><span data-stu-id="75403-123">Requirements</span></span>  
 <span data-ttu-id="75403-124">**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="75403-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="75403-125">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="75403-125">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="75403-126">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="75403-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75403-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="75403-127">See also</span></span>

- [<span data-ttu-id="75403-128">Interfacce Fusion</span><span class="sxs-lookup"><span data-stu-id="75403-128">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="75403-129">Interfaccia IAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="75403-129">IAssemblyEnum Interface</span></span>](iassemblyenum-interface.md)
