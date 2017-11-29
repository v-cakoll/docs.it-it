---
title: Interfaccia IIdentityAuthority
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IIdentityAuthority
api_location: fusion.dll
api_type: COM
f1_keywords: IIdentityAuthority
helpviewer_keywords: IIdentityAuthority interface [.NET Framework fusion]
ms.assetid: 6277f914-51a8-49be-bec6-52d6d648527d
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c3f38d932fa0376186e2c22232d21857d5fa128f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="iidentityauthority-interface"></a><span data-ttu-id="003b4-102">Interfaccia IIdentityAuthority</span><span class="sxs-lookup"><span data-stu-id="003b4-102">IIdentityAuthority Interface</span></span>
<span data-ttu-id="003b4-103">Gestisce le chiavi di identità per gli oggetti di codice.</span><span class="sxs-lookup"><span data-stu-id="003b4-103">Manages identity keys for code objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="003b4-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="003b4-104">Methods</span></span>  
  
|<span data-ttu-id="003b4-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="003b4-105">Method</span></span>|<span data-ttu-id="003b4-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="003b4-106">Description</span></span>|  
|------------|-----------------|  
|`IIdentityAuthority::AreDefinitionsEqual`|<span data-ttu-id="003b4-107">Ottiene un valore che indica se le due [IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) istanze sono uguali.</span><span class="sxs-lookup"><span data-stu-id="003b4-107">Gets a value that indicates whether the two specified [IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) instances are equal.</span></span>|  
|`IIdentityAuthority::AreReferencesEqual`|<span data-ttu-id="003b4-108">Ottiene un valore che indica se le due [IReferenceIdentity](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md) istanze sono uguali.</span><span class="sxs-lookup"><span data-stu-id="003b4-108">Gets a value that indicates whether the two specified [IReferenceIdentity](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md) instances are equal.</span></span>|  
|`IIdentityAuthority::AreTextualDefinitionsEqual`|<span data-ttu-id="003b4-109">Ottiene un valore che indica se le due rappresentazioni identità definizione di stringa specificato sono uguali.</span><span class="sxs-lookup"><span data-stu-id="003b4-109">Gets a value that indicates whether the two specified string definition identity representations are equal.</span></span>|  
|`IIdentityAuthority::AreTextualReferencesEqual`|<span data-ttu-id="003b4-110">Ottiene un valore che indica se le due rappresentazioni identità di riferimento di stringa specificato sono uguali.</span><span class="sxs-lookup"><span data-stu-id="003b4-110">Gets a value that indicates whether the two specified string reference identity representations are equal.</span></span>|  
|`IIdentityAuthority::CreateDefinition`|<span data-ttu-id="003b4-111">Ottiene un puntatore a un nuovo `IDefinitionIdentity` istanza che rappresenta l'oggetto di codice nell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="003b4-111">Gets a pointer to a new `IDefinitionIdentity` instance that represents the code object in the current scope.</span></span>|  
|`IIdentityAuthority::CreateReference`|<span data-ttu-id="003b4-112">Ottiene un puntatore a un nuovo `IReferenceIdentity` istanza che rappresenta l'oggetto di codice nell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="003b4-112">Gets a pointer to a new `IReferenceIdentity` instance that represents the code object in the current scope.</span></span>|  
|`IIdentityAuthority::DefinitionToText`|<span data-ttu-id="003b4-113">Ottiene una stringa formattata di versione dell'oggetto specificato `IDefinitionIdentity`.</span><span class="sxs-lookup"><span data-stu-id="003b4-113">Gets a formatted string version of the specified `IDefinitionIdentity`.</span></span>|  
|`IIdentityAuthority::DefinitionToTextBuffer`|<span data-ttu-id="003b4-114">Riempie i buffer di caratteri "wide" specificato con una versione stringa dell'oggetto specificato `IDefinitionIdentity`.</span><span class="sxs-lookup"><span data-stu-id="003b4-114">Fills the specified wide character buffer with a string version of the specified `IDefinitionIdentity`.</span></span>|  
|`IIdentityAuthority::DoesDefinitionMatchReference`|<span data-ttu-id="003b4-115">Ottiene un valore che indica se l'oggetto specificato `IDefinitionIdentity` e `IReferenceIdentity` istanze fanno riferimento allo stesso oggetto di codice.</span><span class="sxs-lookup"><span data-stu-id="003b4-115">Gets a value that indicates whether the specified `IDefinitionIdentity` and `IReferenceIdentity` instances refer to the same code object.</span></span>|  
|`IIdentityAuthority::DoesTextualDefinitionMatchTextualReference`|<span data-ttu-id="003b4-116">Ottiene un valore che indica se le stringhe specificate fanno riferimento allo stesso oggetto di codice.</span><span class="sxs-lookup"><span data-stu-id="003b4-116">Gets a value that indicates whether the specified strings refer to the same code object.</span></span>|  
|`IIdentityAuthority::GenerateDefinitionKey`|<span data-ttu-id="003b4-117">Ottiene un puntatore a una chiave di stringa appena creata per l'oggetto specificato `IDefinitionIdentity`.</span><span class="sxs-lookup"><span data-stu-id="003b4-117">Gets a pointer to a newly created string key for the specified `IDefinitionIdentity`.</span></span>|  
|`IIdentityAuthority::GenerateReferenceKey`|<span data-ttu-id="003b4-118">Ottiene un puntatore a una chiave di stringa appena creata per l'oggetto specificato `IReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="003b4-118">Gets a pointer to a newly created string key for the specified `IReferenceIdentity`.</span></span>|  
|`IIdentityAuthority::HashDefinition`|<span data-ttu-id="003b4-119">Ottiene un valore hash per l'oggetto specificato `IDefinitionIdentity`.</span><span class="sxs-lookup"><span data-stu-id="003b4-119">Gets a hash value for the specified `IDefinitionIdentity`.</span></span>|  
|`IIdentityAuthority::HashReference`|<span data-ttu-id="003b4-120">Ottiene un valore hash per l'oggetto specificato `IreferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="003b4-120">Gets a hash value for the specified `IreferenceIdentity`.</span></span>|  
|`IIdentityAuthority::ReferenceToText`|<span data-ttu-id="003b4-121">Ottiene una stringa formattata di versione dell'oggetto specificato `IReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="003b4-121">Gets a formatted string version of the specified `IReferenceIdentity`.</span></span>|  
|`IIdentityAuthority::ReferenceToTextBuffer`|<span data-ttu-id="003b4-122">Riempie i buffer di caratteri "wide" specificato con una versione stringa dell'oggetto specificato `IReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="003b4-122">Fills the specified wide character buffer with a string version of the specified `IReferenceIdentity`.</span></span>|  
|`IIdentityAuthority::TextToDefinition`|<span data-ttu-id="003b4-123">Ottiene un puntatore a interfaccia a un `IDefinitionIdentity` stringa formattata di istanza generato dall'oggetto specificato.</span><span class="sxs-lookup"><span data-stu-id="003b4-123">Gets an interface pointer to an `IDefinitionIdentity` instance generated from the specified formatted string.</span></span>|  
|`IIdentityAuthority::TextToReference`|<span data-ttu-id="003b4-124">Ottiene un puntatore a interfaccia a un `IReferenceIdentity` stringa formattata di istanza generato dall'oggetto specificato.</span><span class="sxs-lookup"><span data-stu-id="003b4-124">Gets an interface pointer to an `IReferenceIdentity` instance generated from the specified formatted string.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="003b4-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="003b4-125">Requirements</span></span>  
 <span data-ttu-id="003b4-126">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="003b4-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="003b4-127">**Intestazione:** Isolation. h</span><span class="sxs-lookup"><span data-stu-id="003b4-127">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="003b4-128">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="003b4-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="003b4-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="003b4-129">See Also</span></span>  
 [<span data-ttu-id="003b4-130">Fusion (interfacce)</span><span class="sxs-lookup"><span data-stu-id="003b4-130">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
