---
title: Costanti (riferimenti alle API non gestite)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- constants for unmanaged API [.NET Framework]
- native API reference [.NET Framework], constants
- unmanaged API reference [.NET Framework], constants
ms.assetid: 77526f65-b71c-4483-9d19-3a3751fd8a45
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e086e856bb7a872b14815825f78d208ff5296899
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="constants-unmanaged-api-reference"></a><span data-ttu-id="08a2e-102">Costanti (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="08a2e-102">Constants (Unmanaged API Reference)</span></span>
<span data-ttu-id="08a2e-103">Questo argomento descrive il tipo di linguaggio, fornitore di linguaggio e costanti di tipo di documento che sono definite in CorSym.idl.</span><span class="sxs-lookup"><span data-stu-id="08a2e-103">This topic describes the language type, language vendor, and document type constants that are defined in CorSym.idl.</span></span>  
  
## <a name="language-type-constants"></a><span data-ttu-id="08a2e-104">Costanti del tipo di linguaggio</span><span class="sxs-lookup"><span data-stu-id="08a2e-104">Language Type Constants</span></span>  
 <span data-ttu-id="08a2e-105">Nella tabella seguente viene illustrato come linguaggio di costanti di tipo, che rappresentano i GUID che identificano i linguaggi di programmazione.</span><span class="sxs-lookup"><span data-stu-id="08a2e-105">The following table shows language type constants, which represent GUIDs that identify programming languages.</span></span>  
  
|<span data-ttu-id="08a2e-106">Simbolo</span><span class="sxs-lookup"><span data-stu-id="08a2e-106">Symbol</span></span>|<span data-ttu-id="08a2e-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="08a2e-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="08a2e-108">CorSym_LanguageType_C</span><span class="sxs-lookup"><span data-stu-id="08a2e-108">CorSym_LanguageType_C</span></span>|<span data-ttu-id="08a2e-109">Indica il linguaggio C.</span><span class="sxs-lookup"><span data-stu-id="08a2e-109">Indicates the C language.</span></span>|  
|<span data-ttu-id="08a2e-110">CorSym_LanguageType_CPlusPlus</span><span class="sxs-lookup"><span data-stu-id="08a2e-110">CorSym_LanguageType_CPlusPlus</span></span>|<span data-ttu-id="08a2e-111">Indica il linguaggio C++.</span><span class="sxs-lookup"><span data-stu-id="08a2e-111">Indicates the C++ language.</span></span>|  
|<span data-ttu-id="08a2e-112">CorSym_LanguageType_CSharp</span><span class="sxs-lookup"><span data-stu-id="08a2e-112">CorSym_LanguageType_CSharp</span></span>|<span data-ttu-id="08a2e-113">Indica il linguaggio c#.</span><span class="sxs-lookup"><span data-stu-id="08a2e-113">Indicates the C# language.</span></span>|  
|<span data-ttu-id="08a2e-114">CorSym_LanguageType_Basic</span><span class="sxs-lookup"><span data-stu-id="08a2e-114">CorSym_LanguageType_Basic</span></span>|<span data-ttu-id="08a2e-115">Indica la lingua di base.</span><span class="sxs-lookup"><span data-stu-id="08a2e-115">Indicates the Basic language.</span></span>|  
|<span data-ttu-id="08a2e-116">CorSym_LanguageType_Java</span><span class="sxs-lookup"><span data-stu-id="08a2e-116">CorSym_LanguageType_Java</span></span>|<span data-ttu-id="08a2e-117">Indica il linguaggio Java.</span><span class="sxs-lookup"><span data-stu-id="08a2e-117">Indicates the Java language.</span></span>|  
|<span data-ttu-id="08a2e-118">CorSym_LanguageType_Cobol</span><span class="sxs-lookup"><span data-stu-id="08a2e-118">CorSym_LanguageType_Cobol</span></span>|<span data-ttu-id="08a2e-119">Indica la lingua COBOL.</span><span class="sxs-lookup"><span data-stu-id="08a2e-119">Indicates the COBOL language.</span></span>|  
|<span data-ttu-id="08a2e-120">CorSym_LanguageType_Pascal</span><span class="sxs-lookup"><span data-stu-id="08a2e-120">CorSym_LanguageType_Pascal</span></span>|<span data-ttu-id="08a2e-121">Indica la lingua Pascal.</span><span class="sxs-lookup"><span data-stu-id="08a2e-121">Indicates the Pascal language.</span></span>|  
|<span data-ttu-id="08a2e-122">CorSym_LanguageType_ILAssembly</span><span class="sxs-lookup"><span data-stu-id="08a2e-122">CorSym_LanguageType_ILAssembly</span></span>|<span data-ttu-id="08a2e-123">Indica il codice di assembly di Microsoft intermediate language (MSIL).</span><span class="sxs-lookup"><span data-stu-id="08a2e-123">Indicates the Microsoft intermediate language (MSIL) assembly code.</span></span>|  
|<span data-ttu-id="08a2e-124">CorSym_LanguageType_JScript</span><span class="sxs-lookup"><span data-stu-id="08a2e-124">CorSym_LanguageType_JScript</span></span>|<span data-ttu-id="08a2e-125">Indica il linguaggio JScript.</span><span class="sxs-lookup"><span data-stu-id="08a2e-125">Indicates the JScript language.</span></span>|  
|<span data-ttu-id="08a2e-126">CorSym_LanguageType_SMC</span><span class="sxs-lookup"><span data-stu-id="08a2e-126">CorSym_LanguageType_SMC</span></span>|<span data-ttu-id="08a2e-127">Indica il linguaggio SMC.</span><span class="sxs-lookup"><span data-stu-id="08a2e-127">Indicates the SMC language.</span></span>|  
|<span data-ttu-id="08a2e-128">CorSym_LanguageType_MCPlusPlus</span><span class="sxs-lookup"><span data-stu-id="08a2e-128">CorSym_LanguageType_MCPlusPlus</span></span>|<span data-ttu-id="08a2e-129">Indica il linguaggio C++ abilitato per .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="08a2e-129">Indicates the C++ language enabled for the .NET Framework.</span></span>|  
  
## <a name="language-vendor-constants"></a><span data-ttu-id="08a2e-130">Costanti di fornitore di linguaggio</span><span class="sxs-lookup"><span data-stu-id="08a2e-130">Language Vendor Constants</span></span>  
 <span data-ttu-id="08a2e-131">Nella tabella seguente viene illustrato come linguaggio costanti fornitore, che rappresentano i GUID che identificano i fornitori dei linguaggi di programmazione.</span><span class="sxs-lookup"><span data-stu-id="08a2e-131">The following table shows language vendor constants, which represent GUIDs that identify programming language vendors.</span></span>  
  
|<span data-ttu-id="08a2e-132">Simbolo</span><span class="sxs-lookup"><span data-stu-id="08a2e-132">Symbol</span></span>|<span data-ttu-id="08a2e-133">Descrizione</span><span class="sxs-lookup"><span data-stu-id="08a2e-133">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="08a2e-134">CorSym_LanguageVendor_Microsoft</span><span class="sxs-lookup"><span data-stu-id="08a2e-134">CorSym_LanguageVendor_Microsoft</span></span>|<span data-ttu-id="08a2e-135">Indica a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="08a2e-135">Indicates Microsoft.</span></span>|  
  
## <a name="document-type-constants"></a><span data-ttu-id="08a2e-136">Costanti del tipo di documento</span><span class="sxs-lookup"><span data-stu-id="08a2e-136">Document Type Constants</span></span>  
 <span data-ttu-id="08a2e-137">Nella tabella seguente viene illustrato come documento costanti di tipo, che rappresentano i GUID che identificano i tipi di documento.</span><span class="sxs-lookup"><span data-stu-id="08a2e-137">The following table shows document type constants, which represent GUIDs that identify document types.</span></span>  
  
|<span data-ttu-id="08a2e-138">Simbolo</span><span class="sxs-lookup"><span data-stu-id="08a2e-138">Symbol</span></span>|<span data-ttu-id="08a2e-139">Descrizione</span><span class="sxs-lookup"><span data-stu-id="08a2e-139">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="08a2e-140">CorSym_DocumentType_Text</span><span class="sxs-lookup"><span data-stu-id="08a2e-140">CorSym_DocumentType_Text</span></span>|<span data-ttu-id="08a2e-141">Indica un documento di testo.</span><span class="sxs-lookup"><span data-stu-id="08a2e-141">Indicates a text document.</span></span>|  
|<span data-ttu-id="08a2e-142">CorSym_DocumentType_MC</span><span class="sxs-lookup"><span data-stu-id="08a2e-142">CorSym_DocumentType_MC</span></span>|<span data-ttu-id="08a2e-143">Indica un documento non di testo.</span><span class="sxs-lookup"><span data-stu-id="08a2e-143">Indicates a non-text document.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="08a2e-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="08a2e-144">See Also</span></span>  
 [<span data-ttu-id="08a2e-145">Riferimenti alle API non gestite</span><span class="sxs-lookup"><span data-stu-id="08a2e-145">Unmanaged API Reference</span></span>](../../../docs/framework/unmanaged-api/index.md)
