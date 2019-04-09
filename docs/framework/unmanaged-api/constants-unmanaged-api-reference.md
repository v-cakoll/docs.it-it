---
title: Costanti (riferimenti alle API non gestite)
ms.date: 03/30/2017
helpviewer_keywords:
- constants for unmanaged API [.NET Framework]
- native API reference [.NET Framework], constants
- unmanaged API reference [.NET Framework], constants
ms.assetid: 77526f65-b71c-4483-9d19-3a3751fd8a45
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8c76db644ffee478003d834460c155c4ec6d0070
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59133952"
---
# <a name="constants-unmanaged-api-reference"></a><span data-ttu-id="31d60-102">Costanti (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="31d60-102">Constants (Unmanaged API Reference)</span></span>
<span data-ttu-id="31d60-103">Questo argomento descrive il tipo di linguaggio, fornitore di linguaggio e costanti del tipo di documento che sono definite in CorSym. idl.</span><span class="sxs-lookup"><span data-stu-id="31d60-103">This topic describes the language type, language vendor, and document type constants that are defined in CorSym.idl.</span></span>  
  
## <a name="language-type-constants"></a><span data-ttu-id="31d60-104">Costanti del tipo di linguaggio</span><span class="sxs-lookup"><span data-stu-id="31d60-104">Language Type Constants</span></span>  
 <span data-ttu-id="31d60-105">Nella tabella seguente mostra lingua le costanti dei tipi che rappresentano i GUID che identificano i linguaggi di programmazione.</span><span class="sxs-lookup"><span data-stu-id="31d60-105">The following table shows language type constants, which represent GUIDs that identify programming languages.</span></span>  
  
|<span data-ttu-id="31d60-106">Simbolo</span><span class="sxs-lookup"><span data-stu-id="31d60-106">Symbol</span></span>|<span data-ttu-id="31d60-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="31d60-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="31d60-108">CorSym_LanguageType_C</span><span class="sxs-lookup"><span data-stu-id="31d60-108">CorSym_LanguageType_C</span></span>|<span data-ttu-id="31d60-109">Indica il linguaggio C.</span><span class="sxs-lookup"><span data-stu-id="31d60-109">Indicates the C language.</span></span>|  
|<span data-ttu-id="31d60-110">CorSym_LanguageType_CPlusPlus</span><span class="sxs-lookup"><span data-stu-id="31d60-110">CorSym_LanguageType_CPlusPlus</span></span>|<span data-ttu-id="31d60-111">Indica il linguaggio C++.</span><span class="sxs-lookup"><span data-stu-id="31d60-111">Indicates the C++ language.</span></span>|  
|<span data-ttu-id="31d60-112">CorSym_LanguageType_CSharp</span><span class="sxs-lookup"><span data-stu-id="31d60-112">CorSym_LanguageType_CSharp</span></span>|<span data-ttu-id="31d60-113">Indica il C# linguaggio.</span><span class="sxs-lookup"><span data-stu-id="31d60-113">Indicates the C# language.</span></span>|  
|<span data-ttu-id="31d60-114">CorSym_LanguageType_Basic</span><span class="sxs-lookup"><span data-stu-id="31d60-114">CorSym_LanguageType_Basic</span></span>|<span data-ttu-id="31d60-115">Indica il linguaggio di base.</span><span class="sxs-lookup"><span data-stu-id="31d60-115">Indicates the Basic language.</span></span>|  
|<span data-ttu-id="31d60-116">CorSym_LanguageType_Java</span><span class="sxs-lookup"><span data-stu-id="31d60-116">CorSym_LanguageType_Java</span></span>|<span data-ttu-id="31d60-117">Indica il linguaggio Java.</span><span class="sxs-lookup"><span data-stu-id="31d60-117">Indicates the Java language.</span></span>|  
|<span data-ttu-id="31d60-118">CorSym_LanguageType_Cobol</span><span class="sxs-lookup"><span data-stu-id="31d60-118">CorSym_LanguageType_Cobol</span></span>|<span data-ttu-id="31d60-119">Indica il linguaggio COBOL.</span><span class="sxs-lookup"><span data-stu-id="31d60-119">Indicates the COBOL language.</span></span>|  
|<span data-ttu-id="31d60-120">CorSym_LanguageType_Pascal</span><span class="sxs-lookup"><span data-stu-id="31d60-120">CorSym_LanguageType_Pascal</span></span>|<span data-ttu-id="31d60-121">Indica il linguaggio Pascal.</span><span class="sxs-lookup"><span data-stu-id="31d60-121">Indicates the Pascal language.</span></span>|  
|<span data-ttu-id="31d60-122">CorSym_LanguageType_ILAssembly</span><span class="sxs-lookup"><span data-stu-id="31d60-122">CorSym_LanguageType_ILAssembly</span></span>|<span data-ttu-id="31d60-123">Indica il codice di assembly di Microsoft intermediate language (MSIL).</span><span class="sxs-lookup"><span data-stu-id="31d60-123">Indicates the Microsoft intermediate language (MSIL) assembly code.</span></span>|  
|<span data-ttu-id="31d60-124">CorSym_LanguageType_JScript</span><span class="sxs-lookup"><span data-stu-id="31d60-124">CorSym_LanguageType_JScript</span></span>|<span data-ttu-id="31d60-125">Indica il linguaggio JScript.</span><span class="sxs-lookup"><span data-stu-id="31d60-125">Indicates the JScript language.</span></span>|  
|<span data-ttu-id="31d60-126">CorSym_LanguageType_SMC</span><span class="sxs-lookup"><span data-stu-id="31d60-126">CorSym_LanguageType_SMC</span></span>|<span data-ttu-id="31d60-127">Indica il linguaggio SMC.</span><span class="sxs-lookup"><span data-stu-id="31d60-127">Indicates the SMC language.</span></span>|  
|<span data-ttu-id="31d60-128">CorSym_LanguageType_MCPlusPlus</span><span class="sxs-lookup"><span data-stu-id="31d60-128">CorSym_LanguageType_MCPlusPlus</span></span>|<span data-ttu-id="31d60-129">Indica il linguaggio C++ abilitato per .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="31d60-129">Indicates the C++ language enabled for the .NET Framework.</span></span>|  
  
