---
title: Interfacce Fusion
ms.date: 03/30/2017
helpviewer_keywords:
- interfaces [.NET Framework fusion]
- fusion interfaces [.NET Framework]
- unmanaged interfaces [.NET Framework], fusion
ms.assetid: e2cf98b7-40c1-4f74-86c7-8a76dd9da677
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ec2fd3b309820f2bfb7f6091cc3db720db497408
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33434893"
---
# <a name="fusion-interfaces"></a><span data-ttu-id="22b5f-102">Interfacce Fusion</span><span class="sxs-lookup"><span data-stu-id="22b5f-102">Fusion Interfaces</span></span>
<span data-ttu-id="22b5f-103">Questa sezione descrive le interfacce non gestite utilizzate dall'API Fusion per accedere alle proprietà di risorse dell'applicazione e per individuare le versioni corrette di tali risorse per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="22b5f-103">This section describes the unmanaged interfaces that the fusion API uses to access the properties of an application's resources and to locate the correct versions of those resources for the application.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="22b5f-104">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="22b5f-104">In This Section</span></span>  
 [<span data-ttu-id="22b5f-105">Interfaccia IAppIdAuthority</span><span class="sxs-lookup"><span data-stu-id="22b5f-105">IAppIdAuthority Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iappidauthority-interface.md)  
 <span data-ttu-id="22b5f-106">Fornisce metodi che generano e confrontare le chiavi per le identità delle applicazioni e i riferimenti.</span><span class="sxs-lookup"><span data-stu-id="22b5f-106">Provides methods that generate and compare keys for application identities and references.</span></span>  
  
 [<span data-ttu-id="22b5f-107">Interfaccia IAssemblyCache</span><span class="sxs-lookup"><span data-stu-id="22b5f-107">IAssemblyCache Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)  
 <span data-ttu-id="22b5f-108">Fornisce una rappresentazione della global assembly cache.</span><span class="sxs-lookup"><span data-stu-id="22b5f-108">Provides a representation of the global assembly cache.</span></span>  
  
 [<span data-ttu-id="22b5f-109">Interfaccia IAssemblyCacheItem</span><span class="sxs-lookup"><span data-stu-id="22b5f-109">IAssemblyCacheItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md)  
 <span data-ttu-id="22b5f-110">Rappresenta un singolo assembly nella global assembly cache.</span><span class="sxs-lookup"><span data-stu-id="22b5f-110">Represents a single assembly in the global assembly cache.</span></span>  
  
 [<span data-ttu-id="22b5f-111">Interfaccia IAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="22b5f-111">IAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md)  
 <span data-ttu-id="22b5f-112">Rappresenta un enumeratore per una matrice di `IAssemblyName` oggetti.</span><span class="sxs-lookup"><span data-stu-id="22b5f-112">Represents an enumerator for an array of `IAssemblyName` objects.</span></span>  
  
 [<span data-ttu-id="22b5f-113">Interfaccia IAssemblyName</span><span class="sxs-lookup"><span data-stu-id="22b5f-113">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)  
 <span data-ttu-id="22b5f-114">Fornisce metodi per la descrizione e l'utilizzo di un'identità univoca di assembly.</span><span class="sxs-lookup"><span data-stu-id="22b5f-114">Provides methods for describing and working with an assembly's unique identity.</span></span>  
  
 [<span data-ttu-id="22b5f-115">Interfaccia IDefinitionAppId</span><span class="sxs-lookup"><span data-stu-id="22b5f-115">IDefinitionAppId Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/idefinitionappid-interface.md)  
 <span data-ttu-id="22b5f-116">Rappresenta un identificatore univoco per il codice che definisce l'applicazione nell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="22b5f-116">Represents a unique identifier for the code that defines the application in the current scope.</span></span>  
  
 [<span data-ttu-id="22b5f-117">Interfaccia IDefinitionIdentity</span><span class="sxs-lookup"><span data-stu-id="22b5f-117">IDefinitionIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md)  
 <span data-ttu-id="22b5f-118">Rappresenta la firma univoca del codice che definisce l'applicazione nell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="22b5f-118">Represents the unique signature of the code that defines the application in the current scope.</span></span>  
  
 [<span data-ttu-id="22b5f-119">Interfaccia IEnumDefinitionIdentity</span><span class="sxs-lookup"><span data-stu-id="22b5f-119">IEnumDefinitionIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ienumdefinitionidentity-interface.md)  
 <span data-ttu-id="22b5f-120">Funge dall'enumeratore per un insieme di `IDefinitionIdentity` oggetti.</span><span class="sxs-lookup"><span data-stu-id="22b5f-120">Serves as the enumerator for a collection of `IDefinitionIdentity` objects.</span></span>  
  
 [<span data-ttu-id="22b5f-121">Interfaccia IEnumIDENTITY_ATTRIBUTE</span><span class="sxs-lookup"><span data-stu-id="22b5f-121">IEnumIDENTITY_ATTRIBUTE Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ienumidentity-attribute-interface.md)  
 <span data-ttu-id="22b5f-122">Funge da un enumeratore per gli attributi dell'oggetto codice nell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="22b5f-122">Serves as an enumerator for the attributes of the code object in the current scope.</span></span>  
  
 [<span data-ttu-id="22b5f-123">Interfaccia IEnumReferenceIdentity</span><span class="sxs-lookup"><span data-stu-id="22b5f-123">IEnumReferenceIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ienumreferenceidentity-interface.md)  
 <span data-ttu-id="22b5f-124">Funge da un enumeratore per una raccolta di `IReferenceIdentity` oggetti.</span><span class="sxs-lookup"><span data-stu-id="22b5f-124">Serves as an enumerator for a collection of `IReferenceIdentity` objects.</span></span>  
  
 [<span data-ttu-id="22b5f-125">Interfaccia IIdentityAuthority</span><span class="sxs-lookup"><span data-stu-id="22b5f-125">IIdentityAuthority Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iidentityauthority-interface.md)  
 <span data-ttu-id="22b5f-126">Gestisce le chiavi di identità per gli oggetti di codice.</span><span class="sxs-lookup"><span data-stu-id="22b5f-126">Manages identity keys for code objects.</span></span>  
  
 [<span data-ttu-id="22b5f-127">Interfaccia IInstallReferenceEnum</span><span class="sxs-lookup"><span data-stu-id="22b5f-127">IInstallReferenceEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md)  
 <span data-ttu-id="22b5f-128">Rappresenta un enumeratore per gli assembly di riferimento installati nella global assembly cache.</span><span class="sxs-lookup"><span data-stu-id="22b5f-128">Represents an enumerator for the referenced assemblies installed in the global assembly cache.</span></span>  
  
 [<span data-ttu-id="22b5f-129">Interfaccia IInstallReferenceItem</span><span class="sxs-lookup"><span data-stu-id="22b5f-129">IInstallReferenceItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md)  
 <span data-ttu-id="22b5f-130">Rappresenta un elemento installato nella global assembly cache.</span><span class="sxs-lookup"><span data-stu-id="22b5f-130">Represents an item installed in the global assembly cache.</span></span>  
  
 [<span data-ttu-id="22b5f-131">Interfaccia IReferenceAppId</span><span class="sxs-lookup"><span data-stu-id="22b5f-131">IReferenceAppId Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ireferenceappid-interface.md)  
 <span data-ttu-id="22b5f-132">Rappresenta un riferimento all'identificatore univoco per l'applicazione nell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="22b5f-132">Represents a reference to the unique identifier for the application in the current scope.</span></span>  
  
 [<span data-ttu-id="22b5f-133">Interfaccia IReferenceIdentity</span><span class="sxs-lookup"><span data-stu-id="22b5f-133">IReferenceIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md)  
 <span data-ttu-id="22b5f-134">Rappresenta un riferimento alla firma univoca di un oggetto di codice.</span><span class="sxs-lookup"><span data-stu-id="22b5f-134">Represents a reference to the unique signature of a code object.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="22b5f-135">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="22b5f-135">Reference</span></span>  
 <xref:System.Reflection>  
  
 <xref:System.Reflection.Emit>  
  
## <a name="related-sections"></a><span data-ttu-id="22b5f-136">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="22b5f-136">Related Sections</span></span>  
 [<span data-ttu-id="22b5f-137">Funzioni statiche globali Fusion</span><span class="sxs-lookup"><span data-stu-id="22b5f-137">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)  
  
 [<span data-ttu-id="22b5f-138">Enumerazioni Fusion</span><span class="sxs-lookup"><span data-stu-id="22b5f-138">Fusion Enumerations</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)  
  
 [<span data-ttu-id="22b5f-139">Strutture Fusion</span><span class="sxs-lookup"><span data-stu-id="22b5f-139">Fusion Structures</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-structures.md)
