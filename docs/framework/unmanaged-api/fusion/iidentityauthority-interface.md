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
ms.openlocfilehash: 3e2d2335e37ced9139ea44092f10b19566894681
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127087"
---
# <a name="iidentityauthority-interface"></a><span data-ttu-id="492b5-102">Interfaccia IIdentityAuthority</span><span class="sxs-lookup"><span data-stu-id="492b5-102">IIdentityAuthority Interface</span></span>

<span data-ttu-id="492b5-103">Gestisce chiavi di identità per oggetti di codice.</span><span class="sxs-lookup"><span data-stu-id="492b5-103">Manages identity keys for code objects.</span></span>

## <a name="methods"></a><span data-ttu-id="492b5-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="492b5-104">Methods</span></span>

|<span data-ttu-id="492b5-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="492b5-105">Method</span></span>|<span data-ttu-id="492b5-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="492b5-106">Description</span></span>|
|------------|-----------------|
|`IIdentityAuthority::AreDefinitionsEqual`|<span data-ttu-id="492b5-107">Ottiene un valore che indica se le due istanze di [IDefinitionIdentity](idefinitionidentity-interface.md) specificate sono uguali.</span><span class="sxs-lookup"><span data-stu-id="492b5-107">Gets a value that indicates whether the two specified [IDefinitionIdentity](idefinitionidentity-interface.md) instances are equal.</span></span>|
|`IIdentityAuthority::AreReferencesEqual`|<span data-ttu-id="492b5-108">Ottiene un valore che indica se le due istanze di [IReferenceIdentity](ireferenceidentity-interface.md) specificate sono uguali.</span><span class="sxs-lookup"><span data-stu-id="492b5-108">Gets a value that indicates whether the two specified [IReferenceIdentity](ireferenceidentity-interface.md) instances are equal.</span></span>|
|`IIdentityAuthority::AreTextualDefinitionsEqual`|<span data-ttu-id="492b5-109">Ottiene un valore che indica se le due rappresentazioni di identità della definizione di stringa specificate sono uguali.</span><span class="sxs-lookup"><span data-stu-id="492b5-109">Gets a value that indicates whether the two specified string definition identity representations are equal.</span></span>|
|`IIdentityAuthority::AreTextualReferencesEqual`|<span data-ttu-id="492b5-110">Ottiene un valore che indica se le due rappresentazioni di identità di riferimento della stringa specificate sono uguali.</span><span class="sxs-lookup"><span data-stu-id="492b5-110">Gets a value that indicates whether the two specified string reference identity representations are equal.</span></span>|
|`IIdentityAuthority::CreateDefinition`|<span data-ttu-id="492b5-111">Ottiene un puntatore a una nuova istanza di `IDefinitionIdentity` che rappresenta l'oggetto di codice nell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="492b5-111">Gets a pointer to a new `IDefinitionIdentity` instance that represents the code object in the current scope.</span></span>|
|`IIdentityAuthority::CreateReference`|<span data-ttu-id="492b5-112">Ottiene un puntatore a una nuova istanza di `IReferenceIdentity` che rappresenta l'oggetto di codice nell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="492b5-112">Gets a pointer to a new `IReferenceIdentity` instance that represents the code object in the current scope.</span></span>|
|`IIdentityAuthority::DefinitionToText`|<span data-ttu-id="492b5-113">Ottiene una versione in formato stringa del `IDefinitionIdentity`specificato.</span><span class="sxs-lookup"><span data-stu-id="492b5-113">Gets a formatted string version of the specified `IDefinitionIdentity`.</span></span>|
|`IIdentityAuthority::DefinitionToTextBuffer`|<span data-ttu-id="492b5-114">Riempie il buffer di caratteri wide specificato con una versione in formato stringa del `IDefinitionIdentity`specificato.</span><span class="sxs-lookup"><span data-stu-id="492b5-114">Fills the specified wide character buffer with a string version of the specified `IDefinitionIdentity`.</span></span>|
|`IIdentityAuthority::DoesDefinitionMatchReference`|<span data-ttu-id="492b5-115">Ottiene un valore che indica se le istanze di `IDefinitionIdentity` e `IReferenceIdentity` specificate fanno riferimento allo stesso oggetto di codice.</span><span class="sxs-lookup"><span data-stu-id="492b5-115">Gets a value that indicates whether the specified `IDefinitionIdentity` and `IReferenceIdentity` instances refer to the same code object.</span></span>|
|`IIdentityAuthority::DoesTextualDefinitionMatchTextualReference`|<span data-ttu-id="492b5-116">Ottiene un valore che indica se le stringhe specificate fanno riferimento allo stesso oggetto di codice.</span><span class="sxs-lookup"><span data-stu-id="492b5-116">Gets a value that indicates whether the specified strings refer to the same code object.</span></span>|
|`IIdentityAuthority::GenerateDefinitionKey`|<span data-ttu-id="492b5-117">Ottiene un puntatore a una chiave di stringa appena creata per il `IDefinitionIdentity`specificato.</span><span class="sxs-lookup"><span data-stu-id="492b5-117">Gets a pointer to a newly created string key for the specified `IDefinitionIdentity`.</span></span>|
|`IIdentityAuthority::GenerateReferenceKey`|<span data-ttu-id="492b5-118">Ottiene un puntatore a una chiave di stringa appena creata per il `IReferenceIdentity`specificato.</span><span class="sxs-lookup"><span data-stu-id="492b5-118">Gets a pointer to a newly created string key for the specified `IReferenceIdentity`.</span></span>|
|`IIdentityAuthority::HashDefinition`|<span data-ttu-id="492b5-119">Ottiene un valore hash per il `IDefinitionIdentity`specificato.</span><span class="sxs-lookup"><span data-stu-id="492b5-119">Gets a hash value for the specified `IDefinitionIdentity`.</span></span>|
|`IIdentityAuthority::HashReference`|<span data-ttu-id="492b5-120">Ottiene un valore hash per il `IReferenceIdentity`specificato.</span><span class="sxs-lookup"><span data-stu-id="492b5-120">Gets a hash value for the specified `IReferenceIdentity`.</span></span>|
|`IIdentityAuthority::ReferenceToText`|<span data-ttu-id="492b5-121">Ottiene una versione in formato stringa del `IReferenceIdentity`specificato.</span><span class="sxs-lookup"><span data-stu-id="492b5-121">Gets a formatted string version of the specified `IReferenceIdentity`.</span></span>|
|`IIdentityAuthority::ReferenceToTextBuffer`|<span data-ttu-id="492b5-122">Riempie il buffer di caratteri wide specificato con una versione in formato stringa del `IReferenceIdentity`specificato.</span><span class="sxs-lookup"><span data-stu-id="492b5-122">Fills the specified wide character buffer with a string version of the specified `IReferenceIdentity`.</span></span>|
|`IIdentityAuthority::TextToDefinition`|<span data-ttu-id="492b5-123">Ottiene un puntatore a interfaccia a un'istanza `IDefinitionIdentity` generata dalla stringa formattata specificata.</span><span class="sxs-lookup"><span data-stu-id="492b5-123">Gets an interface pointer to an `IDefinitionIdentity` instance generated from the specified formatted string.</span></span>|
|`IIdentityAuthority::TextToReference`|<span data-ttu-id="492b5-124">Ottiene un puntatore a interfaccia a un'istanza `IReferenceIdentity` generata dalla stringa formattata specificata.</span><span class="sxs-lookup"><span data-stu-id="492b5-124">Gets an interface pointer to an `IReferenceIdentity` instance generated from the specified formatted string.</span></span>|

## <a name="requirements"></a><span data-ttu-id="492b5-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="492b5-125">Requirements</span></span>

<span data-ttu-id="492b5-126">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="492b5-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="492b5-127">**Intestazione:** Isolation. h</span><span class="sxs-lookup"><span data-stu-id="492b5-127">**Header:** Isolation.h</span></span>

<span data-ttu-id="492b5-128">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="492b5-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="492b5-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="492b5-129">See also</span></span>

- [<span data-ttu-id="492b5-130">Interfacce Fusion</span><span class="sxs-lookup"><span data-stu-id="492b5-130">Fusion Interfaces</span></span>](fusion-interfaces.md)
