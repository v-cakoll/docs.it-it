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
ms.openlocfilehash: 7421e0d0e1a1f0e1a5fbe0d0eb7d5a0ab2a48b9a
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796418"
---
# <a name="iidentityauthority-interface"></a><span data-ttu-id="bb651-102">Interfaccia IIdentityAuthority</span><span class="sxs-lookup"><span data-stu-id="bb651-102">IIdentityAuthority Interface</span></span>

<span data-ttu-id="bb651-103">Gestisce chiavi di identità per oggetti di codice.</span><span class="sxs-lookup"><span data-stu-id="bb651-103">Manages identity keys for code objects.</span></span>

## <a name="methods"></a><span data-ttu-id="bb651-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="bb651-104">Methods</span></span>

|<span data-ttu-id="bb651-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="bb651-105">Method</span></span>|<span data-ttu-id="bb651-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bb651-106">Description</span></span>|
|------------|-----------------|
|`IIdentityAuthority::AreDefinitionsEqual`|<span data-ttu-id="bb651-107">Ottiene un valore che indica se le due istanze di [IDefinitionIdentity](idefinitionidentity-interface.md) specificate sono uguali.</span><span class="sxs-lookup"><span data-stu-id="bb651-107">Gets a value that indicates whether the two specified [IDefinitionIdentity](idefinitionidentity-interface.md) instances are equal.</span></span>|
|`IIdentityAuthority::AreReferencesEqual`|<span data-ttu-id="bb651-108">Ottiene un valore che indica se le due istanze di [IReferenceIdentity](ireferenceidentity-interface.md) specificate sono uguali.</span><span class="sxs-lookup"><span data-stu-id="bb651-108">Gets a value that indicates whether the two specified [IReferenceIdentity](ireferenceidentity-interface.md) instances are equal.</span></span>|
|`IIdentityAuthority::AreTextualDefinitionsEqual`|<span data-ttu-id="bb651-109">Ottiene un valore che indica se le due rappresentazioni di identità della definizione di stringa specificate sono uguali.</span><span class="sxs-lookup"><span data-stu-id="bb651-109">Gets a value that indicates whether the two specified string definition identity representations are equal.</span></span>|
|`IIdentityAuthority::AreTextualReferencesEqual`|<span data-ttu-id="bb651-110">Ottiene un valore che indica se le due rappresentazioni di identità di riferimento della stringa specificate sono uguali.</span><span class="sxs-lookup"><span data-stu-id="bb651-110">Gets a value that indicates whether the two specified string reference identity representations are equal.</span></span>|
|`IIdentityAuthority::CreateDefinition`|<span data-ttu-id="bb651-111">Ottiene un puntatore a una nuova `IDefinitionIdentity` istanza di che rappresenta l'oggetto di codice nell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="bb651-111">Gets a pointer to a new `IDefinitionIdentity` instance that represents the code object in the current scope.</span></span>|
|`IIdentityAuthority::CreateReference`|<span data-ttu-id="bb651-112">Ottiene un puntatore a una nuova `IReferenceIdentity` istanza di che rappresenta l'oggetto di codice nell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="bb651-112">Gets a pointer to a new `IReferenceIdentity` instance that represents the code object in the current scope.</span></span>|
|`IIdentityAuthority::DefinitionToText`|<span data-ttu-id="bb651-113">Ottiene una versione in formato stringa dell'oggetto `IDefinitionIdentity`specificato.</span><span class="sxs-lookup"><span data-stu-id="bb651-113">Gets a formatted string version of the specified `IDefinitionIdentity`.</span></span>|
|`IIdentityAuthority::DefinitionToTextBuffer`|<span data-ttu-id="bb651-114">Riempie il buffer di caratteri wide specificato con una versione in formato stringa `IDefinitionIdentity`dell'oggetto specificato.</span><span class="sxs-lookup"><span data-stu-id="bb651-114">Fills the specified wide character buffer with a string version of the specified `IDefinitionIdentity`.</span></span>|
|`IIdentityAuthority::DoesDefinitionMatchReference`|<span data-ttu-id="bb651-115">Ottiene un valore che indica se le istanze `IDefinitionIdentity` e `IReferenceIdentity` specificate fanno riferimento allo stesso oggetto di codice.</span><span class="sxs-lookup"><span data-stu-id="bb651-115">Gets a value that indicates whether the specified `IDefinitionIdentity` and `IReferenceIdentity` instances refer to the same code object.</span></span>|
|`IIdentityAuthority::DoesTextualDefinitionMatchTextualReference`|<span data-ttu-id="bb651-116">Ottiene un valore che indica se le stringhe specificate fanno riferimento allo stesso oggetto di codice.</span><span class="sxs-lookup"><span data-stu-id="bb651-116">Gets a value that indicates whether the specified strings refer to the same code object.</span></span>|
|`IIdentityAuthority::GenerateDefinitionKey`|<span data-ttu-id="bb651-117">Ottiene un puntatore a una chiave di stringa appena creata per l' `IDefinitionIdentity`oggetto specificato.</span><span class="sxs-lookup"><span data-stu-id="bb651-117">Gets a pointer to a newly created string key for the specified `IDefinitionIdentity`.</span></span>|
|`IIdentityAuthority::GenerateReferenceKey`|<span data-ttu-id="bb651-118">Ottiene un puntatore a una chiave di stringa appena creata per l' `IReferenceIdentity`oggetto specificato.</span><span class="sxs-lookup"><span data-stu-id="bb651-118">Gets a pointer to a newly created string key for the specified `IReferenceIdentity`.</span></span>|
|`IIdentityAuthority::HashDefinition`|<span data-ttu-id="bb651-119">Ottiene un valore hash per l'oggetto `IDefinitionIdentity`specificato.</span><span class="sxs-lookup"><span data-stu-id="bb651-119">Gets a hash value for the specified `IDefinitionIdentity`.</span></span>|
|`IIdentityAuthority::HashReference`|<span data-ttu-id="bb651-120">Ottiene un valore hash per l'oggetto `IReferenceIdentity`specificato.</span><span class="sxs-lookup"><span data-stu-id="bb651-120">Gets a hash value for the specified `IReferenceIdentity`.</span></span>|
|`IIdentityAuthority::ReferenceToText`|<span data-ttu-id="bb651-121">Ottiene una versione in formato stringa dell'oggetto `IReferenceIdentity`specificato.</span><span class="sxs-lookup"><span data-stu-id="bb651-121">Gets a formatted string version of the specified `IReferenceIdentity`.</span></span>|
|`IIdentityAuthority::ReferenceToTextBuffer`|<span data-ttu-id="bb651-122">Riempie il buffer di caratteri wide specificato con una versione in formato stringa `IReferenceIdentity`dell'oggetto specificato.</span><span class="sxs-lookup"><span data-stu-id="bb651-122">Fills the specified wide character buffer with a string version of the specified `IReferenceIdentity`.</span></span>|
|`IIdentityAuthority::TextToDefinition`|<span data-ttu-id="bb651-123">Ottiene un puntatore a interfaccia a `IDefinitionIdentity` un'istanza generata dalla stringa formattata specificata.</span><span class="sxs-lookup"><span data-stu-id="bb651-123">Gets an interface pointer to an `IDefinitionIdentity` instance generated from the specified formatted string.</span></span>|
|`IIdentityAuthority::TextToReference`|<span data-ttu-id="bb651-124">Ottiene un puntatore a interfaccia a `IReferenceIdentity` un'istanza generata dalla stringa formattata specificata.</span><span class="sxs-lookup"><span data-stu-id="bb651-124">Gets an interface pointer to an `IReferenceIdentity` instance generated from the specified formatted string.</span></span>|

## <a name="requirements"></a><span data-ttu-id="bb651-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bb651-125">Requirements</span></span>

<span data-ttu-id="bb651-126">**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bb651-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="bb651-127">**Intestazione:** Isolation. h</span><span class="sxs-lookup"><span data-stu-id="bb651-127">**Header:** Isolation.h</span></span>

<span data-ttu-id="bb651-128">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb651-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="bb651-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bb651-129">See also</span></span>

- [<span data-ttu-id="bb651-130">Interfacce Fusion</span><span class="sxs-lookup"><span data-stu-id="bb651-130">Fusion Interfaces</span></span>](fusion-interfaces.md)
