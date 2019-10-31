---
title: Interfaccia IAppIdAuthority
ms.date: 03/30/2017
api_name:
- IAppIdAuthority
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAppIdAuthority
helpviewer_keywords:
- IAppIdAuthority interface [.NET Framework fusion]
ms.assetid: ec354fa1-1efd-41b0-bc43-b90597b6e253
topic_type:
- apiref
ms.openlocfilehash: 004e4f70e3385e7a71c356cce38e64d0253dcfa4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127125"
---
# <a name="iappidauthority-interface"></a><span data-ttu-id="29129-102">Interfaccia IAppIdAuthority</span><span class="sxs-lookup"><span data-stu-id="29129-102">IAppIdAuthority Interface</span></span>
<span data-ttu-id="29129-103">Fornisce metodi che generano e confrontano le chiavi per le identità e i riferimenti dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="29129-103">Provides methods that generate and compare keys for application identities and references.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="29129-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="29129-104">Methods</span></span>  
  
|<span data-ttu-id="29129-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="29129-105">Method</span></span>|<span data-ttu-id="29129-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="29129-106">Description</span></span>|  
|------------|-----------------|  
|`IAppIdAuthority::AreDefinitionsEqual`|<span data-ttu-id="29129-107">Ottiene un valore che indica se le due istanze di [IDefinitionAppId](idefinitionappid-interface.md) specificate sono uguali.</span><span class="sxs-lookup"><span data-stu-id="29129-107">Gets a value that indicates whether the two specified [IDefinitionAppId](idefinitionappid-interface.md) instances are equal.</span></span> <span data-ttu-id="29129-108">È possibile passare il valore del flag IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION per ignorare le rispettive informazioni sulla versione.</span><span class="sxs-lookup"><span data-stu-id="29129-108">You can pass the flag value IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::AreReferencesEqual`|<span data-ttu-id="29129-109">Ottiene un valore che indica se le due istanze di [IReferenceAppId](ireferenceappid-interface.md) specificate sono uguali.</span><span class="sxs-lookup"><span data-stu-id="29129-109">Gets a value that indicates whether the two specified [IReferenceAppId](ireferenceappid-interface.md) instances are equal.</span></span> <span data-ttu-id="29129-110">È possibile passare il valore del flag IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION per ignorare le rispettive informazioni sulla versione.</span><span class="sxs-lookup"><span data-stu-id="29129-110">You can pass the flag value IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::AreTextualDefinitionsEqual`|<span data-ttu-id="29129-111">Ottiene un valore che indica se le due definizioni di stringa specificate sono uguali.</span><span class="sxs-lookup"><span data-stu-id="29129-111">Gets a value that indicates whether the two specified string definitions are equal.</span></span> <span data-ttu-id="29129-112">È possibile passare il valore del flag IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION per ignorare le rispettive informazioni sulla versione.</span><span class="sxs-lookup"><span data-stu-id="29129-112">You can pass the flag value IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::AreTextualReferencesEqual`|<span data-ttu-id="29129-113">Ottiene un valore che indica se i due riferimenti di stringa specificati sono uguali.</span><span class="sxs-lookup"><span data-stu-id="29129-113">Gets a value that indicates whether the two specified string references are equal.</span></span> <span data-ttu-id="29129-114">È possibile passare il valore del flag IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION per ignorare le rispettive informazioni sulla versione.</span><span class="sxs-lookup"><span data-stu-id="29129-114">You can pass the flag value IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::CreateDefinition`|<span data-ttu-id="29129-115">Ottiene un puntatore a interfaccia a un'istanza di `IDefinitionAppId` appena generata che rappresenta l'assembly nell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="29129-115">Gets an interface pointer to a newly generated `IDefinitionAppId` instance that represents the assembly in the current scope.</span></span>|  
|`IAppIdAuthority::CreateReference`|<span data-ttu-id="29129-116">Ottiene un puntatore a interfaccia a un `IReferenceAppId` appena creato che rappresenta l'assembly nell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="29129-116">Gets an interface pointer to a newly created `IReferenceAppId` that represents the assembly in the current scope.</span></span>|  
|`IAppIdAuthority::DefinitionToText`|<span data-ttu-id="29129-117">Ottiene una versione in formato stringa del `IDefinitionAppId`specificato, utilizzando i valori di flag specificati.</span><span class="sxs-lookup"><span data-stu-id="29129-117">Gets a string version of the specified `IDefinitionAppId`, using the specified flag values.</span></span>|  
|`IAppIdAuthority::DoesDefinitionMatchReference`|<span data-ttu-id="29129-118">Ottiene un valore che indica se il `IDefinitionAppId` e il `IReferenceAppId` specificati rappresentano lo stesso assembly.</span><span class="sxs-lookup"><span data-stu-id="29129-118">Gets a value that indicates whether the specified `IDefinitionAppId` and `IReferenceAppId` represent the same assembly.</span></span>|  
|`IAppIdAuthority::DoesTextualDefinitionMatchTextualReference`|<span data-ttu-id="29129-119">Ottiene un valore che indica se la stringa di definizione e la stringa di riferimento specificate rappresentano lo stesso assembly.</span><span class="sxs-lookup"><span data-stu-id="29129-119">Gets a value that indicates whether the specified definition string and reference string represent the same assembly.</span></span>|  
|`IAppIdAuthority::GenerateDefinitionKey`|<span data-ttu-id="29129-120">Ottiene una chiave di stringa che rappresenta l'istanza di `IDefinitionAppId` specificata.</span><span class="sxs-lookup"><span data-stu-id="29129-120">Gets a string key that represents the specified `IDefinitionAppId` instance.</span></span>|  
|`IAppIdAuthority::GenerateReferenceKey`|<span data-ttu-id="29129-121">Ottiene una chiave di stringa che rappresenta l'istanza di `IReferenceAppId` specificata.</span><span class="sxs-lookup"><span data-stu-id="29129-121">Gets a string key that represents the specified `IReferenceAppId` instance.</span></span>|  
|`IAppIdAuthority::HashDefinition`|<span data-ttu-id="29129-122">Ottiene una chiave hash per l'istanza di `IDefinitionAppId` specificata.</span><span class="sxs-lookup"><span data-stu-id="29129-122">Gets a hash key for the specified `IDefinitionAppId` instance.</span></span>|  
|`IAppIdAuthority::HashReference`|<span data-ttu-id="29129-123">Ottiene una chiave hash per l'istanza di `IReferenceAppId` specificata.</span><span class="sxs-lookup"><span data-stu-id="29129-123">Gets a hash key for the specified `IReferenceAppId` instance.</span></span>|  
|`IAppIdAuthority::ReferenceToText`|<span data-ttu-id="29129-124">Ottiene una versione in formato stringa del `IReferenceAppId`specificato, utilizzando i valori di flag specificati.</span><span class="sxs-lookup"><span data-stu-id="29129-124">Gets a string version of the specified `IReferenceAppId`, using the specified flag values.</span></span>|  
|`IAppIdAuthority::TextToDefinition`|<span data-ttu-id="29129-125">Ottiene un puntatore a interfaccia a un'istanza di `IDefinitionAppId` che rappresenta l'assembly a cui fa riferimento la chiave di stringa specificata.</span><span class="sxs-lookup"><span data-stu-id="29129-125">Gets an interface pointer to an `IDefinitionAppId` instance that represents the assembly referenced by the specified string key.</span></span>|  
|`IAppIdAuthority::TextToReference`|<span data-ttu-id="29129-126">Ottiene un puntatore a interfaccia a un'istanza di `IReferenceAppId` che rappresenta l'assembly a cui fa riferimento la chiave di stringa specificata.</span><span class="sxs-lookup"><span data-stu-id="29129-126">Gets an interface pointer to an `IReferenceAppId` instance that represents the assembly referenced by the specified string key.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="29129-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="29129-127">Requirements</span></span>  
 <span data-ttu-id="29129-128">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="29129-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="29129-129">**Intestazione:** Isolation. h</span><span class="sxs-lookup"><span data-stu-id="29129-129">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="29129-130">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="29129-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29129-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="29129-131">See also</span></span>

- [<span data-ttu-id="29129-132">Interfacce Fusion</span><span class="sxs-lookup"><span data-stu-id="29129-132">Fusion Interfaces</span></span>](fusion-interfaces.md)
