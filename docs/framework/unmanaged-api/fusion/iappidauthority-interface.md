---
title: Interfaccia IAppIdAuthority
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IAppIdAuthority
api_location: fusion.dll
api_type: COM
f1_keywords: IAppIdAuthority
helpviewer_keywords: IAppIdAuthority interface [.NET Framework fusion]
ms.assetid: ec354fa1-1efd-41b0-bc43-b90597b6e253
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 07bfd26a43d264babc9854b0fd0da909dd329405
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="iappidauthority-interface"></a><span data-ttu-id="d3eb2-102">Interfaccia IAppIdAuthority</span><span class="sxs-lookup"><span data-stu-id="d3eb2-102">IAppIdAuthority Interface</span></span>
<span data-ttu-id="d3eb2-103">Fornisce metodi che generano e confrontare le chiavi per le identità delle applicazioni e i riferimenti.</span><span class="sxs-lookup"><span data-stu-id="d3eb2-103">Provides methods that generate and compare keys for application identities and references.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d3eb2-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="d3eb2-104">Methods</span></span>  
  
|<span data-ttu-id="d3eb2-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="d3eb2-105">Method</span></span>|<span data-ttu-id="d3eb2-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d3eb2-106">Description</span></span>|  
|------------|-----------------|  
|`IAppIdAuthority::AreDefinitionsEqual`|<span data-ttu-id="d3eb2-107">Ottiene un valore che indica se le due [IDefinitionAppId](../../../../docs/framework/unmanaged-api/fusion/idefinitionappid-interface.md) istanze sono uguali.</span><span class="sxs-lookup"><span data-stu-id="d3eb2-107">Gets a value that indicates whether the two specified [IDefinitionAppId](../../../../docs/framework/unmanaged-api/fusion/idefinitionappid-interface.md) instances are equal.</span></span> <span data-ttu-id="d3eb2-108">È possibile passare il valore del flag IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION per ignorare le rispettive informazioni sulla versione.</span><span class="sxs-lookup"><span data-stu-id="d3eb2-108">You can pass the flag value IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::AreReferencesEqual`|<span data-ttu-id="d3eb2-109">Ottiene un valore che indica se le due [IReferenceAppId](../../../../docs/framework/unmanaged-api/fusion/ireferenceappid-interface.md) istanze sono uguali.</span><span class="sxs-lookup"><span data-stu-id="d3eb2-109">Gets a value that indicates whether the two specified [IReferenceAppId](../../../../docs/framework/unmanaged-api/fusion/ireferenceappid-interface.md) instances are equal.</span></span> <span data-ttu-id="d3eb2-110">È possibile passare il valore del flag IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION per ignorare le rispettive informazioni sulla versione.</span><span class="sxs-lookup"><span data-stu-id="d3eb2-110">You can pass the flag value IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::AreTextualDefinitionsEqual`|<span data-ttu-id="d3eb2-111">Ottiene un valore che indica se le due definizioni di stringa specificato sono uguali.</span><span class="sxs-lookup"><span data-stu-id="d3eb2-111">Gets a value that indicates whether the two specified string definitions are equal.</span></span> <span data-ttu-id="d3eb2-112">È possibile passare il valore del flag IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION per ignorare le rispettive informazioni sulla versione.</span><span class="sxs-lookup"><span data-stu-id="d3eb2-112">You can pass the flag value IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::AreTextualReferencesEqual`|<span data-ttu-id="d3eb2-113">Ottiene un valore che indica se i due riferimenti di stringa specificato sono uguali.</span><span class="sxs-lookup"><span data-stu-id="d3eb2-113">Gets a value that indicates whether the two specified string references are equal.</span></span> <span data-ttu-id="d3eb2-114">È possibile passare il valore del flag IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION per ignorare le rispettive informazioni sulla versione.</span><span class="sxs-lookup"><span data-stu-id="d3eb2-114">You can pass the flag value IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::CreateDefinition`|<span data-ttu-id="d3eb2-115">Ottiene un puntatore a interfaccia a un oggetto appena generato `IDefinitionAppId` istanza che rappresenta l'assembly nell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="d3eb2-115">Gets an interface pointer to a newly generated `IDefinitionAppId` instance that represents the assembly in the current scope.</span></span>|  
|`IAppIdAuthority::CreateReference`|<span data-ttu-id="d3eb2-116">Ottiene un puntatore a interfaccia a un oggetto appena creato `IReferenceAppId` che rappresenta l'assembly nell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="d3eb2-116">Gets an interface pointer to a newly created `IReferenceAppId` that represents the assembly in the current scope.</span></span>|  
|`IAppIdAuthority::DefinitionToText`|<span data-ttu-id="d3eb2-117">Ottiene una versione stringa dell'oggetto specificato `IDefinitionAppId`, utilizzando i valori di flag specificato.</span><span class="sxs-lookup"><span data-stu-id="d3eb2-117">Gets a string version of the specified `IDefinitionAppId`, using the specified flag values.</span></span>|  
|`IAppIdAuthority::DoesDefinitionMatchReference`|<span data-ttu-id="d3eb2-118">Ottiene un valore che indica se l'oggetto specificato `IDefinitionAppId` e `IReferenceAppId` rappresentano lo stesso assembly.</span><span class="sxs-lookup"><span data-stu-id="d3eb2-118">Gets a value that indicates whether the specified `IDefinitionAppId` and `IReferenceAppId` represent the same assembly.</span></span>|  
|`IAppIdAuthority::DoesTextualDefinitionMatchTextualReference`|<span data-ttu-id="d3eb2-119">Ottiene un valore che indica se la stringa di definizione specificato e una stringa di riferimento rappresentano lo stesso assembly.</span><span class="sxs-lookup"><span data-stu-id="d3eb2-119">Gets a value that indicates whether the specified definition string and reference string represent the same assembly.</span></span>|  
|`IAppIdAuthority::GenerateDefinitionKey`|<span data-ttu-id="d3eb2-120">Ottiene una chiave di stringa che rappresenta l'oggetto specificato `IDefinitionAppId` istanza.</span><span class="sxs-lookup"><span data-stu-id="d3eb2-120">Gets a string key that represents the specified `IDefinitionAppId` instance.</span></span>|  
|`IAppIdAuthority::GenerateReferenceKey`|<span data-ttu-id="d3eb2-121">Ottiene una chiave di stringa che rappresenta l'oggetto specificato `IReferenceAppId` istanza.</span><span class="sxs-lookup"><span data-stu-id="d3eb2-121">Gets a string key that represents the specified `IReferenceAppId` instance.</span></span>|  
|`IAppIdAuthority::HashDefinition`|<span data-ttu-id="d3eb2-122">Ottiene una chiave hash per l'oggetto specificato `IDefinitionAppId` istanza.</span><span class="sxs-lookup"><span data-stu-id="d3eb2-122">Gets a hash key for the specified `IDefinitionAppId` instance.</span></span>|  
|`IAppIdAuthority::HashReference`|<span data-ttu-id="d3eb2-123">Ottiene una chiave hash per l'oggetto specificato `IReferenceAppId` istanza.</span><span class="sxs-lookup"><span data-stu-id="d3eb2-123">Gets a hash key for the specified `IReferenceAppId` instance.</span></span>|  
|`IAppIdAuthority::ReferenceToText`|<span data-ttu-id="d3eb2-124">Ottiene una versione stringa dell'oggetto specificato `IReferenceAppId`, utilizzando i valori di flag specificato.</span><span class="sxs-lookup"><span data-stu-id="d3eb2-124">Gets a string version of the specified `IReferenceAppId`, using the specified flag values.</span></span>|  
|`IAppIdAuthority::TextToDefinition`|<span data-ttu-id="d3eb2-125">Ottiene un puntatore a interfaccia a un `IDefinitionAppId` istanza che rappresenta l'assembly a cui fa riferimento la chiave di stringa specificata.</span><span class="sxs-lookup"><span data-stu-id="d3eb2-125">Gets an interface pointer to an `IDefinitionAppId` instance that represents the assembly referenced by the specified string key.</span></span>|  
|`IAppIdAuthority::TextToReference`|<span data-ttu-id="d3eb2-126">Ottiene un puntatore a interfaccia a un `IReferenceAppId` istanza che rappresenta l'assembly a cui fa riferimento la chiave di stringa specificata.</span><span class="sxs-lookup"><span data-stu-id="d3eb2-126">Gets an interface pointer to an `IReferenceAppId` instance that represents the assembly referenced by the specified string key.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d3eb2-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d3eb2-127">Requirements</span></span>  
 <span data-ttu-id="d3eb2-128">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d3eb2-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d3eb2-129">**Intestazione:** Isolation. h</span><span class="sxs-lookup"><span data-stu-id="d3eb2-129">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="d3eb2-130">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d3eb2-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3eb2-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d3eb2-131">See Also</span></span>  
 [<span data-ttu-id="d3eb2-132">Fusion (interfacce)</span><span class="sxs-lookup"><span data-stu-id="d3eb2-132">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
