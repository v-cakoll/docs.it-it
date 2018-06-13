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
ms.openlocfilehash: 65925b7dafb9e89433253d68327c488365674963
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33406278"
---
# <a name="constants-unmanaged-api-reference"></a><span data-ttu-id="c963f-102">Costanti (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="c963f-102">Constants (Unmanaged API Reference)</span></span>
<span data-ttu-id="c963f-103">Questo argomento descrive il tipo di linguaggio, fornitore di linguaggio e costanti di tipo di documento che sono definite in CorSym.idl.</span><span class="sxs-lookup"><span data-stu-id="c963f-103">This topic describes the language type, language vendor, and document type constants that are defined in CorSym.idl.</span></span>  
  
## <a name="language-type-constants"></a><span data-ttu-id="c963f-104">Costanti del tipo di linguaggio</span><span class="sxs-lookup"><span data-stu-id="c963f-104">Language Type Constants</span></span>  
 <span data-ttu-id="c963f-105">Nella tabella seguente viene illustrato come linguaggio di costanti di tipo, che rappresentano i GUID che identificano i linguaggi di programmazione.</span><span class="sxs-lookup"><span data-stu-id="c963f-105">The following table shows language type constants, which represent GUIDs that identify programming languages.</span></span>  
  
|<span data-ttu-id="c963f-106">Simbolo</span><span class="sxs-lookup"><span data-stu-id="c963f-106">Symbol</span></span>|<span data-ttu-id="c963f-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c963f-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="c963f-108">CorSym_LanguageType_C</span><span class="sxs-lookup"><span data-stu-id="c963f-108">CorSym_LanguageType_C</span></span>|<span data-ttu-id="c963f-109">Indica il linguaggio C.</span><span class="sxs-lookup"><span data-stu-id="c963f-109">Indicates the C language.</span></span>|  
|<span data-ttu-id="c963f-110">CorSym_LanguageType_CPlusPlus</span><span class="sxs-lookup"><span data-stu-id="c963f-110">CorSym_LanguageType_CPlusPlus</span></span>|<span data-ttu-id="c963f-111">Indica il linguaggio C++.</span><span class="sxs-lookup"><span data-stu-id="c963f-111">Indicates the C++ language.</span></span>|  
|<span data-ttu-id="c963f-112">CorSym_LanguageType_CSharp</span><span class="sxs-lookup"><span data-stu-id="c963f-112">CorSym_LanguageType_CSharp</span></span>|<span data-ttu-id="c963f-113">Indica il linguaggio c#.</span><span class="sxs-lookup"><span data-stu-id="c963f-113">Indicates the C# language.</span></span>|  
|<span data-ttu-id="c963f-114">CorSym_LanguageType_Basic</span><span class="sxs-lookup"><span data-stu-id="c963f-114">CorSym_LanguageType_Basic</span></span>|<span data-ttu-id="c963f-115">Indica la lingua di base.</span><span class="sxs-lookup"><span data-stu-id="c963f-115">Indicates the Basic language.</span></span>|  
|<span data-ttu-id="c963f-116">CorSym_LanguageType_Java</span><span class="sxs-lookup"><span data-stu-id="c963f-116">CorSym_LanguageType_Java</span></span>|<span data-ttu-id="c963f-117">Indica il linguaggio Java.</span><span class="sxs-lookup"><span data-stu-id="c963f-117">Indicates the Java language.</span></span>|  
|<span data-ttu-id="c963f-118">CorSym_LanguageType_Cobol</span><span class="sxs-lookup"><span data-stu-id="c963f-118">CorSym_LanguageType_Cobol</span></span>|<span data-ttu-id="c963f-119">Indica la lingua COBOL.</span><span class="sxs-lookup"><span data-stu-id="c963f-119">Indicates the COBOL language.</span></span>|  
|<span data-ttu-id="c963f-120">CorSym_LanguageType_Pascal</span><span class="sxs-lookup"><span data-stu-id="c963f-120">CorSym_LanguageType_Pascal</span></span>|<span data-ttu-id="c963f-121">Indica la lingua Pascal.</span><span class="sxs-lookup"><span data-stu-id="c963f-121">Indicates the Pascal language.</span></span>|  
|<span data-ttu-id="c963f-122">CorSym_LanguageType_ILAssembly</span><span class="sxs-lookup"><span data-stu-id="c963f-122">CorSym_LanguageType_ILAssembly</span></span>|<span data-ttu-id="c963f-123">Indica il codice di assembly di Microsoft intermediate language (MSIL).</span><span class="sxs-lookup"><span data-stu-id="c963f-123">Indicates the Microsoft intermediate language (MSIL) assembly code.</span></span>|  
|<span data-ttu-id="c963f-124">CorSym_LanguageType_JScript</span><span class="sxs-lookup"><span data-stu-id="c963f-124">CorSym_LanguageType_JScript</span></span>|<span data-ttu-id="c963f-125">Indica il linguaggio JScript.</span><span class="sxs-lookup"><span data-stu-id="c963f-125">Indicates the JScript language.</span></span>|  
|<span data-ttu-id="c963f-126">CorSym_LanguageType_SMC</span><span class="sxs-lookup"><span data-stu-id="c963f-126">CorSym_LanguageType_SMC</span></span>|<span data-ttu-id="c963f-127">Indica il linguaggio SMC.</span><span class="sxs-lookup"><span data-stu-id="c963f-127">Indicates the SMC language.</span></span>|  
|<span data-ttu-id="c963f-128">CorSym_LanguageType_MCPlusPlus</span><span class="sxs-lookup"><span data-stu-id="c963f-128">CorSym_LanguageType_MCPlusPlus</span></span>|<span data-ttu-id="c963f-129">Indica il linguaggio C++ abilitato per .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c963f-129">Indicates the C++ language enabled for the .NET Framework.</span></span>|  
  
