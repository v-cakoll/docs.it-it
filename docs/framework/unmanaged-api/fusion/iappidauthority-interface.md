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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 724ee01e91f1e9f4e34d2262610152a977ed4f53
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59206655"
---
# <a name="iappidauthority-interface"></a><span data-ttu-id="d7f18-102">Interfaccia IAppIdAuthority</span><span class="sxs-lookup"><span data-stu-id="d7f18-102">IAppIdAuthority Interface</span></span>
<span data-ttu-id="d7f18-103">Fornisce metodi che generano e confrontare le chiavi per le identità dell'applicazione e i riferimenti.</span><span class="sxs-lookup"><span data-stu-id="d7f18-103">Provides methods that generate and compare keys for application identities and references.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d7f18-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="d7f18-104">Methods</span></span>  
  
|<span data-ttu-id="d7f18-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="d7f18-105">Method</span></span>|<span data-ttu-id="d7f18-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d7f18-106">Description</span></span>|  
|------------|-----------------|  
|`IAppIdAuthority::AreDefinitionsEqual`|<span data-ttu-id="d7f18-107">Ottiene un valore che indica se le due [IDefinitionAppId](../../../../docs/framework/unmanaged-api/fusion/idefinitionappid-interface.md) istanze sono uguali.</span><span class="sxs-lookup"><span data-stu-id="d7f18-107">Gets a value that indicates whether the two specified [IDefinitionAppId](../../../../docs/framework/unmanaged-api/fusion/idefinitionappid-interface.md) instances are equal.</span></span> <span data-ttu-id="d7f18-108">È possibile passare il valore del flag IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION per ignorare le rispettive informazioni sulla versione.</span><span class="sxs-lookup"><span data-stu-id="d7f18-108">You can pass the flag value IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::AreReferencesEqual`|<span data-ttu-id="d7f18-109">Ottiene un valore che indica se le due [IReferenceAppId](../../../../docs/framework/unmanaged-api/fusion/ireferenceappid-interface.md) istanze sono uguali.</span><span class="sxs-lookup"><span data-stu-id="d7f18-109">Gets a value that indicates whether the two specified [IReferenceAppId](../../../../docs/framework/unmanaged-api/fusion/ireferenceappid-interface.md) instances are equal.</span></span> <span data-ttu-id="d7f18-110">È possibile passare il valore del flag IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION per ignorare le rispettive informazioni sulla versione.</span><span class="sxs-lookup"><span data-stu-id="d7f18-110">You can pass the flag value IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::AreTextualDefinitionsEqual`|<span data-ttu-id="d7f18-111">Ottiene un valore che indica se le due definizioni di stringa specificato sono uguali.</span><span class="sxs-lookup"><span data-stu-id="d7f18-111">Gets a value that indicates whether the two specified string definitions are equal.</span></span> <span data-ttu-id="d7f18-112">È possibile passare il valore del flag IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION per ignorare le rispettive informazioni sulla versione.</span><span class="sxs-lookup"><span data-stu-id="d7f18-112">You can pass the flag value IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::AreTextualReferencesEqual`|<span data-ttu-id="d7f18-113">Ottiene un valore che indica se i due riferimenti di stringa specificato sono uguali.</span><span class="sxs-lookup"><span data-stu-id="d7f18-113">Gets a value that indicates whether the two specified string references are equal.</span></span> <span data-ttu-id="d7f18-114">È possibile passare il valore del flag IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION per ignorare le rispettive informazioni sulla versione.</span><span class="sxs-lookup"><span data-stu-id="d7f18-114">You can pass the flag value IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::CreateDefinition`|<span data-ttu-id="d7f18-115">Ottiene un puntatore a interfaccia a un nuovo `IDefinitionAppId` istanza che rappresenta l'assembly nell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="d7f18-115">Gets an interface pointer to a newly generated `IDefinitionAppId` instance that represents the assembly in the current scope.</span></span>|  
|`IAppIdAuthority::CreateReference`|<span data-ttu-id="d7f18-116">Ottiene un puntatore di interfaccia di un nuovo `IReferenceAppId` che rappresenta l'assembly nell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="d7f18-116">Gets an interface pointer to a newly created `IReferenceAppId` that represents the assembly in the current scope.</span></span>|  
|`IAppIdAuthority::DefinitionToText`|<span data-ttu-id="d7f18-117">Ottiene una versione stringa dell'oggetto specificato `IDefinitionAppId`, usando i valori di flag specificato.</span><span class="sxs-lookup"><span data-stu-id="d7f18-117">Gets a string version of the specified `IDefinitionAppId`, using the specified flag values.</span></span>|  
|`IAppIdAuthority::DoesDefinitionMatchReference`|<span data-ttu-id="d7f18-118">Ottiene un valore che indica se l'oggetto specificato `IDefinitionAppId` e `IReferenceAppId` rappresentano lo stesso assembly.</span><span class="sxs-lookup"><span data-stu-id="d7f18-118">Gets a value that indicates whether the specified `IDefinitionAppId` and `IReferenceAppId` represent the same assembly.</span></span>|  
|`IAppIdAuthority::DoesTextualDefinitionMatchTextualReference`|<span data-ttu-id="d7f18-119">Ottiene un valore che indica se la stringa di definizione specificato e una stringa di riferimento rappresentano lo stesso assembly.</span><span class="sxs-lookup"><span data-stu-id="d7f18-119">Gets a value that indicates whether the specified definition string and reference string represent the same assembly.</span></span>|  
|`IAppIdAuthority::GenerateDefinitionKey`|<span data-ttu-id="d7f18-120">Ottiene una chiave di stringa che rappresenta l'oggetto specificato `IDefinitionAppId` istanza.</span><span class="sxs-lookup"><span data-stu-id="d7f18-120">Gets a string key that represents the specified `IDefinitionAppId` instance.</span></span>|  
|`IAppIdAuthority::GenerateReferenceKey`|<span data-ttu-id="d7f18-121">Ottiene una chiave di stringa che rappresenta l'oggetto specificato `IReferenceAppId` istanza.</span><span class="sxs-lookup"><span data-stu-id="d7f18-121">Gets a string key that represents the specified `IReferenceAppId` instance.</span></span>|  
|`IAppIdAuthority::HashDefinition`|<span data-ttu-id="d7f18-122">Ottiene una chiave hash per l'oggetto specificato `IDefinitionAppId` istanza.</span><span class="sxs-lookup"><span data-stu-id="d7f18-122">Gets a hash key for the specified `IDefinitionAppId` instance.</span></span>|  
|`IAppIdAuthority::HashReference`|<span data-ttu-id="d7f18-123">Ottiene una chiave hash per l'oggetto specificato `IReferenceAppId` istanza.</span><span class="sxs-lookup"><span data-stu-id="d7f18-123">Gets a hash key for the specified `IReferenceAppId` instance.</span></span>|  
|`IAppIdAuthority::ReferenceToText`|<span data-ttu-id="d7f18-124">Ottiene una versione stringa dell'oggetto specificato `IReferenceAppId`, usando i valori di flag specificato.</span><span class="sxs-lookup"><span data-stu-id="d7f18-124">Gets a string version of the specified `IReferenceAppId`, using the specified flag values.</span></span>|  
|`IAppIdAuthority::TextToDefinition`|<span data-ttu-id="d7f18-125">Ottiene un puntatore a interfaccia per un `IDefinitionAppId` istanza che rappresenta l'assembly fa riferimento la chiave della stringa specificata.</span><span class="sxs-lookup"><span data-stu-id="d7f18-125">Gets an interface pointer to an `IDefinitionAppId` instance that represents the assembly referenced by the specified string key.</span></span>|  
|`IAppIdAuthority::TextToReference`|<span data-ttu-id="d7f18-126">Ottiene un puntatore a interfaccia per un `IReferenceAppId` istanza che rappresenta l'assembly fa riferimento la chiave della stringa specificata.</span><span class="sxs-lookup"><span data-stu-id="d7f18-126">Gets an interface pointer to an `IReferenceAppId` instance that represents the assembly referenced by the specified string key.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d7f18-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d7f18-127">Requirements</span></span>  
 <span data-ttu-id="d7f18-128">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d7f18-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7f18-129">**Intestazione:** Isolation. h</span><span class="sxs-lookup"><span data-stu-id="d7f18-129">**Header:** Isolation.h</span></span>  
  
 **<span data-ttu-id="d7f18-130">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="d7f18-130">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d7f18-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d7f18-131">See also</span></span>

- [<span data-ttu-id="d7f18-132">Interfacce Fusion</span><span class="sxs-lookup"><span data-stu-id="d7f18-132">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
