---
title: Enumerazione CorDebugInterfaceVersion
ms.date: 03/30/2017
api_name:
- CorDebugInterfaceVersion
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugInterfaceVersion
helpviewer_keywords:
- CorDebugInterfaceVersion enumeration [.NET Framework debugging]
ms.assetid: 7d1e6cd9-2a15-41c6-9b68-008705a4ed90
topic_type:
- apiref
ms.openlocfilehash: 5ebbbf01bc27974850c7e0bb3591b8f050fd0579
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179264"
---
# <a name="cordebuginterfaceversion-enumeration"></a><span data-ttu-id="276de-102">Enumerazione CorDebugInterfaceVersion</span><span class="sxs-lookup"><span data-stu-id="276de-102">CorDebugInterfaceVersion Enumeration</span></span>
<span data-ttu-id="276de-103">Specifica un'interfaccia, una versione di .NET Framework o una versione di .NET Framework in cui è stata introdotta un'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="276de-103">Specifies an interface, a version of the .NET Framework, or a version of the .NET Framework in which an interface was introduced.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="276de-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="276de-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugInterfaceVersion {  
  
    CorDebugInvalidVersion            = 0,  
    CorDebugVersion_1_0               = CorDebugInvalidVersion + 1,  
  
    ver_ICorDebugManagedCallback      = CorDebugVersion_1_0,  
    ver_ICorDebugUnmanagedCallback    = CorDebugVersion_1_0,  
    ver_ICorDebug                     = CorDebugVersion_1_0,  
    ver_ICorDebugController           = CorDebugVersion_1_0,  
    ver_ICorDebugAppDomain            = CorDebugVersion_1_0,  
    ver_ICorDebugAssembly             = CorDebugVersion_1_0,  
    ver_ICorDebugProcess              = CorDebugVersion_1_0,  
    ver_ICorDebugBreakpoint           = CorDebugVersion_1_0,  
    ver_ICorDebugFunctionBreakpoint   = CorDebugVersion_1_0,  
    ver_ICorDebugModuleBreakpoint     = CorDebugVersion_1_0,  
    ver_ICorDebugValueBreakpoint      = CorDebugVersion_1_0,  
    ver_ICorDebugStepper              = CorDebugVersion_1_0,  
    ver_ICorDebugRegisterSet          = CorDebugVersion_1_0,  
    ver_ICorDebugThread               = CorDebugVersion_1_0,  
    ver_ICorDebugChain                = CorDebugVersion_1_0,  
    ver_ICorDebugFrame                = CorDebugVersion_1_0,  
    ver_ICorDebugILFrame              = CorDebugVersion_1_0,  
    ver_ICorDebugNativeFrame          = CorDebugVersion_1_0,  
    ver_ICorDebugModule               = CorDebugVersion_1_0,  
    ver_ICorDebugFunction             = CorDebugVersion_1_0,  
    ver_ICorDebugCode                 = CorDebugVersion_1_0,  
    ver_ICorDebugClass                = CorDebugVersion_1_0,  
    ver_ICorDebugEval                 = CorDebugVersion_1_0,  
    ver_ICorDebugValue                = CorDebugVersion_1_0,  
    ver_ICorDebugGenericValue         = CorDebugVersion_1_0,  
    ver_ICorDebugReferenceValue       = CorDebugVersion_1_0,  
    ver_ICorDebugHeapValue            = CorDebugVersion_1_0,  
    ver_ICorDebugObjectValue          = CorDebugVersion_1_0,  
    ver_ICorDebugBoxValue             = CorDebugVersion_1_0,  
    ver_ICorDebugStringValue          = CorDebugVersion_1_0,  
    ver_ICorDebugArrayValue           = CorDebugVersion_1_0,  
    ver_ICorDebugContext              = CorDebugVersion_1_0,  
    ver_ICorDebugEnum                 = CorDebugVersion_1_0,  
    ver_ICorDebugObjectEnum           = CorDebugVersion_1_0,  
    ver_ICorDebugBreakpointEnum       = CorDebugVersion_1_0,  
    ver_ICorDebugStepperEnum          = CorDebugVersion_1_0,  
    ver_ICorDebugProcessEnum          = CorDebugVersion_1_0,  
    ver_ICorDebugThreadEnum           = CorDebugVersion_1_0,  
    ver_ICorDebugFrameEnum            = CorDebugVersion_1_0,  
    ver_ICorDebugChainEnum            = CorDebugVersion_1_0,  
    ver_ICorDebugModuleEnum           = CorDebugVersion_1_0,  
    ver_ICorDebugValueEnum            = CorDebugVersion_1_0,  
    ver_ICorDebugCodeEnum             = CorDebugVersion_1_0,  
    ver_ICorDebugTypeEnum             = CorDebugVersion_1_0,  
    ver_ICorDebugErrorInfoEnum        = CorDebugVersion_1_0,  
    ver_ICorDebugAppDomainEnum        = CorDebugVersion_1_0,  
    ver_ICorDebugAssemblyEnum         = CorDebugVersion_1_0,  
    ver_ICorDebugEditAndContinueErrorInfo
                                      = CorDebugVersion_1_0,  
    ver_ICorDebugEditAndContinueSnapshot
                                      = CorDebugVersion_1_0,  
  
    CorDebugVersion_1_1               = CorDebugVersion_1_0 + 1,  
    // No interface definitions in version 1.1.  
  
    CorDebugVersion_2_0 = CorDebugVersion_1_1 + 1,  
  
    ver_ICorDebugManagedCallback2    = CorDebugVersion_2_0,  
    ver_ICorDebugAppDomain2          = CorDebugVersion_2_0,  
    ver_ICorDebugProcess2            = CorDebugVersion_2_0,  
    ver_ICorDebugStepper2            = CorDebugVersion_2_0,  
    ver_ICorDebugRegisterSet2        = CorDebugVersion_2_0,  
    ver_ICorDebugThread2             = CorDebugVersion_2_0,  
    ver_ICorDebugILFrame2            = CorDebugVersion_2_0,  
    ver_ICorDebugModule2             = CorDebugVersion_2_0,  
    ver_ICorDebugFunction2           = CorDebugVersion_2_0,  
    ver_ICorDebugCode2               = CorDebugVersion_2_0,  
    ver_ICorDebugClass2              = CorDebugVersion_2_0,  
    ver_ICorDebugValue2              = CorDebugVersion_2_0,  
    ver_ICorDebugEval2               = CorDebugVersion_2_0,  
    ver_ICorDebugObjectValue2        = CorDebugVersion_2_0,  
  
    // CLR v4 - next major CLR version after CLR v2  
    // Includes Silverlight 4  
    CorDebugVersion_4_0 = CorDebugVersion_2_0 + 1,  
  
    ver_ICorDebugThread3             = CorDebugVersion_4_0,  
    ver_ICorDebugThread4             = CorDebugVersion_4_0,  
    ver_ICorDebugStackWalk           = CorDebugVersion_4_0,  
    ver_ICorDebugNativeFrame2        = CorDebugVersion_4_0,  
    ver_ICorDebugInternalFrame2      = CorDebugVersion_4_0,  
    ver_ICorDebugRuntimeUnwindableFrame = CorDebugVersion_4_0,  
    ver_ICorDebugHeapValue3          = CorDebugVersion_4_0,  
    ver_ICorDebugBlockingObjectEnum  = CorDebugVersion_4_0,  
    ver_ICorDebugValue3 = CorDebugVersion_4_0,  
  
    CorDebugVersion_4_5 = CorDebugVersion_4_0 + 1,  
  
    ver_ICorDebugComObjectValue = CorDebugVersion_4_5,  
    ver_ICorDebugAppDomain3 = CorDebugVersion_4_5,  
    ver_ICorDebugCode3 = CorDebugVersion_4_5,  
    ver_ICorDebugILFrame3 = CorDebugVersion_4_5,  
  
    CorDebugLatestVersion = CorDebugVersion_4_5  
  
} CorDebugInterfaceVersion;  
```  
  
## <a name="members"></a><span data-ttu-id="276de-105">Members</span><span class="sxs-lookup"><span data-stu-id="276de-105">Members</span></span>  
 <span data-ttu-id="276de-106">La tabella seguente contiene collegamenti da ogni valore di enumerazione all'interfaccia corrispondente.</span><span class="sxs-lookup"><span data-stu-id="276de-106">The following table provides links from each enumeration value to the corresponding interface.</span></span> <span data-ttu-id="276de-107">Inoltre, la tabella indica la prima versione di .NET Framework in cui l'interfaccia è supportata.</span><span class="sxs-lookup"><span data-stu-id="276de-107">In addition, the table indicates the first version of the .NET Framework that the interface was supported in.</span></span>  
  
|<span data-ttu-id="276de-108">Membro</span><span class="sxs-lookup"><span data-stu-id="276de-108">Member</span></span>|<span data-ttu-id="276de-109">Specifica</span><span class="sxs-lookup"><span data-stu-id="276de-109">Specifies</span></span>|<span data-ttu-id="276de-110">Versione di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="276de-110">.NET Framework version</span></span>|  
|------------|---------------|----------------------------|  
|`CorDebugInvalidVersion`|<span data-ttu-id="276de-111">La versione di .NET Framework non è valida.</span><span class="sxs-lookup"><span data-stu-id="276de-111">The version of the .NET Framework is invalid.</span></span>|-|  
|`CorDebugVersion_1_0`|<span data-ttu-id="276de-112">La versione di .NET Framework, inclusi tutti i relativi Service Pack, è 1.0.</span><span class="sxs-lookup"><span data-stu-id="276de-112">The version of the .NET Framework, including all its service packs, is 1.0.</span></span>|<span data-ttu-id="276de-113">1.0</span><span class="sxs-lookup"><span data-stu-id="276de-113">1.0</span></span>|  
|`CorDebugVersion_1_1`|<span data-ttu-id="276de-114">La versione di .NET Framework, inclusi tutti i relativi Service Pack, è 1.1.</span><span class="sxs-lookup"><span data-stu-id="276de-114">The version of the .NET Framework, including all service packs, is 1.1.</span></span>|<span data-ttu-id="276de-115">1.1</span><span class="sxs-lookup"><span data-stu-id="276de-115">1.1</span></span>|  
|`CorDebugVersion_2_0`|<span data-ttu-id="276de-116">La versione di .NET Framework, inclusi tutti i relativi Service Pack, è 2.0.</span><span class="sxs-lookup"><span data-stu-id="276de-116">The version of the .NET Framework, including all service packs, is 2.0.</span></span>|<span data-ttu-id="276de-117">2.0</span><span class="sxs-lookup"><span data-stu-id="276de-117">2.0</span></span>|  
|`CorDebugVersion_4_0`|<span data-ttu-id="276de-118">La versione di .NET Framework, inclusi tutti i relativi Service Pack, è 4.</span><span class="sxs-lookup"><span data-stu-id="276de-118">The version of the .NET Framework, including all service packs, is 4.</span></span>|<span data-ttu-id="276de-119">4</span><span class="sxs-lookup"><span data-stu-id="276de-119">4</span></span>|  
|`CorDebugVersion_4_5`|<span data-ttu-id="276de-120">La versione di .NET Framework, inclusi tutti i relativi Service Pack, è 4.5.</span><span class="sxs-lookup"><span data-stu-id="276de-120">The version of the .NET Framework, including all service packs, is 4.5.</span></span>|<span data-ttu-id="276de-121">4.5</span><span class="sxs-lookup"><span data-stu-id="276de-121">4.5</span></span>|  
|`ver_ICorDebugManagedCallback`|[<span data-ttu-id="276de-122">ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="276de-122">ICorDebugManagedCallback</span></span>](icordebugmanagedcallback-interface.md)|<span data-ttu-id="276de-123">1.0</span><span class="sxs-lookup"><span data-stu-id="276de-123">1.0</span></span>|  
|`ver_ICorDebugUnmanagedCallback`|[<span data-ttu-id="276de-124">ICorDebugUnmanagedCallback</span><span class="sxs-lookup"><span data-stu-id="276de-124">ICorDebugUnmanagedCallback</span></span>](icordebugunmanagedcallback-interface.md)|<span data-ttu-id="276de-125">1.0</span><span class="sxs-lookup"><span data-stu-id="276de-125">1.0</span></span>|  
|`ver_ICorDebug`|[<span data-ttu-id="276de-126">ICorDebug</span><span class="sxs-lookup"><span data-stu-id="276de-126">ICorDebug</span></span>](icordebug-interface.md)|<span data-ttu-id="276de-127">1.0</span><span class="sxs-lookup"><span data-stu-id="276de-127">1.0</span></span>|  
|`ver_ICorDebugController`|[<span data-ttu-id="276de-128">ICorDebugController</span><span class="sxs-lookup"><span data-stu-id="276de-128">ICorDebugController</span></span>](icordebugcontroller-interface.md)|<span data-ttu-id="276de-129">1.0</span><span class="sxs-lookup"><span data-stu-id="276de-129">1.0</span></span>|  
|`ver_ICorDebugAppDomain`|[<span data-ttu-id="276de-130">ICorDebugAppDomain</span><span class="sxs-lookup"><span data-stu-id="276de-130">ICorDebugAppDomain</span></span>](icordebugappdomain-interface.md)|<span data-ttu-id="276de-131">1.0</span><span class="sxs-lookup"><span data-stu-id="276de-131">1.0</span></span>|  
|`ver_ICorDebugAssembly`|[<span data-ttu-id="276de-132">ICorDebugAssembly</span><span class="sxs-lookup"><span data-stu-id="276de-132">ICorDebugAssembly</span></span>](icordebugassembly-interface.md)|<span data-ttu-id="276de-133">1.0</span><span class="sxs-lookup"><span data-stu-id="276de-133">1.0</span></span>|  
|`ver_ICorDebugProcess`|[<span data-ttu-id="276de-134">ICorDebugProcess</span><span class="sxs-lookup"><span data-stu-id="276de-134">ICorDebugProcess</span></span>](icordebugprocess-interface.md)|<span data-ttu-id="276de-135">1.0</span><span class="sxs-lookup"><span data-stu-id="276de-135">1.0</span></span>|  
|`ver_ICorDebugBreakpoint`|[<span data-ttu-id="276de-136">ICorDebugBreakpoint</span><span class="sxs-lookup"><span data-stu-id="276de-136">ICorDebugBreakpoint</span></span>](icordebugbreakpoint-interface.md)|<span data-ttu-id="276de-137">1.0</span><span class="sxs-lookup"><span data-stu-id="276de-137">1.0</span></span>|  
|`ver_ICorDebugFunctionBreakpoint`|[<span data-ttu-id="276de-138">ICorDebugFunctionBreakpoint</span><span class="sxs-lookup"><span data-stu-id="276de-138">ICorDebugFunctionBreakpoint</span></span>](icordebugfunctionbreakpoint-interface.md)|<span data-ttu-id="276de-139">1.0</span><span class="sxs-lookup"><span data-stu-id="276de-139">1.0</span></span>|  
|`ver_ICorDebugModuleBreakpoint`|[<span data-ttu-id="276de-140">ICorDebugModuleBreakpoint</span><span class="sxs-lookup"><span data-stu-id="276de-140">ICorDebugModuleBreakpoint</span></span>](icordebugmodulebreakpoint-interface.md)|<span data-ttu-id="276de-141">1.0</span><span class="sxs-lookup"><span data-stu-id="276de-141">1.0</span></span>|  
|`ver_ICorDebugValueBreakpoint`|[<span data-ttu-id="276de-142">ICorDebugValueBreakpoint</span><span class="sxs-lookup"><span data-stu-id="276de-142">ICorDebugValueBreakpoint</span></span>](icordebugvaluebreakpoint-interface.md)|<span data-ttu-id="276de-143">1.0</span><span class="sxs-lookup"><span data-stu-id="276de-143">1.0</span></span>|  
|`ver_ICorDebugStepper`|[<span data-ttu-id="276de-144">ICorDebugStepper</span><span class="sxs-lookup"><span data-stu-id="276de-144">ICorDebugStepper</span></span>](icordebugstepper-interface.md)|<span data-ttu-id="276de-145">1.0</span><span class="sxs-lookup"><span data-stu-id="276de-145">1.0</span></span>|  
|`ver_ICorDebugRegisterSet`|[<span data-ttu-id="276de-146">ICorDebugRegisterSet</span><span class="sxs-lookup"><span data-stu-id="276de-146">ICorDebugRegisterSet</span></span>](icordebugregisterset-interface.md)|<span data-ttu-id="276de-147">1.0</span><span class="sxs-lookup"><span data-stu-id="276de-147">1.0</span></span>|  
|`ver_ICorDebugThread`|[<span data-ttu-id="276de-148">ICorDebugThread</span><span class="sxs-lookup"><span data-stu-id="276de-148">ICorDebugThread</span></span>](icordebugthread-interface.md)|<span data-ttu-id="276de-149">1.0</span><span class="sxs-lookup"><span data-stu-id="276de-149">1.0</span></span>|  
|`ver_ICorDebugChain`|[<span data-ttu-id="276de-150">ICorDebugChain</span><span class="sxs-lookup"><span data-stu-id="276de-150">ICorDebugChain</span></span>](icordebugchain-interface.md)|<span data-ttu-id="276de-151">1.0</span><span class="sxs-lookup"><span data-stu-id="276de-151">1.0</span></span>|  
|`ver_ICorDebugFrame`|[<span data-ttu-id="276de-152">ICorDebugFrame</span><span class="sxs-lookup"><span data-stu-id="276de-152">ICorDebugFrame</span></span>](icordebugframe-interface.md)|<span data-ttu-id="276de-153">1.0</span><span class="sxs-lookup"><span data-stu-id="276de-153">1.0</span></span>|  
|`ver_ICorDebugILFrame`|[<span data-ttu-id="276de-154">ICorDebugILFrame</span><span class="sxs-lookup"><span data-stu-id="276de-154">ICorDebugILFrame</span></span>](icordebugilframe-interface.md)|<span data-ttu-id="276de-155">1.0</span><span class="sxs-lookup"><span data-stu-id="276de-155">1.0</span></span>|  
|`ver_ICorDebugNativeFrame`|[<span data-ttu-id="276de-156">ICorDebugNativeFrame</span><span class="sxs-lookup"><span data-stu-id="276de-156">ICorDebugNativeFrame</span></span>](icordebugnativeframe-interface.md)|<span data-ttu-id="276de-157">1.0</span><span class="sxs-lookup"><span data-stu-id="276de-157">1.0</span></span>|  
|`ver_ICorDebugModule`|[<span data-ttu-id="276de-158">ICorDebugModule</span><span class="sxs-lookup"><span data-stu-id="276de-158">ICorDebugModule</span></span>](icordebugmodule-interface.md)|<span data-ttu-id="276de-159">1.0</span><span class="sxs-lookup"><span data-stu-id="276de-159">1.0</span></span>|  
|`ver_ICorDebugFunction`|[<span data-ttu-id="276de-160">ICorDebugFunction</span><span class="sxs-lookup"><span data-stu-id="276de-160">ICorDebugFunction</span></span>](icordebugfunction-interface1.md)|<span data-ttu-id="276de-161">1.0</span><span class="sxs-lookup"><span data-stu-id="276de-161">1.0</span></span>|  
|`ver_ICorDebugCode`|[<span data-ttu-id="276de-162">ICorDebugCode</span><span class="sxs-lookup"><span data-stu-id="276de-162">ICorDebugCode</span></span>](icordebugcode-interface1.md)|<span data-ttu-id="276de-163">1.0</span><span class="sxs-lookup"><span data-stu-id="276de-163">1.0</span></span>|  
|`ver_ICorDebugClass`|[<span data-ttu-id="276de-164">ICorDebugClass</span><span class="sxs-lookup"><span data-stu-id="276de-164">ICorDebugClass</span></span>](icordebugclass-interface.md)|<span data-ttu-id="276de-165">1.0</span><span class="sxs-lookup"><span data-stu-id="276de-165">1.0</span></span>|  
|`ver_ICorDebugEval`|[<span data-ttu-id="276de-166">ICorDebugEval</span><span class="sxs-lookup"><span data-stu-id="276de-166">ICorDebugEval</span></span>](icordebugeval-interface.md)|<span data-ttu-id="276de-167">1.0</span><span class="sxs-lookup"><span data-stu-id="276de-167">1.0</span></span>|  
|`ver_ICorDebugValue`|[<span data-ttu-id="276de-168">ICorDebugValue</span><span class="sxs-lookup"><span data-stu-id="276de-168">ICorDebugValue</span></span>](icordebugvalue-interface.md)|<span data-ttu-id="276de-169">1.0</span><span class="sxs-lookup"><span data-stu-id="276de-169">1.0</span></span>|  
|`ver_ICorDebugGenericValue`|[<span data-ttu-id="276de-170">ICorDebugGenericValueICorDebugGenericValue</span><span class="sxs-lookup"><span data-stu-id="276de-170">ICorDebugGenericValue</span></span>](icordebuggenericvalue-interface.md)|<span data-ttu-id="276de-171">1.0</span><span class="sxs-lookup"><span data-stu-id="276de-171">1.0</span></span>|  
|`ver_ICorDebugReferenceValue`|[<span data-ttu-id="276de-172">ICorDebugReferenceValue</span><span class="sxs-lookup"><span data-stu-id="276de-172">ICorDebugReferenceValue</span></span>](icordebugreferencevalue-interface.md)|<span data-ttu-id="276de-173">1.0</span><span class="sxs-lookup"><span data-stu-id="276de-173">1.0</span></span>|  
|`ver_ICorDebugHeapValue`|[<span data-ttu-id="276de-174">ICorDebugHeapValue</span><span class="sxs-lookup"><span data-stu-id="276de-174">ICorDebugHeapValue</span></span>](icordebugheapvalue-interface.md)|<span data-ttu-id="276de-175">1.0</span><span class="sxs-lookup"><span data-stu-id="276de-175">1.0</span></span>|  
|`ver_ICorDebugObjectValue`|[<span data-ttu-id="276de-176">ICorDebugObjectValue</span><span class="sxs-lookup"><span data-stu-id="276de-176">ICorDebugObjectValue</span></span>](icordebugobjectvalue-interface.md)|<span data-ttu-id="276de-177">1.0</span><span class="sxs-lookup"><span data-stu-id="276de-177">1.0</span></span>|  
|`ver_ICorDebugBoxValue`|[<span data-ttu-id="276de-178">ICorDebugBoxValue</span><span class="sxs-lookup"><span data-stu-id="276de-178">ICorDebugBoxValue</span></span>](icordebugboxvalue-interface.md)|<span data-ttu-id="276de-179">1.0</span><span class="sxs-lookup"><span data-stu-id="276de-179">1.0</span></span>|  
|`ver_ICorDebugStringValue`|[<span data-ttu-id="276de-180">ICorDebugStringValue</span><span class="sxs-lookup"><span data-stu-id="276de-180">ICorDebugStringValue</span></span>](icordebugstringvalue-interface.md)|<span data-ttu-id="276de-181">1.0</span><span class="sxs-lookup"><span data-stu-id="276de-181">1.0</span></span>|  
|`ver_ICorDebugArrayValue`|[<span data-ttu-id="276de-182">ICorDebugArrayValueICorDebugArrayValue</span><span class="sxs-lookup"><span data-stu-id="276de-182">ICorDebugArrayValue</span></span>](icordebugarrayvalue-interface.md)|<span data-ttu-id="276de-183">1.0</span><span class="sxs-lookup"><span data-stu-id="276de-183">1.0</span></span>|  
|`ver_ICorDebugContext`|[<span data-ttu-id="276de-184">ICorDebugContext</span><span class="sxs-lookup"><span data-stu-id="276de-184">ICorDebugContext</span></span>](icordebugcontext-interface.md)|<span data-ttu-id="276de-185">1.0</span><span class="sxs-lookup"><span data-stu-id="276de-185">1.0</span></span>|  
|`ver_ICorDebugEnum`|[<span data-ttu-id="276de-186">ICorDebugEnum</span><span class="sxs-lookup"><span data-stu-id="276de-186">ICorDebugEnum</span></span>](icordebugenum-interface1.md)|<span data-ttu-id="276de-187">1.0</span><span class="sxs-lookup"><span data-stu-id="276de-187">1.0</span></span>|  
|`ver_ICorDebugObjectEnum`|[<span data-ttu-id="276de-188">ICorDebugObjectEnum</span><span class="sxs-lookup"><span data-stu-id="276de-188">ICorDebugObjectEnum</span></span>](icordebugobjectenum-interface.md)|<span data-ttu-id="276de-189">1.0</span><span class="sxs-lookup"><span data-stu-id="276de-189">1.0</span></span>|  
|`ver_ICorDebugBreakpointEnum`|[<span data-ttu-id="276de-190">ICorDebugBreakpointEnum</span><span class="sxs-lookup"><span data-stu-id="276de-190">ICorDebugBreakpointEnum</span></span>](icordebugbreakpointenum-interface.md)|<span data-ttu-id="276de-191">1.0</span><span class="sxs-lookup"><span data-stu-id="276de-191">1.0</span></span>|  
|`ver_ICorDebugStepperEnum`|[<span data-ttu-id="276de-192">ICorDebugStepperEnum</span><span class="sxs-lookup"><span data-stu-id="276de-192">ICorDebugStepperEnum</span></span>](icordebugstepperenum-interface.md)|<span data-ttu-id="276de-193">1.0</span><span class="sxs-lookup"><span data-stu-id="276de-193">1.0</span></span>|  
|`ver_ICorDebugProcessEnum`|[<span data-ttu-id="276de-194">ICorDebugProcessEnum</span><span class="sxs-lookup"><span data-stu-id="276de-194">ICorDebugProcessEnum</span></span>](icordebugprocessenum-interface.md)|<span data-ttu-id="276de-195">1.0</span><span class="sxs-lookup"><span data-stu-id="276de-195">1.0</span></span>|  
|`ver_ICorDebugThreadEnum`|[<span data-ttu-id="276de-196">ICorDebugThreadEnum</span><span class="sxs-lookup"><span data-stu-id="276de-196">ICorDebugThreadEnum</span></span>](icordebugthreadenum-interface1.md)|<span data-ttu-id="276de-197">1.0</span><span class="sxs-lookup"><span data-stu-id="276de-197">1.0</span></span>|  
|`ver_ICorDebugFrameEnum`|[<span data-ttu-id="276de-198">ICorDebugFrameEnumICorDebugFrameEnum</span><span class="sxs-lookup"><span data-stu-id="276de-198">ICorDebugFrameEnum</span></span>](icordebugframeenum-interface.md)|<span data-ttu-id="276de-199">1.0</span><span class="sxs-lookup"><span data-stu-id="276de-199">1.0</span></span>|  
|`ver_ICorDebugChainEnum`|[<span data-ttu-id="276de-200">ICorDebugChainEnum</span><span class="sxs-lookup"><span data-stu-id="276de-200">ICorDebugChainEnum</span></span>](icordebugchainenum-interface.md)|<span data-ttu-id="276de-201">1.0</span><span class="sxs-lookup"><span data-stu-id="276de-201">1.0</span></span>|  
|`ver_ICorDebugModuleEnum`|[<span data-ttu-id="276de-202">ICorDebugModuleEnum</span><span class="sxs-lookup"><span data-stu-id="276de-202">ICorDebugModuleEnum</span></span>](icordebugmoduleenum-interface.md)|<span data-ttu-id="276de-203">1.0</span><span class="sxs-lookup"><span data-stu-id="276de-203">1.0</span></span>|  
|`ver_ICorDebugValueEnum`|[<span data-ttu-id="276de-204">ICorDebugValueEnum</span><span class="sxs-lookup"><span data-stu-id="276de-204">ICorDebugValueEnum</span></span>](icordebugvalueenum-interface.md)|<span data-ttu-id="276de-205">1.0</span><span class="sxs-lookup"><span data-stu-id="276de-205">1.0</span></span>|  
|`ver_ICorDebugCodeEnum`|[<span data-ttu-id="276de-206">ICorDebugCodeEnum</span><span class="sxs-lookup"><span data-stu-id="276de-206">ICorDebugCodeEnum</span></span>](icordebugcodeenum-interface.md)|<span data-ttu-id="276de-207">1.0</span><span class="sxs-lookup"><span data-stu-id="276de-207">1.0</span></span>|  
|`ver_ICorDebugTypeEnum`|[<span data-ttu-id="276de-208">ICorDebugTypeEnum</span><span class="sxs-lookup"><span data-stu-id="276de-208">ICorDebugTypeEnum</span></span>](icordebugtypeenum-interface.md)|<span data-ttu-id="276de-209">1.0</span><span class="sxs-lookup"><span data-stu-id="276de-209">1.0</span></span>|  
|`ver_ICorDebugErrorInfoEnum`|[<span data-ttu-id="276de-210">ICorDebugErrorInfoEnum</span><span class="sxs-lookup"><span data-stu-id="276de-210">ICorDebugErrorInfoEnum</span></span>](icordebugerrorinfoenum-interface.md)|<span data-ttu-id="276de-211">1.0</span><span class="sxs-lookup"><span data-stu-id="276de-211">1.0</span></span>|  
|`ver_ICorDebugAppDomainEnum`|[<span data-ttu-id="276de-212">ICorDebugAppDomainEnum</span><span class="sxs-lookup"><span data-stu-id="276de-212">ICorDebugAppDomainEnum</span></span>](icordebugappdomainenum-interface.md)|<span data-ttu-id="276de-213">1.0</span><span class="sxs-lookup"><span data-stu-id="276de-213">1.0</span></span>|  
|`ver_ICorDebugAssemblyEnum`|[<span data-ttu-id="276de-214">ICorDebugAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="276de-214">ICorDebugAssemblyEnum</span></span>](icordebugassemblyenum-interface.md)|<span data-ttu-id="276de-215">1.0</span><span class="sxs-lookup"><span data-stu-id="276de-215">1.0</span></span>|  
|`ver_ICorDebugEditAndContinueErrorInfo`|[<span data-ttu-id="276de-216">ICorDebugEditAndContinueErrorInfo</span><span class="sxs-lookup"><span data-stu-id="276de-216">ICorDebugEditAndContinueErrorInfo</span></span>](icordebugeditandcontinueerrorinfo-interface.md)|<span data-ttu-id="276de-217">1.0</span><span class="sxs-lookup"><span data-stu-id="276de-217">1.0</span></span>|  
|`ver_ICorDebugEditAndContinueSnapshot`|[<span data-ttu-id="276de-218">ICorDebugEditAndContinueSnapshotICorDebugEditAndContinueSnapshot</span><span class="sxs-lookup"><span data-stu-id="276de-218">ICorDebugEditAndContinueSnapshot</span></span>](icordebugeditandcontinuesnapshot-interface.md)|<span data-ttu-id="276de-219">1.0</span><span class="sxs-lookup"><span data-stu-id="276de-219">1.0</span></span>|  
|`ver_ICorDebugManagedCallback2`|[<span data-ttu-id="276de-220">ICorDebugManagedCallback2</span><span class="sxs-lookup"><span data-stu-id="276de-220">ICorDebugManagedCallback2</span></span>](icordebugmanagedcallback2-interface.md)|<span data-ttu-id="276de-221">2.0</span><span class="sxs-lookup"><span data-stu-id="276de-221">2.0</span></span>|  
|`ver_ICorDebugAppDomain2`|[<span data-ttu-id="276de-222">ICorDebugAppDomain2</span><span class="sxs-lookup"><span data-stu-id="276de-222">ICorDebugAppDomain2</span></span>](icordebugappdomain2-interface.md)|<span data-ttu-id="276de-223">2.0</span><span class="sxs-lookup"><span data-stu-id="276de-223">2.0</span></span>|  
|`ver_ICorDebugProcess2`|[<span data-ttu-id="276de-224">ICorDebugProcess2</span><span class="sxs-lookup"><span data-stu-id="276de-224">ICorDebugProcess2</span></span>](icordebugprocess2-interface1.md)|<span data-ttu-id="276de-225">2.0</span><span class="sxs-lookup"><span data-stu-id="276de-225">2.0</span></span>|  
|`ver_ICorDebugStepper2`|[<span data-ttu-id="276de-226">ICorDebugStepper2</span><span class="sxs-lookup"><span data-stu-id="276de-226">ICorDebugStepper2</span></span>](icordebugstepper2-interface1.md)|<span data-ttu-id="276de-227">2.0</span><span class="sxs-lookup"><span data-stu-id="276de-227">2.0</span></span>|  
|`ver_ICorDebugRegisterSet2`|[<span data-ttu-id="276de-228">ICorDebugRegisterSet2</span><span class="sxs-lookup"><span data-stu-id="276de-228">ICorDebugRegisterSet2</span></span>](icordebugregisterset2-interface.md)|<span data-ttu-id="276de-229">2.0</span><span class="sxs-lookup"><span data-stu-id="276de-229">2.0</span></span>|  
|`ver_ICorDebugThread2`|[<span data-ttu-id="276de-230">ICorDebugThread2</span><span class="sxs-lookup"><span data-stu-id="276de-230">ICorDebugThread2</span></span>](icordebugthread2-interface.md)|<span data-ttu-id="276de-231">2.0</span><span class="sxs-lookup"><span data-stu-id="276de-231">2.0</span></span>|  
|`ver_ICorDebugILFrame2`|[<span data-ttu-id="276de-232">ICorDebugILFrame2</span><span class="sxs-lookup"><span data-stu-id="276de-232">ICorDebugILFrame2</span></span>](icordebugilframe2-interface.md)|<span data-ttu-id="276de-233">2.0</span><span class="sxs-lookup"><span data-stu-id="276de-233">2.0</span></span>|  
|`ver_ICorDebugModule2`|[<span data-ttu-id="276de-234">ICorDebugModule2</span><span class="sxs-lookup"><span data-stu-id="276de-234">ICorDebugModule2</span></span>](icordebugmodule2-interface.md)|<span data-ttu-id="276de-235">2.0</span><span class="sxs-lookup"><span data-stu-id="276de-235">2.0</span></span>|  
|`ver_ICorDebugFunction2`|[<span data-ttu-id="276de-236">ICorDebugFunction2</span><span class="sxs-lookup"><span data-stu-id="276de-236">ICorDebugFunction2</span></span>](icordebugfunction2-interface.md)|<span data-ttu-id="276de-237">2.0</span><span class="sxs-lookup"><span data-stu-id="276de-237">2.0</span></span>|  
|`ver_ICorDebugCode2`|[<span data-ttu-id="276de-238">ICorDebugCode2</span><span class="sxs-lookup"><span data-stu-id="276de-238">ICorDebugCode2</span></span>](icordebugcode2-interface.md)|<span data-ttu-id="276de-239">2.0</span><span class="sxs-lookup"><span data-stu-id="276de-239">2.0</span></span>|  
|`ver_ICorDebugClass2`|<span data-ttu-id="276de-240">"ICorDebugClass2"</span><span class="sxs-lookup"><span data-stu-id="276de-240">"ICorDebugClass2"</span></span>|<span data-ttu-id="276de-241">2.0</span><span class="sxs-lookup"><span data-stu-id="276de-241">2.0</span></span>|  
|`ver_ICorDebugValue2`|<span data-ttu-id="276de-242">"ICorDebugValue2"</span><span class="sxs-lookup"><span data-stu-id="276de-242">"ICorDebugValue2"</span></span>|<span data-ttu-id="276de-243">2.0</span><span class="sxs-lookup"><span data-stu-id="276de-243">2.0</span></span>|  
|`ver_ICorDebugEval2`|<span data-ttu-id="276de-244">Il "ICorDebugEval2".</span><span class="sxs-lookup"><span data-stu-id="276de-244">The "ICorDebugEval2".</span></span>|<span data-ttu-id="276de-245">2.0</span><span class="sxs-lookup"><span data-stu-id="276de-245">2.0</span></span>|  
|`ver_ICorDebugObjectValue2`|<span data-ttu-id="276de-246">"ICorDebugObjectValue2"</span><span class="sxs-lookup"><span data-stu-id="276de-246">"ICorDebugObjectValue2"</span></span>|<span data-ttu-id="276de-247">2.0</span><span class="sxs-lookup"><span data-stu-id="276de-247">2.0</span></span>|  
|`ver_ICorDebugThread3`|[<span data-ttu-id="276de-248">ICorDebugThread3</span><span class="sxs-lookup"><span data-stu-id="276de-248">ICorDebugThread3</span></span>](icordebugthread3-interface.md)|<span data-ttu-id="276de-249">4</span><span class="sxs-lookup"><span data-stu-id="276de-249">4</span></span>|  
|`ver_ICorDebugThread4`|[<span data-ttu-id="276de-250">ICorDebugThread4</span><span class="sxs-lookup"><span data-stu-id="276de-250">ICorDebugThread4</span></span>](icordebugthread4-interface.md)|<span data-ttu-id="276de-251">4</span><span class="sxs-lookup"><span data-stu-id="276de-251">4</span></span>|  
|`ver_ICorDebugStackWalk`|[<span data-ttu-id="276de-252">ICorDebugStackWalkICorDebugStackWalk</span><span class="sxs-lookup"><span data-stu-id="276de-252">ICorDebugStackWalk</span></span>](icordebugstackwalk-interface.md)|<span data-ttu-id="276de-253">4</span><span class="sxs-lookup"><span data-stu-id="276de-253">4</span></span>|  
|`ver_ICorDebugNativeFrame2`|[<span data-ttu-id="276de-254">ICorDebugNativeFrame2</span><span class="sxs-lookup"><span data-stu-id="276de-254">ICorDebugNativeFrame2</span></span>](icordebugnativeframe2-interface.md)|<span data-ttu-id="276de-255">4</span><span class="sxs-lookup"><span data-stu-id="276de-255">4</span></span>|  
|`ver_ICorDebugInternalFrame2`|[<span data-ttu-id="276de-256">ICorDebugInternalFrame2</span><span class="sxs-lookup"><span data-stu-id="276de-256">ICorDebugInternalFrame2</span></span>](icordebuginternalframe2-interface.md)|<span data-ttu-id="276de-257">4</span><span class="sxs-lookup"><span data-stu-id="276de-257">4</span></span>|  
|`ver_ICorDebugRuntimeUnwindableFrame`|[<span data-ttu-id="276de-258">ICorDebugRuntimeUnwindableFrame</span><span class="sxs-lookup"><span data-stu-id="276de-258">ICorDebugRuntimeUnwindableFrame</span></span>](icordebugruntimeunwindableframe-interface.md)|<span data-ttu-id="276de-259">4</span><span class="sxs-lookup"><span data-stu-id="276de-259">4</span></span>|  
|`ver_ICorDebugHeapValue3`|[<span data-ttu-id="276de-260">Interfaccia ICorDebugHeapValue3</span><span class="sxs-lookup"><span data-stu-id="276de-260">ICorDebugHeapValue3 Interface</span></span>](icordebugheapvalue3-interface.md)|<span data-ttu-id="276de-261">4</span><span class="sxs-lookup"><span data-stu-id="276de-261">4</span></span>|  
|`ver_ICorDebugBlockingObjectEnum`|[<span data-ttu-id="276de-262">Interfaccia ICorDebugBlockingObjectEnum</span><span class="sxs-lookup"><span data-stu-id="276de-262">ICorDebugBlockingObjectEnum Interface</span></span>](icordebugblockingobjectenum-interface.md)|<span data-ttu-id="276de-263">4</span><span class="sxs-lookup"><span data-stu-id="276de-263">4</span></span>|  
|`ver_ICorDebugValue3`|[<span data-ttu-id="276de-264">ICorDebugValue3</span><span class="sxs-lookup"><span data-stu-id="276de-264">ICorDebugValue3</span></span>](icordebugvalue3-interface.md)|<span data-ttu-id="276de-265">4</span><span class="sxs-lookup"><span data-stu-id="276de-265">4</span></span>|  
|`ver_ICorDebugComObjectValue`|[<span data-ttu-id="276de-266">ICorDebugComObjectValue</span><span class="sxs-lookup"><span data-stu-id="276de-266">ICorDebugComObjectValue</span></span>](icordebugcomobjectvalue-interface.md)|<span data-ttu-id="276de-267">4.5</span><span class="sxs-lookup"><span data-stu-id="276de-267">4.5</span></span>|  
|`ver_ICorDebugAppDomain3`|[<span data-ttu-id="276de-268">ICorDebugAppDomain3</span><span class="sxs-lookup"><span data-stu-id="276de-268">ICorDebugAppDomain3</span></span>](icordebugappdomain3-interface.md)|<span data-ttu-id="276de-269">4.5</span><span class="sxs-lookup"><span data-stu-id="276de-269">4.5</span></span>|  
|`ver_ICorDebugCode3`|[<span data-ttu-id="276de-270">ICorDebugCode3</span><span class="sxs-lookup"><span data-stu-id="276de-270">ICorDebugCode3</span></span>](icordebugcode3-interface.md)|<span data-ttu-id="276de-271">4.5</span><span class="sxs-lookup"><span data-stu-id="276de-271">4.5</span></span>|  
|`ver_ICorDebugILFrame3`|[<span data-ttu-id="276de-272">ICorDebugILFrame3</span><span class="sxs-lookup"><span data-stu-id="276de-272">ICorDebugILFrame3</span></span>](icordebugilframe3-interface.md)|<span data-ttu-id="276de-273">4.5</span><span class="sxs-lookup"><span data-stu-id="276de-273">4.5</span></span>|  
|`CorDebugLatestVersion`|<span data-ttu-id="276de-274">La versione di .NET Framework, inclusi tutti i relativi Service Pack, è l'ultima versione.</span><span class="sxs-lookup"><span data-stu-id="276de-274">The version of the .NET Framework, including all of its service packs, is the latest version.</span></span>|-|  
  
## <a name="remarks"></a><span data-ttu-id="276de-275">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="276de-275">Remarks</span></span>  
 <span data-ttu-id="276de-276">Un debugger può `CorDebugInterfaceVersion` utilizzare l'enumerazione nella funzione [CreateDebuggingInterfaceFromVersion](../../../../docs/framework/unmanaged-api/hosting/createdebugginginterfacefromversion-function.md) per specificare la versione più recente di .NET Framework supportata dal debugger.</span><span class="sxs-lookup"><span data-stu-id="276de-276">A debugger can use the `CorDebugInterfaceVersion` enumeration in the [CreateDebuggingInterfaceFromVersion](../../../../docs/framework/unmanaged-api/hosting/createdebugginginterfacefromversion-function.md) function to specify the highest version of the .NET Framework that the debugger supports.</span></span>  
  
## <a name="interface-names"></a><span data-ttu-id="276de-277">Nomi delle interfacce</span><span class="sxs-lookup"><span data-stu-id="276de-277">Interface Names</span></span>  
 <span data-ttu-id="276de-278">Il numero visualizzato nella parte finale del nome di interfaccia nell'API di debug (ad esempio, "3" in `ICorDebugThread3`) specifica la versione dell'interfaccia, non la versione di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="276de-278">The number that appears at the end of the interface names in the debugging API (for example, the "3" in `ICorDebugThread3`) specifies the version of the interface, not the version of the .NET Framework.</span></span> <span data-ttu-id="276de-279">Tutti i nomi delle interfacce nell'API di debug includono i numeri di versione, ad eccezione delle interfacce introdotte in .NET Framework versione 1.</span><span class="sxs-lookup"><span data-stu-id="276de-279">All interface names in the debugging API include version numbers except for interfaces that were introduced in the .NET Framework version 1.</span></span> <span data-ttu-id="276de-280">L'eventuale corrispondenza tra numeri di versione dell'interfaccia e numeri di versione di .NET Framework è casuale.</span><span class="sxs-lookup"><span data-stu-id="276de-280">Any correspondence between interface version numbers and.NET Framework version numbers are coincidental.</span></span>  
  
- <span data-ttu-id="276de-281">Le interfacce introdotte in .NET Framework versione 1.0 non includono numeri, perché sono implicitamente tutte versioni 1.</span><span class="sxs-lookup"><span data-stu-id="276de-281">Interfaces that were introduced in the .NET Framework version 1.0 do not include numbers, because they are all implicitly version 1.</span></span>  
  
- <span data-ttu-id="276de-282">In .NET Framework versione 1.1 vengono usate interfacce 1.0 e non vengono introdotte nuove interfacce di debug.</span><span class="sxs-lookup"><span data-stu-id="276de-282">The .NET Framework version 1.1 uses version 1.0 interfaces, and does not introduce any new debugging interfaces.</span></span>  
  
- <span data-ttu-id="276de-283">Le 14 interfacce di debug introdotte in .NET Framework versione 2.0 sono estensioni logiche dei corrispettivi della versione 1 e includono il numero "2" nei nomi.</span><span class="sxs-lookup"><span data-stu-id="276de-283">The 14 debugging interfaces introduced in the .NET Framework version 2.0 are logical extensions of their version 1 counterparts and include the number "2" in their names.</span></span>  
  
- <span data-ttu-id="276de-284">In .NET Framework versioni 3.0 e 3.5 vengono usate le interfacce .NET Framework 2.0 esistenti e non vengono introdotte nuove interfacce.</span><span class="sxs-lookup"><span data-stu-id="276de-284">The .NET Framework versions 3.0 and 3.5 use the existing .NET Framework 2.0 interfaces, and do not introduce any new interfaces.</span></span>  
  
- <span data-ttu-id="276de-285">.NET Framework 4 introduce una combinazione di versioni dell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="276de-285">The .NET Framework 4 introduces a mix of interface versions.</span></span> <span data-ttu-id="276de-286">Ad esempio, sia `ICorDebugThread3` che `ICorDebugThread4` vengono visualizzate come terza e quarta versione dell'interfaccia `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="276de-286">For example, both `ICorDebugThread3` and `ICorDebugThread4` appear as the third and fourth versions of the `ICorDebugThread` interface.</span></span> <span data-ttu-id="276de-287">.NET Framework 4 introduce inoltre la `ICorDebugStackWalk` prima versione dell'interfaccia `ICorDebugNativeFrame` e`ICorDebugNativeFrame2`la seconda versione dell'interfaccia ( ).</span><span class="sxs-lookup"><span data-stu-id="276de-287">The .NET Framework 4 also introduces the first version of the `ICorDebugStackWalk` interface and the second version of the `ICorDebugNativeFrame` interface (`ICorDebugNativeFrame2`).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="276de-288">Requisiti</span><span class="sxs-lookup"><span data-stu-id="276de-288">Requirements</span></span>  
 <span data-ttu-id="276de-289">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="276de-289">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="276de-290">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="276de-290">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="276de-291">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="276de-291">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="276de-292">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="276de-292">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="276de-293">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="276de-293">See also</span></span>

- [<span data-ttu-id="276de-294">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="276de-294">Debugging Enumerations</span></span>](debugging-enumerations.md)
