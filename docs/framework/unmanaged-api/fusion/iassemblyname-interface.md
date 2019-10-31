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
ms.openlocfilehash: de49d66667033dfc6918b139f90cd5523661597f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134322"
---
# <a name="iassemblyname-interface"></a><span data-ttu-id="c4b1a-102">Interfaccia IAssemblyName</span><span class="sxs-lookup"><span data-stu-id="c4b1a-102">IAssemblyName Interface</span></span>
<span data-ttu-id="c4b1a-103">Fornisce metodi per la descrizione e l'utilizzo dell'identità univoca di un assembly.</span><span class="sxs-lookup"><span data-stu-id="c4b1a-103">Provides methods for describing and working with an assembly's unique identity.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c4b1a-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="c4b1a-104">Methods</span></span>  
  
|<span data-ttu-id="c4b1a-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="c4b1a-105">Method</span></span>|<span data-ttu-id="c4b1a-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c4b1a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c4b1a-107">Metodo Clone</span><span class="sxs-lookup"><span data-stu-id="c4b1a-107">Clone Method</span></span>](iassemblyname-clone-method.md)|<span data-ttu-id="c4b1a-108">Crea una copia superficiale di questo oggetto `IAssemblyName`.</span><span class="sxs-lookup"><span data-stu-id="c4b1a-108">Creates a shallow copy of this `IAssemblyName` object.</span></span>|  
|[<span data-ttu-id="c4b1a-109">Metodo Finalize</span><span class="sxs-lookup"><span data-stu-id="c4b1a-109">Finalize Method</span></span>](iassemblyname-finalize-method.md)|<span data-ttu-id="c4b1a-110">Consente a questo oggetto `IAssemblyName` di rilasciare risorse ed eseguire altre operazioni di pulizia prima che venga chiamato il relativo distruttore.</span><span class="sxs-lookup"><span data-stu-id="c4b1a-110">Allows this `IAssemblyName` object to release resources and perform other cleanup operations before its destructor is called.</span></span>|  
|[<span data-ttu-id="c4b1a-111">Metodo GetDisplayName</span><span class="sxs-lookup"><span data-stu-id="c4b1a-111">GetDisplayName Method</span></span>](iassemblyname-getdisplayname-method.md)|<span data-ttu-id="c4b1a-112">Ottiene il nome leggibile dell'assembly a cui fa riferimento questo oggetto `IAssemblyName`.</span><span class="sxs-lookup"><span data-stu-id="c4b1a-112">Gets the human-readable name of the assembly referenced by this `IAssemblyName` object.</span></span>|  
|[<span data-ttu-id="c4b1a-113">Metodo GetName</span><span class="sxs-lookup"><span data-stu-id="c4b1a-113">GetName Method</span></span>](iassemblyname-getname-method.md)|<span data-ttu-id="c4b1a-114">Ottiene il nome semplice e non crittografato dell'assembly a cui fa riferimento questo oggetto `IAssemblyName`.</span><span class="sxs-lookup"><span data-stu-id="c4b1a-114">Gets the simple, unencrypted name of the assembly referenced by this `IAssemblyName` object.</span></span>|  
|[<span data-ttu-id="c4b1a-115">Metodo GetProperty</span><span class="sxs-lookup"><span data-stu-id="c4b1a-115">GetProperty Method</span></span>](iassemblyname-getproperty-method.md)|<span data-ttu-id="c4b1a-116">Ottiene un puntatore alla proprietà a cui fa riferimento il `PropertyId`specificato.</span><span class="sxs-lookup"><span data-stu-id="c4b1a-116">Gets a pointer to the property referenced by the specified `PropertyId`.</span></span>|  
|[<span data-ttu-id="c4b1a-117">Metodo GetVersion</span><span class="sxs-lookup"><span data-stu-id="c4b1a-117">GetVersion Method</span></span>](iassemblyname-getversion-method.md)|<span data-ttu-id="c4b1a-118">Ottiene le informazioni sulla versione per l'assembly a cui fa riferimento questo oggetto `IAssemblyName`.</span><span class="sxs-lookup"><span data-stu-id="c4b1a-118">Gets the version information for the assembly referenced by this `IAssemblyName` object.</span></span>|  
|[<span data-ttu-id="c4b1a-119">Metodo IsEqual</span><span class="sxs-lookup"><span data-stu-id="c4b1a-119">IsEqual Method</span></span>](iassemblyname-isequal-method.md)|<span data-ttu-id="c4b1a-120">Determina se un oggetto `IAssemblyName` specificato è uguale a questo `IAssemblyName`, in base ai flag di confronto specificati.</span><span class="sxs-lookup"><span data-stu-id="c4b1a-120">Determines whether a specified `IAssemblyName` object is equal to this `IAssemblyName`, based on the specified comparison flags.</span></span>|  
|[<span data-ttu-id="c4b1a-121">Metodo SetProperty</span><span class="sxs-lookup"><span data-stu-id="c4b1a-121">SetProperty Method</span></span>](iassemblyname-setproperty-method.md)|<span data-ttu-id="c4b1a-122">Imposta il valore della proprietà a cui fa riferimento il `PropertyId`specificato.</span><span class="sxs-lookup"><span data-stu-id="c4b1a-122">Sets the value of the property referenced by the specified `PropertyId`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c4b1a-123">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c4b1a-123">Requirements</span></span>  
 <span data-ttu-id="c4b1a-124">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c4b1a-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4b1a-125">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="c4b1a-125">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="c4b1a-126">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c4b1a-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4b1a-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c4b1a-127">See also</span></span>

- [<span data-ttu-id="c4b1a-128">Interfacce Fusion</span><span class="sxs-lookup"><span data-stu-id="c4b1a-128">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="c4b1a-129">Interfaccia IAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="c4b1a-129">IAssemblyEnum Interface</span></span>](iassemblyenum-interface.md)