## <a name="language-vendor-constants"></a><span data-ttu-id="c963f-130">Costanti di fornitore di linguaggio</span><span class="sxs-lookup"><span data-stu-id="c963f-130">Language Vendor Constants</span></span>  
 <span data-ttu-id="c963f-131">Nella tabella seguente viene illustrato come linguaggio costanti fornitore, che rappresentano i GUID che identificano i fornitori dei linguaggi di programmazione.</span><span class="sxs-lookup"><span data-stu-id="c963f-131">The following table shows language vendor constants, which represent GUIDs that identify programming language vendors.</span></span>  
  
|<span data-ttu-id="c963f-132">Simbolo</span><span class="sxs-lookup"><span data-stu-id="c963f-132">Symbol</span></span>|<span data-ttu-id="c963f-133">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c963f-133">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="c963f-134">CorSym_LanguageVendor_Microsoft</span><span class="sxs-lookup"><span data-stu-id="c963f-134">CorSym_LanguageVendor_Microsoft</span></span>|<span data-ttu-id="c963f-135">Indica a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c963f-135">Indicates Microsoft.</span></span>|  
  
## <a name="document-type-constants"></a><span data-ttu-id="c963f-136">Costanti del tipo di documento</span><span class="sxs-lookup"><span data-stu-id="c963f-136">Document Type Constants</span></span>  
 <span data-ttu-id="c963f-137">Nella tabella seguente viene illustrato come documento costanti di tipo, che rappresentano i GUID che identificano i tipi di documento.</span><span class="sxs-lookup"><span data-stu-id="c963f-137">The following table shows document type constants, which represent GUIDs that identify document types.</span></span>  
  
|<span data-ttu-id="c963f-138">Simbolo</span><span class="sxs-lookup"><span data-stu-id="c963f-138">Symbol</span></span>|<span data-ttu-id="c963f-139">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c963f-139">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="c963f-140">CorSym_DocumentType_Text</span><span class="sxs-lookup"><span data-stu-id="c963f-140">CorSym_DocumentType_Text</span></span>|<span data-ttu-id="c963f-141">Indica un documento di testo.</span><span class="sxs-lookup"><span data-stu-id="c963f-141">Indicates a text document.</span></span>|  
|<span data-ttu-id="c963f-142">CorSym_DocumentType_MC</span><span class="sxs-lookup"><span data-stu-id="c963f-142">CorSym_DocumentType_MC</span></span>|<span data-ttu-id="c963f-143">Indica un documento non di testo.</span><span class="sxs-lookup"><span data-stu-id="c963f-143">Indicates a non-text document.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c963f-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c963f-144">See Also</span></span>  
 [<span data-ttu-id="c963f-145">Riferimenti alle API non gestite</span><span class="sxs-lookup"><span data-stu-id="c963f-145">Unmanaged API Reference</span></span>](../../../docs/framework/unmanaged-api/index.md)
