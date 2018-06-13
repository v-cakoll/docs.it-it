---
title: Interfaccia IIdentityAuthority
ms.date: 03/30/2017
api_name:
- IIdentityAuthority
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IIdentityAuthority
helpviewer_keywords:
- IIdentityAuthority interface [.NET Framework fusion]
ms.assetid: 6277f914-51a8-49be-bec6-52d6d648527d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 692ac4ef4fe8ea64c6a63dc2f02cc04244a842c3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33432528"
---
# <a name="iidentityauthority-interface"></a><span data-ttu-id="b2ad8-102">Interfaccia IIdentityAuthority</span><span class="sxs-lookup"><span data-stu-id="b2ad8-102">IIdentityAuthority Interface</span></span>
<span data-ttu-id="b2ad8-103">Gestisce le chiavi di identità per gli oggetti di codice.</span><span class="sxs-lookup"><span data-stu-id="b2ad8-103">Manages identity keys for code objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b2ad8-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="b2ad8-104">Methods</span></span>  
  
|<span data-ttu-id="b2ad8-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="b2ad8-105">Method</span></span>|<span data-ttu-id="b2ad8-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b2ad8-106">Description</span></span>|  
|------------|-----------------|  
|`IIdentityAuthority::AreDefinitionsEqual`|<span data-ttu-id="b2ad8-107">Ottiene un valore che indica se le due [IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) istanze sono uguali.</span><span class="sxs-lookup"><span data-stu-id="b2ad8-107">Gets a value that indicates whether the two specified [IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) instances are equal.</span></span>|  
|`IIdentityAuthority::AreReferencesEqual`|<span data-ttu-id="b2ad8-108">Ottiene un valore che indica se le due [IReferenceIdentity](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md) istanze sono uguali.</span><span class="sxs-lookup"><span data-stu-id="b2ad8-108">Gets a value that indicates whether the two specified [IReferenceIdentity](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md) instances are equal.</span></span>|  
|`IIdentityAuthority::AreTextualDefinitionsEqual`|<span data-ttu-id="b2ad8-109">Ottiene un valore che indica se le due rappresentazioni identità definizione di stringa specificato sono uguali.</span><span class="sxs-lookup"><span data-stu-id="b2ad8-109">Gets a value that indicates whether the two specified string definition identity representations are equal.</span></span>|  
|`IIdentityAuthority::AreTextualReferencesEqual`|<span data-ttu-id="b2ad8-110">Ottiene un valore che indica se le due rappresentazioni identità di riferimento di stringa specificato sono uguali.</span><span class="sxs-lookup"><span data-stu-id="b2ad8-110">Gets a value that indicates whether the two specified string reference identity representations are equal.</span></span>|  
|`IIdentityAuthority::CreateDefinition`|<span data-ttu-id="b2ad8-111">Ottiene un puntatore a un nuovo `IDefinitionIdentity` istanza che rappresenta l'oggetto di codice nell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="b2ad8-111">Gets a pointer to a new `IDefinitionIdentity` instance that represents the code object in the current scope.</span></span>|  
|`IIdentityAuthority::CreateReference`|<span data-ttu-id="b2ad8-112">Ottiene un puntatore a un nuovo `IReferenceIdentity` istanza che rappresenta l'oggetto di codice nell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="b2ad8-112">Gets a pointer to a new `IReferenceIdentity` instance that represents the code object in the current scope.</span></span>|  
|`IIdentityAuthority::DefinitionToText`|<span data-ttu-id="b2ad8-113">Ottiene una stringa formattata di versione dell'oggetto specificato `IDefinitionIdentity`.</span><span class="sxs-lookup"><span data-stu-id="b2ad8-113">Gets a formatted string version of the specified `IDefinitionIdentity`.</span></span>|  
|`IIdentityAuthority::DefinitionToTextBuffer`|<span data-ttu-id="b2ad8-114">Riempie i buffer di caratteri "wide" specificato con una versione stringa dell'oggetto specificato `IDefinitionIdentity`.</span><span class="sxs-lookup"><span data-stu-id="b2ad8-114">Fills the specified wide character buffer with a string version of the specified `IDefinitionIdentity`.</span></span>|  
|`IIdentityAuthority::DoesDefinitionMatchReference`|<span data-ttu-id="b2ad8-115">Ottiene un valore che indica se l'oggetto specificato `IDefinitionIdentity` e `IReferenceIdentity` istanze fanno riferimento allo stesso oggetto di codice.</span><span class="sxs-lookup"><span data-stu-id="b2ad8-115">Gets a value that indicates whether the specified `IDefinitionIdentity` and `IReferenceIdentity` instances refer to the same code object.</span></span>|  
|`IIdentityAuthority::DoesTextualDefinitionMatchTextualReference`|<span data-ttu-id="b2ad8-116">Ottiene un valore che indica se le stringhe specificate fanno riferimento allo stesso oggetto di codice.</span><span class="sxs-lookup"><span data-stu-id="b2ad8-116">Gets a value that indicates whether the specified strings refer to the same code object.</span></span>|  
|`IIdentityAuthority::GenerateDefinitionKey`|<span data-ttu-id="b2ad8-117">Ottiene un puntatore a una chiave di stringa appena creata per l'oggetto specificato `IDefinitionIdentity`.</span><span class="sxs-lookup"><span data-stu-id="b2ad8-117">Gets a pointer to a newly created string key for the specified `IDefinitionIdentity`.</span></span>|  
|`IIdentityAuthority::GenerateReferenceKey`|<span data-ttu-id="b2ad8-118">Ottiene un puntatore a una chiave di stringa appena creata per l'oggetto specificato `IReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="b2ad8-118">Gets a pointer to a newly created string key for the specified `IReferenceIdentity`.</span></span>|  
|`IIdentityAuthority::HashDefinition`|<span data-ttu-id="b2ad8-119">Ottiene un valore hash per l'oggetto specificato `IDefinitionIdentity`.</span><span class="sxs-lookup"><span data-stu-id="b2ad8-119">Gets a hash value for the specified `IDefinitionIdentity`.</span></span>|  
|`IIdentityAuthority::HashReference`|<span data-ttu-id="b2ad8-120">Ottiene un valore hash per l'oggetto specificato `IreferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="b2ad8-120">Gets a hash value for the specified `IreferenceIdentity`.</span></span>|  
|`IIdentityAuthority::ReferenceToText`|<span data-ttu-id="b2ad8-121">Ottiene una stringa formattata di versione dell'oggetto specificato `IReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="b2ad8-121">Gets a formatted string version of the specified `IReferenceIdentity`.</span></span>|  
|`IIdentityAuthority::ReferenceToTextBuffer`|<span data-ttu-id="b2ad8-122">Riempie i buffer di caratteri "wide" specificato con una versione stringa dell'oggetto specificato `IReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="b2ad8-122">Fills the specified wide character buffer with a string version of the specified `IReferenceIdentity`.</span></span>|  
|`IIdentityAuthority::TextToDefinition`|<span data-ttu-id="b2ad8-123">Ottiene un puntatore a interfaccia a un `IDefinitionIdentity` stringa formattata di istanza generato dall'oggetto specificato.</span><span class="sxs-lookup"><span data-stu-id="b2ad8-123">Gets an interface pointer to an `IDefinitionIdentity` instance generated from the specified formatted string.</span></span>|  
|`IIdentityAuthority::TextToReference`|<span data-ttu-id="b2ad8-124">Ottiene un puntatore a interfaccia a un `IReferenceIdentity` stringa formattata di istanza generato dall'oggetto specificato.</span><span class="sxs-lookup"><span data-stu-id="b2ad8-124">Gets an interface pointer to an `IReferenceIdentity` instance generated from the specified formatted string.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b2ad8-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b2ad8-125">Requirements</span></span>  
 <span data-ttu-id="b2ad8-126">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b2ad8-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2ad8-127">**Intestazione:** Isolation. h</span><span class="sxs-lookup"><span data-stu-id="b2ad8-127">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="b2ad8-128">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2ad8-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2ad8-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b2ad8-129">See Also</span></span>  
 [<span data-ttu-id="b2ad8-130">Interfacce Fusion</span><span class="sxs-lookup"><span data-stu-id="b2ad8-130">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
