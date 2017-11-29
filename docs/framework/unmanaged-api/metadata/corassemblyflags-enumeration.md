---
title: Enumerazione CorAssemblyFlags
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorAssemblyFlags
api_location: mscoree.dll
api_type: COM
f1_keywords: CorAssemblyFlags
helpviewer_keywords: CorAssemblyFlags enumeration [.NET Framework metadata]
ms.assetid: bb8db3b6-d81d-49fc-b74c-dbc908a9eab9
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 67057944705a1cecd1754c3c11da08725c9a93f9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="corassemblyflags-enumeration"></a><span data-ttu-id="ab518-102">Enumerazione CorAssemblyFlags</span><span class="sxs-lookup"><span data-stu-id="ab518-102">CorAssemblyFlags Enumeration</span></span>
<span data-ttu-id="ab518-103">Contiene valori che descrivono i metadati applicati alla compilazione di un assembly.</span><span class="sxs-lookup"><span data-stu-id="ab518-103">Contains values that describe the metadata applied to an assembly compilation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab518-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ab518-104">Syntax</span></span>  
  
```  
typedef enum CorAssemblyFlags {  
  
    afPublicKey             =   0x0001,  
    afPA_None               =   0x0000,  
    afPA_MSIL               =   0x0010,  
    afPA_x86                =   0x0020,  
    afPA_IA64               =   0x0030,  
    afPA_AMD64              =   0x0040,  
    afPA_ARM                =   0x0050,  
    afPA_NoPlatform         =   0x0070,  
    afPA_Specified          =   0x0080,  
    afPA_Mask               =   0x0070,  
    afPA_FullMask           =   0x00F0,  
    afPA_Shift              =   0x0004,  
  
    afEnableJITcompileTracking  =   0x8000,  
    afDisableJITcompileOptimizer=   0x4000,  
  
    afRetargetable          =   0x0100,  
    afContentType_Default        =   0x0000,  
    afContentType_WindowsRuntime =   0x0200,  
    afContentType_Mask           =   0x0E00,  
  
} CorAssemblyFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="ab518-105">Membri</span><span class="sxs-lookup"><span data-stu-id="ab518-105">Members</span></span>  
  
|<span data-ttu-id="ab518-106">Membro</span><span class="sxs-lookup"><span data-stu-id="ab518-106">Member</span></span>|<span data-ttu-id="ab518-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ab518-107">Description</span></span>|  
|------------|-----------------|  
|`afPublicKey`|<span data-ttu-id="ab518-108">Indica che il riferimento all'assembly contiene la chiave pubblica completa, senza hash.</span><span class="sxs-lookup"><span data-stu-id="ab518-108">Indicates that the assembly reference holds the full, unhashed public key.</span></span>|  
|`afPA_None`|<span data-ttu-id="ab518-109">Indica che l'architettura del processore non è specificata.</span><span class="sxs-lookup"><span data-stu-id="ab518-109">Indicates that the processor architecture is unspecified.</span></span>|  
|`afPA_MSIL`|<span data-ttu-id="ab518-110">Indica che l'architettura del processore è neutra (PE32).</span><span class="sxs-lookup"><span data-stu-id="ab518-110">Indicates that the processor architecture is neutral (PE32).</span></span>|  
|`afPA_x86`|<span data-ttu-id="ab518-111">Indica che l'architettura del processore x86 (PE32).</span><span class="sxs-lookup"><span data-stu-id="ab518-111">Indicates that the processor architecture is x86 (PE32).</span></span>|  
|`afPA_IA64`|<span data-ttu-id="ab518-112">Indica che l'architettura del processore Itanium (PE32 +).</span><span class="sxs-lookup"><span data-stu-id="ab518-112">Indicates that the processor architecture is Itanium (PE32+).</span></span>|  
|`afPA_AMD64`|<span data-ttu-id="ab518-113">Indica che l'architettura del processore AMD X64 (PE32 +).</span><span class="sxs-lookup"><span data-stu-id="ab518-113">Indicates that the processor architecture is AMD X64 (PE32+).</span></span>|  
|`afPA_ARM`|<span data-ttu-id="ab518-114">Indica che l'architettura del processore ARM (PE32).</span><span class="sxs-lookup"><span data-stu-id="ab518-114">Indicates that the processor architecture is ARM (PE32).</span></span>|  
|`afPA_NoPlatform`|<span data-ttu-id="ab518-115">Indica che l'assembly è un assembly di riferimento. ovvero, si applica a qualsiasi architettura, ma non è possibile eseguire su qualsiasi architettura.</span><span class="sxs-lookup"><span data-stu-id="ab518-115">Indicates that the assembly is a reference assembly; that is, it applies to any architecture but cannot run on any architecture.</span></span> <span data-ttu-id="ab518-116">Di conseguenza, il flag è identico `afPA_Mask`.</span><span class="sxs-lookup"><span data-stu-id="ab518-116">Thus, the flag is the same as `afPA_Mask`.</span></span>|  
|`afPA_Specified`|<span data-ttu-id="ab518-117">Indica che i flag di architettura del processore devono essere propagati ad il `AssemblyRef` record.</span><span class="sxs-lookup"><span data-stu-id="ab518-117">Indicates that the processor architecture flags should be propagated to the `AssemblyRef` record.</span></span>|  
|`afPA_Mask`|<span data-ttu-id="ab518-118">Maschera che descrive l'architettura del processore.</span><span class="sxs-lookup"><span data-stu-id="ab518-118">A mask that describes the processor architecture.</span></span>|  
|`afPA_FullMask`|<span data-ttu-id="ab518-119">Specifica che la descrizione dell'architettura del processore è inclusa.</span><span class="sxs-lookup"><span data-stu-id="ab518-119">Specifies that the processor architecture description is included.</span></span>|  
|`afPA_Shift`|<span data-ttu-id="ab518-120">Indica un numero di spostamenti nei flag di architettura del processore da e verso l'indice.</span><span class="sxs-lookup"><span data-stu-id="ab518-120">Indicates a shift count in the processor architecture flags to and from the index.</span></span>|  
|`afEnableJITcompileTracking`|<span data-ttu-id="ab518-121">Indica il valore corrispondente di <xref:System.Diagnostics.DebuggableAttribute.DebuggingModes> del <xref:System.Diagnostics.DebuggableAttribute>.</span><span class="sxs-lookup"><span data-stu-id="ab518-121">Indicates the corresponding value from the <xref:System.Diagnostics.DebuggableAttribute.DebuggingModes> of the <xref:System.Diagnostics.DebuggableAttribute>.</span></span>|  
|`afDisableJITcompileOptimizer`|<span data-ttu-id="ab518-122">Indica il valore corrispondente di <xref:System.Diagnostics.DebuggableAttribute.DebuggingModes> del <xref:System.Diagnostics.DebuggableAttribute>.</span><span class="sxs-lookup"><span data-stu-id="ab518-122">Indicates the corresponding value from the <xref:System.Diagnostics.DebuggableAttribute.DebuggingModes> of the <xref:System.Diagnostics.DebuggableAttribute>.</span></span>|  
|`afRetargetable`|<span data-ttu-id="ab518-123">Indica che l'assembly può essere reindirizzato in fase di esecuzione a un assembly da un server di pubblicazione diverso.</span><span class="sxs-lookup"><span data-stu-id="ab518-123">Indicates that the assembly can be retargeted at run time to an assembly from a different publisher.</span></span>|  
|`afContentType_Mask`|<span data-ttu-id="ab518-124">Maschera che descrive il tipo di contenuto.</span><span class="sxs-lookup"><span data-stu-id="ab518-124">A mask that describes the content type.</span></span>|  
|`afContentType_Default`|<span data-ttu-id="ab518-125">Indica il tipo di contenuto predefinito.</span><span class="sxs-lookup"><span data-stu-id="ab518-125">Indicates the default content type.</span></span>|  
|`afContentType_WindowsRuntime`|<span data-ttu-id="ab518-126">Indica il [!INCLUDE[wrt](../../../../includes/wrt-md.md)] tipo di contenuto.</span><span class="sxs-lookup"><span data-stu-id="ab518-126">Indicates the [!INCLUDE[wrt](../../../../includes/wrt-md.md)] content type.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ab518-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ab518-127">Requirements</span></span>  
 <span data-ttu-id="ab518-128">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ab518-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ab518-129">**Intestazione:** CorHdr. H</span><span class="sxs-lookup"><span data-stu-id="ab518-129">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="ab518-130">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ab518-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab518-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ab518-131">See Also</span></span>  
 [<span data-ttu-id="ab518-132">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="ab518-132">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
