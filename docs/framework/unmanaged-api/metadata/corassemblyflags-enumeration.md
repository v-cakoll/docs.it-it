---
title: Enumerazione CorAssemblyFlags
ms.date: 03/30/2017
api_name:
- CorAssemblyFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorAssemblyFlags
helpviewer_keywords:
- CorAssemblyFlags enumeration [.NET Framework metadata]
ms.assetid: bb8db3b6-d81d-49fc-b74c-dbc908a9eab9
topic_type:
- apiref
ms.openlocfilehash: fda890cee5f513ea8cf7e82e710f5451a860c49f
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74443916"
---
# <a name="corassemblyflags-enumeration"></a><span data-ttu-id="60a60-102">Enumerazione CorAssemblyFlags</span><span class="sxs-lookup"><span data-stu-id="60a60-102">CorAssemblyFlags Enumeration</span></span>
<span data-ttu-id="60a60-103">Contiene valori che descrivono i metadati applicati alla compilazione di un assembly.</span><span class="sxs-lookup"><span data-stu-id="60a60-103">Contains values that describe the metadata applied to an assembly compilation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60a60-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="60a60-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="60a60-105">Members</span><span class="sxs-lookup"><span data-stu-id="60a60-105">Members</span></span>  
  
|<span data-ttu-id="60a60-106">Membro</span><span class="sxs-lookup"><span data-stu-id="60a60-106">Member</span></span>|<span data-ttu-id="60a60-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="60a60-107">Description</span></span>|  
|------------|-----------------|  
|`afPublicKey`|<span data-ttu-id="60a60-108">Indica che il riferimento all'assembly include la chiave pubblica completa e senza hash.</span><span class="sxs-lookup"><span data-stu-id="60a60-108">Indicates that the assembly reference holds the full, unhashed public key.</span></span>|  
|`afPA_None`|<span data-ttu-id="60a60-109">Indica che l'architettura del processore non è specificata.</span><span class="sxs-lookup"><span data-stu-id="60a60-109">Indicates that the processor architecture is unspecified.</span></span>|  
|`afPA_MSIL`|<span data-ttu-id="60a60-110">Indica che l'architettura del processore è neutra (PE32).</span><span class="sxs-lookup"><span data-stu-id="60a60-110">Indicates that the processor architecture is neutral (PE32).</span></span>|  
|`afPA_x86`|<span data-ttu-id="60a60-111">Indica che l'architettura del processore è x86 (PE32).</span><span class="sxs-lookup"><span data-stu-id="60a60-111">Indicates that the processor architecture is x86 (PE32).</span></span>|  
|`afPA_IA64`|<span data-ttu-id="60a60-112">Indica che l'architettura del processore è Itanium (PE32 +).</span><span class="sxs-lookup"><span data-stu-id="60a60-112">Indicates that the processor architecture is Itanium (PE32+).</span></span>|  
|`afPA_AMD64`|<span data-ttu-id="60a60-113">Indica che l'architettura del processore è AMD x64 (PE32 +).</span><span class="sxs-lookup"><span data-stu-id="60a60-113">Indicates that the processor architecture is AMD X64 (PE32+).</span></span>|  
|`afPA_ARM`|<span data-ttu-id="60a60-114">Indica che l'architettura del processore è ARM (PE32).</span><span class="sxs-lookup"><span data-stu-id="60a60-114">Indicates that the processor architecture is ARM (PE32).</span></span>|  
|`afPA_NoPlatform`|<span data-ttu-id="60a60-115">Indica che l'assembly è un assembly di riferimento. ovvero si applica a qualsiasi architettura, ma non può essere eseguita su qualsiasi architettura.</span><span class="sxs-lookup"><span data-stu-id="60a60-115">Indicates that the assembly is a reference assembly; that is, it applies to any architecture but cannot run on any architecture.</span></span> <span data-ttu-id="60a60-116">Pertanto, il flag corrisponde a `afPA_Mask`.</span><span class="sxs-lookup"><span data-stu-id="60a60-116">Thus, the flag is the same as `afPA_Mask`.</span></span>|  
|`afPA_Specified`|<span data-ttu-id="60a60-117">Indica che i flag di architettura del processore devono essere propagati al record `AssemblyRef`.</span><span class="sxs-lookup"><span data-stu-id="60a60-117">Indicates that the processor architecture flags should be propagated to the `AssemblyRef` record.</span></span>|  
|`afPA_Mask`|<span data-ttu-id="60a60-118">Maschera che descrive l'architettura del processore.</span><span class="sxs-lookup"><span data-stu-id="60a60-118">A mask that describes the processor architecture.</span></span>|  
|`afPA_FullMask`|<span data-ttu-id="60a60-119">Specifica che è inclusa la descrizione dell'architettura del processore.</span><span class="sxs-lookup"><span data-stu-id="60a60-119">Specifies that the processor architecture description is included.</span></span>|  
|`afPA_Shift`|<span data-ttu-id="60a60-120">Indica un conteggio dei turni nei flag di architettura del processore da e verso l'indice.</span><span class="sxs-lookup"><span data-stu-id="60a60-120">Indicates a shift count in the processor architecture flags to and from the index.</span></span>|  
|`afEnableJITcompileTracking`|<span data-ttu-id="60a60-121">Indica il valore corrispondente dalla <xref:System.Diagnostics.DebuggableAttribute.DebuggingModes> del <xref:System.Diagnostics.DebuggableAttribute>.</span><span class="sxs-lookup"><span data-stu-id="60a60-121">Indicates the corresponding value from the <xref:System.Diagnostics.DebuggableAttribute.DebuggingModes> of the <xref:System.Diagnostics.DebuggableAttribute>.</span></span>|  
|`afDisableJITcompileOptimizer`|<span data-ttu-id="60a60-122">Indica il valore corrispondente dalla <xref:System.Diagnostics.DebuggableAttribute.DebuggingModes> del <xref:System.Diagnostics.DebuggableAttribute>.</span><span class="sxs-lookup"><span data-stu-id="60a60-122">Indicates the corresponding value from the <xref:System.Diagnostics.DebuggableAttribute.DebuggingModes> of the <xref:System.Diagnostics.DebuggableAttribute>.</span></span>|  
|`afRetargetable`|<span data-ttu-id="60a60-123">Indica che l'assembly può essere ridestinato in fase di esecuzione a un assembly di un server di pubblicazione diverso.</span><span class="sxs-lookup"><span data-stu-id="60a60-123">Indicates that the assembly can be retargeted at run time to an assembly from a different publisher.</span></span>|  
|`afContentType_Mask`|<span data-ttu-id="60a60-124">Maschera che descrive il tipo di contenuto.</span><span class="sxs-lookup"><span data-stu-id="60a60-124">A mask that describes the content type.</span></span>|  
|`afContentType_Default`|<span data-ttu-id="60a60-125">Indica il tipo di contenuto predefinito.</span><span class="sxs-lookup"><span data-stu-id="60a60-125">Indicates the default content type.</span></span>|  
|`afContentType_WindowsRuntime`|<span data-ttu-id="60a60-126">Indica il tipo di contenuto Windows Runtime.</span><span class="sxs-lookup"><span data-stu-id="60a60-126">Indicates the Windows Runtime content type.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="60a60-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="60a60-127">Requirements</span></span>  
 <span data-ttu-id="60a60-128">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="60a60-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="60a60-129">**Intestazione:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="60a60-129">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="60a60-130">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="60a60-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60a60-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="60a60-131">See also</span></span>

- [<span data-ttu-id="60a60-132">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="60a60-132">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
