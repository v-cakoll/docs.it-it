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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: eca4b66a3f7c1a96bb06827dde477f34cb904ba3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59072714"
---
# <a name="corassemblyflags-enumeration"></a><span data-ttu-id="01f4b-102">Enumerazione CorAssemblyFlags</span><span class="sxs-lookup"><span data-stu-id="01f4b-102">CorAssemblyFlags Enumeration</span></span>
<span data-ttu-id="01f4b-103">Contiene valori che descrivono i metadati applicati alla compilazione di un assembly.</span><span class="sxs-lookup"><span data-stu-id="01f4b-103">Contains values that describe the metadata applied to an assembly compilation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01f4b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="01f4b-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="01f4b-105">Membri</span><span class="sxs-lookup"><span data-stu-id="01f4b-105">Members</span></span>  
  
|<span data-ttu-id="01f4b-106">Member</span><span class="sxs-lookup"><span data-stu-id="01f4b-106">Member</span></span>|<span data-ttu-id="01f4b-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="01f4b-107">Description</span></span>|  
|------------|-----------------|  
|`afPublicKey`|<span data-ttu-id="01f4b-108">Indica che il riferimento all'assembly contiene la chiave pubblica completa, senza hash.</span><span class="sxs-lookup"><span data-stu-id="01f4b-108">Indicates that the assembly reference holds the full, unhashed public key.</span></span>|  
|`afPA_None`|<span data-ttu-id="01f4b-109">Indica che l'architettura del processore non è specificata.</span><span class="sxs-lookup"><span data-stu-id="01f4b-109">Indicates that the processor architecture is unspecified.</span></span>|  
|`afPA_MSIL`|<span data-ttu-id="01f4b-110">Indica che l'architettura del processore è neutra (PE32).</span><span class="sxs-lookup"><span data-stu-id="01f4b-110">Indicates that the processor architecture is neutral (PE32).</span></span>|  
|`afPA_x86`|<span data-ttu-id="01f4b-111">Indica che l'architettura del processore x86 (PE32).</span><span class="sxs-lookup"><span data-stu-id="01f4b-111">Indicates that the processor architecture is x86 (PE32).</span></span>|  
|`afPA_IA64`|<span data-ttu-id="01f4b-112">Indica che l'architettura del processore Itanium (PE32 +).</span><span class="sxs-lookup"><span data-stu-id="01f4b-112">Indicates that the processor architecture is Itanium (PE32+).</span></span>|  
|`afPA_AMD64`|<span data-ttu-id="01f4b-113">Indica che l'architettura del processore AMD X64 (PE32 +).</span><span class="sxs-lookup"><span data-stu-id="01f4b-113">Indicates that the processor architecture is AMD X64 (PE32+).</span></span>|  
|`afPA_ARM`|<span data-ttu-id="01f4b-114">Indica che l'architettura del processore ARM (PE32).</span><span class="sxs-lookup"><span data-stu-id="01f4b-114">Indicates that the processor architecture is ARM (PE32).</span></span>|  
|`afPA_NoPlatform`|<span data-ttu-id="01f4b-115">Indica che l'assembly è un assembly di riferimento. vale a dire, si applica a qualsiasi architettura, ma non è possibile eseguire su qualsiasi architettura.</span><span class="sxs-lookup"><span data-stu-id="01f4b-115">Indicates that the assembly is a reference assembly; that is, it applies to any architecture but cannot run on any architecture.</span></span> <span data-ttu-id="01f4b-116">Di conseguenza, il flag è identico `afPA_Mask`.</span><span class="sxs-lookup"><span data-stu-id="01f4b-116">Thus, the flag is the same as `afPA_Mask`.</span></span>|  
|`afPA_Specified`|<span data-ttu-id="01f4b-117">Indica che il flag di architettura del processore deve essere propagato al `AssemblyRef` record.</span><span class="sxs-lookup"><span data-stu-id="01f4b-117">Indicates that the processor architecture flags should be propagated to the `AssemblyRef` record.</span></span>|  
|`afPA_Mask`|<span data-ttu-id="01f4b-118">Maschera che descrive l'architettura del processore.</span><span class="sxs-lookup"><span data-stu-id="01f4b-118">A mask that describes the processor architecture.</span></span>|  
|`afPA_FullMask`|<span data-ttu-id="01f4b-119">Specifica che la descrizione dell'architettura del processore è inclusa.</span><span class="sxs-lookup"><span data-stu-id="01f4b-119">Specifies that the processor architecture description is included.</span></span>|  
|`afPA_Shift`|<span data-ttu-id="01f4b-120">Indica un conteggio dello spostamento nei flag di architettura di processore da e verso l'indice.</span><span class="sxs-lookup"><span data-stu-id="01f4b-120">Indicates a shift count in the processor architecture flags to and from the index.</span></span>|  
|`afEnableJITcompileTracking`|<span data-ttu-id="01f4b-121">Indica il valore corrispondente dal <xref:System.Diagnostics.DebuggableAttribute.DebuggingModes> del <xref:System.Diagnostics.DebuggableAttribute>.</span><span class="sxs-lookup"><span data-stu-id="01f4b-121">Indicates the corresponding value from the <xref:System.Diagnostics.DebuggableAttribute.DebuggingModes> of the <xref:System.Diagnostics.DebuggableAttribute>.</span></span>|  
|`afDisableJITcompileOptimizer`|<span data-ttu-id="01f4b-122">Indica il valore corrispondente dal <xref:System.Diagnostics.DebuggableAttribute.DebuggingModes> del <xref:System.Diagnostics.DebuggableAttribute>.</span><span class="sxs-lookup"><span data-stu-id="01f4b-122">Indicates the corresponding value from the <xref:System.Diagnostics.DebuggableAttribute.DebuggingModes> of the <xref:System.Diagnostics.DebuggableAttribute>.</span></span>|  
|`afRetargetable`|<span data-ttu-id="01f4b-123">Indica che l'assembly può essere ridestinato in fase di esecuzione a un assembly da un autore diverso.</span><span class="sxs-lookup"><span data-stu-id="01f4b-123">Indicates that the assembly can be retargeted at run time to an assembly from a different publisher.</span></span>|  
|`afContentType_Mask`|<span data-ttu-id="01f4b-124">Maschera che descrive il tipo di contenuto.</span><span class="sxs-lookup"><span data-stu-id="01f4b-124">A mask that describes the content type.</span></span>|  
|`afContentType_Default`|<span data-ttu-id="01f4b-125">Indica il tipo di contenuto predefinito.</span><span class="sxs-lookup"><span data-stu-id="01f4b-125">Indicates the default content type.</span></span>|  
|`afContentType_WindowsRuntime`|<span data-ttu-id="01f4b-126">Indica il [!INCLUDE[wrt](../../../../includes/wrt-md.md)] tipo di contenuto.</span><span class="sxs-lookup"><span data-stu-id="01f4b-126">Indicates the [!INCLUDE[wrt](../../../../includes/wrt-md.md)] content type.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="01f4b-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="01f4b-127">Requirements</span></span>  
 <span data-ttu-id="01f4b-128">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="01f4b-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="01f4b-129">**Intestazione:** CorHdr. H</span><span class="sxs-lookup"><span data-stu-id="01f4b-129">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="01f4b-130">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="01f4b-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01f4b-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="01f4b-131">See also</span></span>

- [<span data-ttu-id="01f4b-132">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="01f4b-132">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
