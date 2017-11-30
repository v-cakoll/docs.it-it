---
title: Interfacce Fusion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- interfaces [.NET Framework fusion]
- fusion interfaces [.NET Framework]
- unmanaged interfaces [.NET Framework], fusion
ms.assetid: e2cf98b7-40c1-4f74-86c7-8a76dd9da677
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f1742025bed977dfd377a78db42df42c1bc43966
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="fusion-interfaces"></a><span data-ttu-id="d212a-102">Interfacce Fusion</span><span class="sxs-lookup"><span data-stu-id="d212a-102">Fusion Interfaces</span></span>
<span data-ttu-id="d212a-103">Questa sezione descrive le interfacce non gestite utilizzate dall'API Fusion per accedere alle proprietà di risorse dell'applicazione e per individuare le versioni corrette di tali risorse per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d212a-103">This section describes the unmanaged interfaces that the fusion API uses to access the properties of an application's resources and to locate the correct versions of those resources for the application.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d212a-104">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="d212a-104">In This Section</span></span>  
 [<span data-ttu-id="d212a-105">IAppIdAuthority (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="d212a-105">IAppIdAuthority Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iappidauthority-interface.md)  
 <span data-ttu-id="d212a-106">Fornisce metodi che generano e confrontare le chiavi per le identità delle applicazioni e i riferimenti.</span><span class="sxs-lookup"><span data-stu-id="d212a-106">Provides methods that generate and compare keys for application identities and references.</span></span>  
  
 [<span data-ttu-id="d212a-107">IAssemblyCache (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="d212a-107">IAssemblyCache Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)  
 <span data-ttu-id="d212a-108">Fornisce una rappresentazione della global assembly cache.</span><span class="sxs-lookup"><span data-stu-id="d212a-108">Provides a representation of the global assembly cache.</span></span>  
  
 [<span data-ttu-id="d212a-109">IAssemblyCacheItem (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="d212a-109">IAssemblyCacheItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md)  
 <span data-ttu-id="d212a-110">Rappresenta un singolo assembly nella global assembly cache.</span><span class="sxs-lookup"><span data-stu-id="d212a-110">Represents a single assembly in the global assembly cache.</span></span>  
  
 [<span data-ttu-id="d212a-111">IAssemblyEnum (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="d212a-111">IAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md)  
 <span data-ttu-id="d212a-112">Rappresenta un enumeratore per una matrice di `IAssemblyName` oggetti.</span><span class="sxs-lookup"><span data-stu-id="d212a-112">Represents an enumerator for an array of `IAssemblyName` objects.</span></span>  
  
 [<span data-ttu-id="d212a-113">IAssemblyName (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="d212a-113">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)  
 <span data-ttu-id="d212a-114">Fornisce metodi per la descrizione e l'utilizzo di un'identità univoca di assembly.</span><span class="sxs-lookup"><span data-stu-id="d212a-114">Provides methods for describing and working with an assembly's unique identity.</span></span>  
  
 [<span data-ttu-id="d212a-115">IDefinitionAppId (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="d212a-115">IDefinitionAppId Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/idefinitionappid-interface.md)  
 <span data-ttu-id="d212a-116">Rappresenta un identificatore univoco per il codice che definisce l'applicazione nell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="d212a-116">Represents a unique identifier for the code that defines the application in the current scope.</span></span>  
  
 [<span data-ttu-id="d212a-117">IDefinitionIdentity (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="d212a-117">IDefinitionIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md)  
 <span data-ttu-id="d212a-118">Rappresenta la firma univoca del codice che definisce l'applicazione nell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="d212a-118">Represents the unique signature of the code that defines the application in the current scope.</span></span>  
  
 [<span data-ttu-id="d212a-119">IEnumDefinitionIdentity (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="d212a-119">IEnumDefinitionIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ienumdefinitionidentity-interface.md)  
 <span data-ttu-id="d212a-120">Funge dall'enumeratore per un insieme di `IDefinitionIdentity` oggetti.</span><span class="sxs-lookup"><span data-stu-id="d212a-120">Serves as the enumerator for a collection of `IDefinitionIdentity` objects.</span></span>  
  
 [<span data-ttu-id="d212a-121">IEnumIDENTITY_ATTRIBUTE (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="d212a-121">IEnumIDENTITY_ATTRIBUTE Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ienumidentity-attribute-interface.md)  
 <span data-ttu-id="d212a-122">Funge da un enumeratore per gli attributi dell'oggetto codice nell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="d212a-122">Serves as an enumerator for the attributes of the code object in the current scope.</span></span>  
  
 [<span data-ttu-id="d212a-123">IEnumReferenceIdentity (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="d212a-123">IEnumReferenceIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ienumreferenceidentity-interface.md)  
 <span data-ttu-id="d212a-124">Funge da un enumeratore per una raccolta di `IReferenceIdentity` oggetti.</span><span class="sxs-lookup"><span data-stu-id="d212a-124">Serves as an enumerator for a collection of `IReferenceIdentity` objects.</span></span>  
  
 [<span data-ttu-id="d212a-125">IIdentityAuthority (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="d212a-125">IIdentityAuthority Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iidentityauthority-interface.md)  
 <span data-ttu-id="d212a-126">Gestisce le chiavi di identità per gli oggetti di codice.</span><span class="sxs-lookup"><span data-stu-id="d212a-126">Manages identity keys for code objects.</span></span>  
  
 [<span data-ttu-id="d212a-127">IInstallReferenceEnum (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="d212a-127">IInstallReferenceEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md)  
 <span data-ttu-id="d212a-128">Rappresenta un enumeratore per gli assembly di riferimento installati nella global assembly cache.</span><span class="sxs-lookup"><span data-stu-id="d212a-128">Represents an enumerator for the referenced assemblies installed in the global assembly cache.</span></span>  
  
 [<span data-ttu-id="d212a-129">IInstallReferenceItem (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="d212a-129">IInstallReferenceItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md)  
 <span data-ttu-id="d212a-130">Rappresenta un elemento installato nella global assembly cache.</span><span class="sxs-lookup"><span data-stu-id="d212a-130">Represents an item installed in the global assembly cache.</span></span>  
  
 [<span data-ttu-id="d212a-131">IReferenceAppId (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="d212a-131">IReferenceAppId Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ireferenceappid-interface.md)  
 <span data-ttu-id="d212a-132">Rappresenta un riferimento all'identificatore univoco per l'applicazione nell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="d212a-132">Represents a reference to the unique identifier for the application in the current scope.</span></span>  
  
 [<span data-ttu-id="d212a-133">IReferenceIdentity (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="d212a-133">IReferenceIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md)  
 <span data-ttu-id="d212a-134">Rappresenta un riferimento alla firma univoca di un oggetto di codice.</span><span class="sxs-lookup"><span data-stu-id="d212a-134">Represents a reference to the unique signature of a code object.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="d212a-135">Riferimento</span><span class="sxs-lookup"><span data-stu-id="d212a-135">Reference</span></span>  
 <xref:System.Reflection>  
  
 <xref:System.Reflection.Emit>  
  
## <a name="related-sections"></a><span data-ttu-id="d212a-136">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="d212a-136">Related Sections</span></span>  
 [<span data-ttu-id="d212a-137">Funzioni statiche globali Fusion</span><span class="sxs-lookup"><span data-stu-id="d212a-137">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)  
  
 [<span data-ttu-id="d212a-138">Enumerazioni Fusion</span><span class="sxs-lookup"><span data-stu-id="d212a-138">Fusion Enumerations</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)  
  
 [<span data-ttu-id="d212a-139">Strutture Fusion</span><span class="sxs-lookup"><span data-stu-id="d212a-139">Fusion Structures</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-structures.md)
