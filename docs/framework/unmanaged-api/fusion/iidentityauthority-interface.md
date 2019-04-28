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
ms.openlocfilehash: 263dc0f9d686440aaa23e359c26db1b4d3d09b1e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61609100"
---
# <a name="iidentityauthority-interface"></a><span data-ttu-id="67157-102">Interfaccia IIdentityAuthority</span><span class="sxs-lookup"><span data-stu-id="67157-102">IIdentityAuthority Interface</span></span>

<span data-ttu-id="67157-103">Gestisce le chiavi di identità per gli oggetti di codice.</span><span class="sxs-lookup"><span data-stu-id="67157-103">Manages identity keys for code objects.</span></span>

## <a name="methods"></a><span data-ttu-id="67157-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="67157-104">Methods</span></span>

|<span data-ttu-id="67157-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="67157-105">Method</span></span>|<span data-ttu-id="67157-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="67157-106">Description</span></span>|
|------------|-----------------|
|`IIdentityAuthority::AreDefinitionsEqual`|<span data-ttu-id="67157-107">Ottiene un valore che indica se le due [IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) istanze sono uguali.</span><span class="sxs-lookup"><span data-stu-id="67157-107">Gets a value that indicates whether the two specified [IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) instances are equal.</span></span>|
|`IIdentityAuthority::AreReferencesEqual`|<span data-ttu-id="67157-108">Ottiene un valore che indica se le due [IReferenceIdentity](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md) istanze sono uguali.</span><span class="sxs-lookup"><span data-stu-id="67157-108">Gets a value that indicates whether the two specified [IReferenceIdentity](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md) instances are equal.</span></span>|
|`IIdentityAuthority::AreTextualDefinitionsEqual`|<span data-ttu-id="67157-109">Ottiene un valore che indica se le due rappresentazioni identità definizione di stringa specificato sono uguali.</span><span class="sxs-lookup"><span data-stu-id="67157-109">Gets a value that indicates whether the two specified string definition identity representations are equal.</span></span>|
|`IIdentityAuthority::AreTextualReferencesEqual`|<span data-ttu-id="67157-110">Ottiene un valore che indica se le due rappresentazioni identità di riferimento di stringa specificato sono uguali.</span><span class="sxs-lookup"><span data-stu-id="67157-110">Gets a value that indicates whether the two specified string reference identity representations are equal.</span></span>|
|`IIdentityAuthority::CreateDefinition`|<span data-ttu-id="67157-111">Ottiene un puntatore a un nuovo `IDefinitionIdentity` istanza che rappresenta l'oggetto di codice nell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="67157-111">Gets a pointer to a new `IDefinitionIdentity` instance that represents the code object in the current scope.</span></span>|
|`IIdentityAuthority::CreateReference`|<span data-ttu-id="67157-112">Ottiene un puntatore a un nuovo `IReferenceIdentity` istanza che rappresenta l'oggetto di codice nell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="67157-112">Gets a pointer to a new `IReferenceIdentity` instance that represents the code object in the current scope.</span></span>|
|`IIdentityAuthority::DefinitionToText`|<span data-ttu-id="67157-113">Ottiene una versione di stringa formattato dell'oggetto specificato `IDefinitionIdentity`.</span><span class="sxs-lookup"><span data-stu-id="67157-113">Gets a formatted string version of the specified `IDefinitionIdentity`.</span></span>|
|`IIdentityAuthority::DefinitionToTextBuffer`|<span data-ttu-id="67157-114">Riempie i buffer di caratteri wide specificata con una versione stringa dell'oggetto specificato `IDefinitionIdentity`.</span><span class="sxs-lookup"><span data-stu-id="67157-114">Fills the specified wide character buffer with a string version of the specified `IDefinitionIdentity`.</span></span>|
|`IIdentityAuthority::DoesDefinitionMatchReference`|<span data-ttu-id="67157-115">Ottiene un valore che indica se l'oggetto specificato `IDefinitionIdentity` e `IReferenceIdentity` istanze fanno riferimento allo stesso oggetto di codice.</span><span class="sxs-lookup"><span data-stu-id="67157-115">Gets a value that indicates whether the specified `IDefinitionIdentity` and `IReferenceIdentity` instances refer to the same code object.</span></span>|
|`IIdentityAuthority::DoesTextualDefinitionMatchTextualReference`|<span data-ttu-id="67157-116">Ottiene un valore che indica se le stringhe specificate fanno riferimento allo stesso oggetto di codice.</span><span class="sxs-lookup"><span data-stu-id="67157-116">Gets a value that indicates whether the specified strings refer to the same code object.</span></span>|
|`IIdentityAuthority::GenerateDefinitionKey`|<span data-ttu-id="67157-117">Ottiene un puntatore a una chiave di stringa appena creata per l'oggetto specificato `IDefinitionIdentity`.</span><span class="sxs-lookup"><span data-stu-id="67157-117">Gets a pointer to a newly created string key for the specified `IDefinitionIdentity`.</span></span>|
|`IIdentityAuthority::GenerateReferenceKey`|<span data-ttu-id="67157-118">Ottiene un puntatore a una chiave di stringa appena creata per l'oggetto specificato `IReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="67157-118">Gets a pointer to a newly created string key for the specified `IReferenceIdentity`.</span></span>|
|`IIdentityAuthority::HashDefinition`|<span data-ttu-id="67157-119">Ottiene un valore hash per l'oggetto specificato `IDefinitionIdentity`.</span><span class="sxs-lookup"><span data-stu-id="67157-119">Gets a hash value for the specified `IDefinitionIdentity`.</span></span>|
|`IIdentityAuthority::HashReference`|<span data-ttu-id="67157-120">Ottiene un valore hash per l'oggetto specificato `IReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="67157-120">Gets a hash value for the specified `IReferenceIdentity`.</span></span>|
|`IIdentityAuthority::ReferenceToText`|<span data-ttu-id="67157-121">Ottiene una versione di stringa formattato dell'oggetto specificato `IReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="67157-121">Gets a formatted string version of the specified `IReferenceIdentity`.</span></span>|
|`IIdentityAuthority::ReferenceToTextBuffer`|<span data-ttu-id="67157-122">Riempie i buffer di caratteri wide specificata con una versione stringa dell'oggetto specificato `IReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="67157-122">Fills the specified wide character buffer with a string version of the specified `IReferenceIdentity`.</span></span>|
|`IIdentityAuthority::TextToDefinition`|<span data-ttu-id="67157-123">Ottiene un puntatore a interfaccia per un `IDefinitionIdentity` istanza generata dagli oggetti stringa formattata.</span><span class="sxs-lookup"><span data-stu-id="67157-123">Gets an interface pointer to an `IDefinitionIdentity` instance generated from the specified formatted string.</span></span>|
|`IIdentityAuthority::TextToReference`|<span data-ttu-id="67157-124">Ottiene un puntatore a interfaccia per un `IReferenceIdentity` istanza generata dagli oggetti stringa formattata.</span><span class="sxs-lookup"><span data-stu-id="67157-124">Gets an interface pointer to an `IReferenceIdentity` instance generated from the specified formatted string.</span></span>|

## <a name="requirements"></a><span data-ttu-id="67157-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="67157-125">Requirements</span></span>

<span data-ttu-id="67157-126">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="67157-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="67157-127">**Intestazione:** Isolation. h</span><span class="sxs-lookup"><span data-stu-id="67157-127">**Header:** Isolation.h</span></span>

<span data-ttu-id="67157-128">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67157-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="67157-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="67157-129">See also</span></span>

- [<span data-ttu-id="67157-130">Interfacce Fusion</span><span class="sxs-lookup"><span data-stu-id="67157-130">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
