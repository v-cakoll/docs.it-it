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
ms.openlocfilehash: 45e4d41c16695010dc452d2f22850d43f885974a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="constants-unmanaged-api-reference"></a><span data-ttu-id="d3bcb-102">Costanti (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="d3bcb-102">Constants (Unmanaged API Reference)</span></span>
<span data-ttu-id="d3bcb-103">Questo argomento descrive il tipo di linguaggio, fornitore di linguaggio e costanti di tipo di documento che sono definite in CorSym.idl.</span><span class="sxs-lookup"><span data-stu-id="d3bcb-103">This topic describes the language type, language vendor, and document type constants that are defined in CorSym.idl.</span></span>  
  
## <a name="language-type-constants"></a><span data-ttu-id="d3bcb-104">Costanti del tipo di linguaggio</span><span class="sxs-lookup"><span data-stu-id="d3bcb-104">Language Type Constants</span></span>  
 <span data-ttu-id="d3bcb-105">Nella tabella seguente viene illustrato come linguaggio di costanti di tipo, che rappresentano i GUID che identificano i linguaggi di programmazione.</span><span class="sxs-lookup"><span data-stu-id="d3bcb-105">The following table shows language type constants, which represent GUIDs that identify programming languages.</span></span>  
  
|<span data-ttu-id="d3bcb-106">Simbolo</span><span class="sxs-lookup"><span data-stu-id="d3bcb-106">Symbol</span></span>|<span data-ttu-id="d3bcb-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d3bcb-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="d3bcb-108">CorSym_LanguageType_C</span><span class="sxs-lookup"><span data-stu-id="d3bcb-108">CorSym_LanguageType_C</span></span>|<span data-ttu-id="d3bcb-109">Indica il linguaggio C.</span><span class="sxs-lookup"><span data-stu-id="d3bcb-109">Indicates the C language.</span></span>|  
|<span data-ttu-id="d3bcb-110">CorSym_LanguageType_CPlusPlus</span><span class="sxs-lookup"><span data-stu-id="d3bcb-110">CorSym_LanguageType_CPlusPlus</span></span>|<span data-ttu-id="d3bcb-111">Indica il linguaggio C++.</span><span class="sxs-lookup"><span data-stu-id="d3bcb-111">Indicates the C++ language.</span></span>|  
|<span data-ttu-id="d3bcb-112">CorSym_LanguageType_CSharp</span><span class="sxs-lookup"><span data-stu-id="d3bcb-112">CorSym_LanguageType_CSharp</span></span>|<span data-ttu-id="d3bcb-113">Indica il linguaggio c#.</span><span class="sxs-lookup"><span data-stu-id="d3bcb-113">Indicates the C# language.</span></span>|  
|<span data-ttu-id="d3bcb-114">CorSym_LanguageType_Basic</span><span class="sxs-lookup"><span data-stu-id="d3bcb-114">CorSym_LanguageType_Basic</span></span>|<span data-ttu-id="d3bcb-115">Indica la lingua di base.</span><span class="sxs-lookup"><span data-stu-id="d3bcb-115">Indicates the Basic language.</span></span>|  
|<span data-ttu-id="d3bcb-116">CorSym_LanguageType_Java</span><span class="sxs-lookup"><span data-stu-id="d3bcb-116">CorSym_LanguageType_Java</span></span>|<span data-ttu-id="d3bcb-117">Indica il linguaggio Java.</span><span class="sxs-lookup"><span data-stu-id="d3bcb-117">Indicates the Java language.</span></span>|  
|<span data-ttu-id="d3bcb-118">CorSym_LanguageType_Cobol</span><span class="sxs-lookup"><span data-stu-id="d3bcb-118">CorSym_LanguageType_Cobol</span></span>|<span data-ttu-id="d3bcb-119">Indica la lingua COBOL.</span><span class="sxs-lookup"><span data-stu-id="d3bcb-119">Indicates the COBOL language.</span></span>|  
|<span data-ttu-id="d3bcb-120">CorSym_LanguageType_Pascal</span><span class="sxs-lookup"><span data-stu-id="d3bcb-120">CorSym_LanguageType_Pascal</span></span>|<span data-ttu-id="d3bcb-121">Indica la lingua Pascal.</span><span class="sxs-lookup"><span data-stu-id="d3bcb-121">Indicates the Pascal language.</span></span>|  
|<span data-ttu-id="d3bcb-122">CorSym_LanguageType_ILAssembly</span><span class="sxs-lookup"><span data-stu-id="d3bcb-122">CorSym_LanguageType_ILAssembly</span></span>|<span data-ttu-id="d3bcb-123">Indica il codice di assembly di Microsoft intermediate language (MSIL).</span><span class="sxs-lookup"><span data-stu-id="d3bcb-123">Indicates the Microsoft intermediate language (MSIL) assembly code.</span></span>|  
|<span data-ttu-id="d3bcb-124">CorSym_LanguageType_JScript</span><span class="sxs-lookup"><span data-stu-id="d3bcb-124">CorSym_LanguageType_JScript</span></span>|<span data-ttu-id="d3bcb-125">Indica il linguaggio JScript.</span><span class="sxs-lookup"><span data-stu-id="d3bcb-125">Indicates the JScript language.</span></span>|  
|<span data-ttu-id="d3bcb-126">CorSym_LanguageType_SMC</span><span class="sxs-lookup"><span data-stu-id="d3bcb-126">CorSym_LanguageType_SMC</span></span>|<span data-ttu-id="d3bcb-127">Indica il linguaggio SMC.</span><span class="sxs-lookup"><span data-stu-id="d3bcb-127">Indicates the SMC language.</span></span>|  
|<span data-ttu-id="d3bcb-128">CorSym_LanguageType_MCPlusPlus</span><span class="sxs-lookup"><span data-stu-id="d3bcb-128">CorSym_LanguageType_MCPlusPlus</span></span>|<span data-ttu-id="d3bcb-129">Indica il linguaggio C++ abilitato per .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d3bcb-129">Indicates the C++ language enabled for the .NET Framework.</span></span>|  
  
## <a name="language-vendor-constants"></a><span data-ttu-id="d3bcb-130">Costanti di fornitore di linguaggio</span><span class="sxs-lookup"><span data-stu-id="d3bcb-130">Language Vendor Constants</span></span>  
 <span data-ttu-id="d3bcb-131">Nella tabella seguente viene illustrato come linguaggio costanti fornitore, che rappresentano i GUID che identificano i fornitori dei linguaggi di programmazione.</span><span class="sxs-lookup"><span data-stu-id="d3bcb-131">The following table shows language vendor constants, which represent GUIDs that identify programming language vendors.</span></span>  
  
|<span data-ttu-id="d3bcb-132">Simbolo</span><span class="sxs-lookup"><span data-stu-id="d3bcb-132">Symbol</span></span>|<span data-ttu-id="d3bcb-133">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d3bcb-133">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="d3bcb-134">CorSym_LanguageVendor_Microsoft</span><span class="sxs-lookup"><span data-stu-id="d3bcb-134">CorSym_LanguageVendor_Microsoft</span></span>|<span data-ttu-id="d3bcb-135">Indica a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d3bcb-135">Indicates Microsoft.</span></span>|  
  
## <a name="document-type-constants"></a><span data-ttu-id="d3bcb-136">Costanti del tipo di documento</span><span class="sxs-lookup"><span data-stu-id="d3bcb-136">Document Type Constants</span></span>  
 <span data-ttu-id="d3bcb-137">Nella tabella seguente viene illustrato come documento costanti di tipo, che rappresentano i GUID che identificano i tipi di documento.</span><span class="sxs-lookup"><span data-stu-id="d3bcb-137">The following table shows document type constants, which represent GUIDs that identify document types.</span></span>  
  
|<span data-ttu-id="d3bcb-138">Simbolo</span><span class="sxs-lookup"><span data-stu-id="d3bcb-138">Symbol</span></span>|<span data-ttu-id="d3bcb-139">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d3bcb-139">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="d3bcb-140">CorSym_DocumentType_Text</span><span class="sxs-lookup"><span data-stu-id="d3bcb-140">CorSym_DocumentType_Text</span></span>|<span data-ttu-id="d3bcb-141">Indica un documento di testo.</span><span class="sxs-lookup"><span data-stu-id="d3bcb-141">Indicates a text document.</span></span>|  
|<span data-ttu-id="d3bcb-142">CorSym_DocumentType_MC</span><span class="sxs-lookup"><span data-stu-id="d3bcb-142">CorSym_DocumentType_MC</span></span>|<span data-ttu-id="d3bcb-143">Indica un documento non di testo.</span><span class="sxs-lookup"><span data-stu-id="d3bcb-143">Indicates a non-text document.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d3bcb-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d3bcb-144">See Also</span></span>  
 [<span data-ttu-id="d3bcb-145">Riferimenti alle API non gestite</span><span class="sxs-lookup"><span data-stu-id="d3bcb-145">Unmanaged API Reference</span></span>](../../../docs/framework/unmanaged-api/index.md)
