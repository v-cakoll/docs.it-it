---
title: Enumerazione CorAttributeTargets
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorAttributeTargets
api_location: mscoree.dll
api_type: COM
f1_keywords: CorAttributeTargets
helpviewer_keywords: CorAttributeTargets enumeration [.NET Framework metadata]
ms.assetid: 694c0fa0-7011-41a9-9dfd-f0e16ea574b5
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4ce701c026b4e977c376b6e6f0f342b031634e38
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="corattributetargets-enumeration"></a><span data-ttu-id="f0011-102">Enumerazione CorAttributeTargets</span><span class="sxs-lookup"><span data-stu-id="f0011-102">CorAttributeTargets Enumeration</span></span>
<span data-ttu-id="f0011-103">Specifica gli elementi dell'applicazione ai quali è valido applicare un attributo.</span><span class="sxs-lookup"><span data-stu-id="f0011-103">Specifies the application elements on which it is valid to apply an attribute.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0011-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f0011-104">Syntax</span></span>  
  
```  
typedef enum CorAttributeTargets  
{  
    catAssembly            = 0x0001,  
    catModule              = 0x0002,  
    catClass               = 0x0004,  
    catStruct              = 0x0008,  
    catEnum                = 0x0010,  
    catConstructor         = 0x0020,  
    catMethod              = 0x0040,  
    catProperty            = 0x0080,  
    catField               = 0x0100,  
    catEvent               = 0x0200,  
    catInterface           = 0x0400,  
    catParameter           = 0x0800,  
    catDelegate            = 0x1000,  
    catGenericParameter    = 0x4000,  
  
    catAll                 =   
        catAssembly | catModule | catClass | catStruct |   
        catEnum | catConstructor | catMethod | catProperty |   
        catField | catEvent | catInterface | catParameter |   
        catDelegate | catGenericParameter,  
  
    catClassMembers        =   
        catClass | catStruct | catEnum | catConstructor |   
        catMethod | catProperty | catField | catEvent |   
        catDelegate | catInterface  
  
} CorAttributeTargets;  
```  
  
## <a name="members"></a><span data-ttu-id="f0011-105">Membri</span><span class="sxs-lookup"><span data-stu-id="f0011-105">Members</span></span>  
  
|<span data-ttu-id="f0011-106">Membro</span><span class="sxs-lookup"><span data-stu-id="f0011-106">Member</span></span>|<span data-ttu-id="f0011-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f0011-107">Description</span></span>|  
|------------|-----------------|  
|`catAssembly`|<span data-ttu-id="f0011-108">Attributo può essere applicato a un assembly.</span><span class="sxs-lookup"><span data-stu-id="f0011-108">Attribute can be applied to an assembly.</span></span>|  
|`catModule`|<span data-ttu-id="f0011-109">Attributo può essere applicato a un modulo (con estensione dll o .exe) eseguibile portabile.</span><span class="sxs-lookup"><span data-stu-id="f0011-109">Attribute can be applied to a portable executable (.dll or .exe) module.</span></span>|  
|`catClass`|<span data-ttu-id="f0011-110">Attributo può essere applicato a una classe.</span><span class="sxs-lookup"><span data-stu-id="f0011-110">Attribute can be applied to a class.</span></span>|  
|`catStruct`|<span data-ttu-id="f0011-111">Attributo può essere applicato a una struttura; ovvero, un tipo di valore.</span><span class="sxs-lookup"><span data-stu-id="f0011-111">Attribute can be applied to a structure; that is, a value type.</span></span>|  
|`catEnum`|<span data-ttu-id="f0011-112">Attributo può essere applicato a un'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="f0011-112">Attribute can be applied to an enumeration.</span></span>|  
|`catConstructor`|<span data-ttu-id="f0011-113">Attributo può essere applicato a un costruttore.</span><span class="sxs-lookup"><span data-stu-id="f0011-113">Attribute can be applied to a constructor.</span></span>|  
|`catMethod`|<span data-ttu-id="f0011-114">Attributo può essere applicato a un metodo.</span><span class="sxs-lookup"><span data-stu-id="f0011-114">Attribute can be applied to a method.</span></span>|  
|`catProperty`|<span data-ttu-id="f0011-115">Attributo può essere applicato a una proprietà.</span><span class="sxs-lookup"><span data-stu-id="f0011-115">Attribute can be applied to a property.</span></span>|  
|`catField`|<span data-ttu-id="f0011-116">Attributo può essere applicato a un campo.</span><span class="sxs-lookup"><span data-stu-id="f0011-116">Attribute can be applied to a field.</span></span>|  
|`catEvent`|<span data-ttu-id="f0011-117">Attributo può essere applicato a un evento.</span><span class="sxs-lookup"><span data-stu-id="f0011-117">Attribute can be applied to an event.</span></span>|  
|`catInterface`|<span data-ttu-id="f0011-118">Attributo può essere applicato a un'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="f0011-118">Attribute can be applied to an interface.</span></span>|  
|`catParameter`|<span data-ttu-id="f0011-119">Attributo può essere applicato a un parametro.</span><span class="sxs-lookup"><span data-stu-id="f0011-119">Attribute can be applied to a parameter.</span></span>|  
|`catDelegate`|<span data-ttu-id="f0011-120">Attributo può essere applicato a un delegato.</span><span class="sxs-lookup"><span data-stu-id="f0011-120">Attribute can be applied to a delegate.</span></span>|  
|`catGenericParameter`|<span data-ttu-id="f0011-121">Attributo può essere applicato a un parametro generico.</span><span class="sxs-lookup"><span data-stu-id="f0011-121">Attribute can be applied to a generic parameter.</span></span>|  
|`catAll`|<span data-ttu-id="f0011-122">Attributo può essere applicato a qualsiasi elemento dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f0011-122">Attribute can be applied to any application element.</span></span>|  
|`catClassMembers`|<span data-ttu-id="f0011-123">Attributo può essere applicato a un membro di una classe.</span><span class="sxs-lookup"><span data-stu-id="f0011-123">Attribute can be applied to a member of a class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f0011-124">Note</span><span class="sxs-lookup"><span data-stu-id="f0011-124">Remarks</span></span>  
 <span data-ttu-id="f0011-125">Il `CorAttributeTargets` valori di enumerazione possono essere combinati con un'operazione OR bit per bit per ottenere la combinazione desiderata.</span><span class="sxs-lookup"><span data-stu-id="f0011-125">The `CorAttributeTargets` enumeration values can be combined with a bitwise OR operation to get the preferred combination.</span></span>  
  
 <span data-ttu-id="f0011-126">Il `CorAttributeTargets` parallelo gestito <xref:System.AttributeTargets?displayProperty=nameWithType> enumerazione.</span><span class="sxs-lookup"><span data-stu-id="f0011-126">The `CorAttributeTargets` parallels the managed <xref:System.AttributeTargets?displayProperty=nameWithType> enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0011-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f0011-127">Requirements</span></span>  
 <span data-ttu-id="f0011-128">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f0011-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0011-129">**Intestazione:** CorHdr. H</span><span class="sxs-lookup"><span data-stu-id="f0011-129">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="f0011-130">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0011-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0011-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f0011-131">See Also</span></span>  
 [<span data-ttu-id="f0011-132">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="f0011-132">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