## <a name="language-vendor-constants"></a><span data-ttu-id="31d60-130">Costanti di fornitore di linguaggio</span><span class="sxs-lookup"><span data-stu-id="31d60-130">Language Vendor Constants</span></span>  
 <span data-ttu-id="31d60-131">La tabella seguente mostra linguaggio costanti fornitore, che rappresentano i GUID che identificano i fornitori dei linguaggi di programmazione.</span><span class="sxs-lookup"><span data-stu-id="31d60-131">The following table shows language vendor constants, which represent GUIDs that identify programming language vendors.</span></span>  
  
|<span data-ttu-id="31d60-132">Simbolo</span><span class="sxs-lookup"><span data-stu-id="31d60-132">Symbol</span></span>|<span data-ttu-id="31d60-133">Descrizione</span><span class="sxs-lookup"><span data-stu-id="31d60-133">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="31d60-134">CorSym_LanguageVendor_Microsoft</span><span class="sxs-lookup"><span data-stu-id="31d60-134">CorSym_LanguageVendor_Microsoft</span></span>|<span data-ttu-id="31d60-135">Indica a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="31d60-135">Indicates Microsoft.</span></span>|  
  
## <a name="document-type-constants"></a><span data-ttu-id="31d60-136">Costanti del tipo di documento</span><span class="sxs-lookup"><span data-stu-id="31d60-136">Document Type Constants</span></span>  
 <span data-ttu-id="31d60-137">Nella tabella seguente viene illustrato come documento le costanti dei tipi che rappresentano i GUID che identificano i tipi di documento.</span><span class="sxs-lookup"><span data-stu-id="31d60-137">The following table shows document type constants, which represent GUIDs that identify document types.</span></span>  
  
|<span data-ttu-id="31d60-138">Simbolo</span><span class="sxs-lookup"><span data-stu-id="31d60-138">Symbol</span></span>|<span data-ttu-id="31d60-139">Descrizione</span><span class="sxs-lookup"><span data-stu-id="31d60-139">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="31d60-140">CorSym_DocumentType_Text</span><span class="sxs-lookup"><span data-stu-id="31d60-140">CorSym_DocumentType_Text</span></span>|<span data-ttu-id="31d60-141">Indica un documento di testo.</span><span class="sxs-lookup"><span data-stu-id="31d60-141">Indicates a text document.</span></span>|  
|<span data-ttu-id="31d60-142">CorSym_DocumentType_MC</span><span class="sxs-lookup"><span data-stu-id="31d60-142">CorSym_DocumentType_MC</span></span>|<span data-ttu-id="31d60-143">Indica un documento non di testo.</span><span class="sxs-lookup"><span data-stu-id="31d60-143">Indicates a non-text document.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="31d60-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="31d60-144">See also</span></span>

- [<span data-ttu-id="31d60-145">Riferimenti alle API non gestite</span><span class="sxs-lookup"><span data-stu-id="31d60-145">Unmanaged API Reference</span></span>](../../../docs/framework/unmanaged-api/index.md)
