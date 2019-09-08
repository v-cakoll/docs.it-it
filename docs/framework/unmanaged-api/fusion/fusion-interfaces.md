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
ms.openlocfilehash: 1605605f8510f7ccf5f0bbf2f3f6b09050a16025
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795308"
---
# <a name="fusion-interfaces"></a><span data-ttu-id="a3b7c-102">Interfacce Fusion</span><span class="sxs-lookup"><span data-stu-id="a3b7c-102">Fusion Interfaces</span></span>
<span data-ttu-id="a3b7c-103">Questa sezione descrive le interfacce non gestite utilizzate dall'API Fusion per accedere alle proprietà delle risorse di un'applicazione e per individuare le versioni corrette delle risorse per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a3b7c-103">This section describes the unmanaged interfaces that the fusion API uses to access the properties of an application's resources and to locate the correct versions of those resources for the application.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a3b7c-104">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="a3b7c-104">In This Section</span></span>  
 [<span data-ttu-id="a3b7c-105">Interfaccia IAppIdAuthority</span><span class="sxs-lookup"><span data-stu-id="a3b7c-105">IAppIdAuthority Interface</span></span>](iappidauthority-interface.md)  
 <span data-ttu-id="a3b7c-106">Fornisce metodi che generano e confrontano le chiavi per le identità e i riferimenti dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a3b7c-106">Provides methods that generate and compare keys for application identities and references.</span></span>  
  
 [<span data-ttu-id="a3b7c-107">Interfaccia IAssemblyCache</span><span class="sxs-lookup"><span data-stu-id="a3b7c-107">IAssemblyCache Interface</span></span>](iassemblycache-interface.md)  
 <span data-ttu-id="a3b7c-108">Fornisce una rappresentazione del Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="a3b7c-108">Provides a representation of the global assembly cache.</span></span>  
  
 [<span data-ttu-id="a3b7c-109">Interfaccia IAssemblyCacheItem</span><span class="sxs-lookup"><span data-stu-id="a3b7c-109">IAssemblyCacheItem Interface</span></span>](iassemblycacheitem-interface.md)  
 <span data-ttu-id="a3b7c-110">Rappresenta un singolo assembly nel Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="a3b7c-110">Represents a single assembly in the global assembly cache.</span></span>  
  
 [<span data-ttu-id="a3b7c-111">Interfaccia IAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="a3b7c-111">IAssemblyEnum Interface</span></span>](iassemblyenum-interface.md)  
 <span data-ttu-id="a3b7c-112">Rappresenta un enumeratore per una matrice `IAssemblyName` di oggetti.</span><span class="sxs-lookup"><span data-stu-id="a3b7c-112">Represents an enumerator for an array of `IAssemblyName` objects.</span></span>  
  
 [<span data-ttu-id="a3b7c-113">Interfaccia IAssemblyName</span><span class="sxs-lookup"><span data-stu-id="a3b7c-113">IAssemblyName Interface</span></span>](iassemblyname-interface.md)  
 <span data-ttu-id="a3b7c-114">Fornisce metodi per la descrizione e l'utilizzo dell'identità univoca di un assembly.</span><span class="sxs-lookup"><span data-stu-id="a3b7c-114">Provides methods for describing and working with an assembly's unique identity.</span></span>  
  
 [<span data-ttu-id="a3b7c-115">Interfaccia IDefinitionAppId</span><span class="sxs-lookup"><span data-stu-id="a3b7c-115">IDefinitionAppId Interface</span></span>](idefinitionappid-interface.md)  
 <span data-ttu-id="a3b7c-116">Rappresenta un identificatore univoco per il codice che definisce l'applicazione nell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="a3b7c-116">Represents a unique identifier for the code that defines the application in the current scope.</span></span>  
  
 [<span data-ttu-id="a3b7c-117">Interfaccia IDefinitionIdentity</span><span class="sxs-lookup"><span data-stu-id="a3b7c-117">IDefinitionIdentity Interface</span></span>](idefinitionidentity-interface.md)  
 <span data-ttu-id="a3b7c-118">Rappresenta la firma univoca del codice che definisce l'applicazione nell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="a3b7c-118">Represents the unique signature of the code that defines the application in the current scope.</span></span>  
  
 [<span data-ttu-id="a3b7c-119">Interfaccia IEnumDefinitionIdentity</span><span class="sxs-lookup"><span data-stu-id="a3b7c-119">IEnumDefinitionIdentity Interface</span></span>](ienumdefinitionidentity-interface.md)  
 <span data-ttu-id="a3b7c-120">Funge da enumeratore per una raccolta di `IDefinitionIdentity` oggetti.</span><span class="sxs-lookup"><span data-stu-id="a3b7c-120">Serves as the enumerator for a collection of `IDefinitionIdentity` objects.</span></span>  
  
 [<span data-ttu-id="a3b7c-121">Interfaccia IEnumIDENTITY_ATTRIBUTE</span><span class="sxs-lookup"><span data-stu-id="a3b7c-121">IEnumIDENTITY_ATTRIBUTE Interface</span></span>](ienumidentity-attribute-interface.md)  
 <span data-ttu-id="a3b7c-122">Funge da enumeratore per gli attributi dell'oggetto di codice nell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="a3b7c-122">Serves as an enumerator for the attributes of the code object in the current scope.</span></span>  
  
 [<span data-ttu-id="a3b7c-123">Interfaccia IEnumReferenceIdentity</span><span class="sxs-lookup"><span data-stu-id="a3b7c-123">IEnumReferenceIdentity Interface</span></span>](ienumreferenceidentity-interface.md)  
 <span data-ttu-id="a3b7c-124">Funge da enumeratore per una raccolta di `IReferenceIdentity` oggetti.</span><span class="sxs-lookup"><span data-stu-id="a3b7c-124">Serves as an enumerator for a collection of `IReferenceIdentity` objects.</span></span>  
  
 [<span data-ttu-id="a3b7c-125">Interfaccia IIdentityAuthority</span><span class="sxs-lookup"><span data-stu-id="a3b7c-125">IIdentityAuthority Interface</span></span>](iidentityauthority-interface.md)  
 <span data-ttu-id="a3b7c-126">Gestisce chiavi di identità per oggetti di codice.</span><span class="sxs-lookup"><span data-stu-id="a3b7c-126">Manages identity keys for code objects.</span></span>  
  
 [<span data-ttu-id="a3b7c-127">Interfaccia IInstallReferenceEnum</span><span class="sxs-lookup"><span data-stu-id="a3b7c-127">IInstallReferenceEnum Interface</span></span>](iinstallreferenceenum-interface.md)  
 <span data-ttu-id="a3b7c-128">Rappresenta un enumeratore per gli assembly di riferimento installati nell'Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="a3b7c-128">Represents an enumerator for the referenced assemblies installed in the global assembly cache.</span></span>  
  
 [<span data-ttu-id="a3b7c-129">Interfaccia IInstallReferenceItem</span><span class="sxs-lookup"><span data-stu-id="a3b7c-129">IInstallReferenceItem Interface</span></span>](iinstallreferenceitem-interface.md)  
 <span data-ttu-id="a3b7c-130">Rappresenta un elemento installato nell'Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="a3b7c-130">Represents an item installed in the global assembly cache.</span></span>  
  
 [<span data-ttu-id="a3b7c-131">Interfaccia IReferenceAppId</span><span class="sxs-lookup"><span data-stu-id="a3b7c-131">IReferenceAppId Interface</span></span>](ireferenceappid-interface.md)  
 <span data-ttu-id="a3b7c-132">Rappresenta un riferimento all'identificatore univoco per l'applicazione nell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="a3b7c-132">Represents a reference to the unique identifier for the application in the current scope.</span></span>  
  
 [<span data-ttu-id="a3b7c-133">Interfaccia IReferenceIdentity</span><span class="sxs-lookup"><span data-stu-id="a3b7c-133">IReferenceIdentity Interface</span></span>](ireferenceidentity-interface.md)  
 <span data-ttu-id="a3b7c-134">Rappresenta un riferimento alla firma univoca di un oggetto di codice.</span><span class="sxs-lookup"><span data-stu-id="a3b7c-134">Represents a reference to the unique signature of a code object.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="a3b7c-135">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="a3b7c-135">Reference</span></span>  
 <xref:System.Reflection>  
  
 <xref:System.Reflection.Emit>  
  
## <a name="related-sections"></a><span data-ttu-id="a3b7c-136">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="a3b7c-136">Related Sections</span></span>  
 [<span data-ttu-id="a3b7c-137">Funzioni statiche globali Fusion</span><span class="sxs-lookup"><span data-stu-id="a3b7c-137">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)  
  
 [<span data-ttu-id="a3b7c-138">Enumerazioni Fusion</span><span class="sxs-lookup"><span data-stu-id="a3b7c-138">Fusion Enumerations</span></span>](fusion-enumerations.md)  
  
 [<span data-ttu-id="a3b7c-139">Strutture Fusion</span><span class="sxs-lookup"><span data-stu-id="a3b7c-139">Fusion Structures</span></span>](fusion-structures.md)
