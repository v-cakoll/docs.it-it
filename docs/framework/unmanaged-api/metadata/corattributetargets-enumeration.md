---
title: Enumerazione CorAttributeTargets
ms.date: 03/30/2017
api_name:
- CorAttributeTargets
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorAttributeTargets
helpviewer_keywords:
- CorAttributeTargets enumeration [.NET Framework metadata]
ms.assetid: 694c0fa0-7011-41a9-9dfd-f0e16ea574b5
topic_type:
- apiref
ms.openlocfilehash: f1836f26af99f91ab1765107573f6b067edd5e95
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007923"
---
# <a name="corattributetargets-enumeration"></a><span data-ttu-id="d1b44-102">Enumerazione CorAttributeTargets</span><span class="sxs-lookup"><span data-stu-id="d1b44-102">CorAttributeTargets Enumeration</span></span>
<span data-ttu-id="d1b44-103">Specifica gli elementi dell'applicazione ai quali è valido applicare un attributo.</span><span class="sxs-lookup"><span data-stu-id="d1b44-103">Specifies the application elements on which it is valid to apply an attribute.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1b44-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d1b44-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="d1b44-105">Membri</span><span class="sxs-lookup"><span data-stu-id="d1b44-105">Members</span></span>  
  
|<span data-ttu-id="d1b44-106">Membro</span><span class="sxs-lookup"><span data-stu-id="d1b44-106">Member</span></span>|<span data-ttu-id="d1b44-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d1b44-107">Description</span></span>|  
|------------|-----------------|  
|`catAssembly`|<span data-ttu-id="d1b44-108">Attributo applicabile a un assembly.</span><span class="sxs-lookup"><span data-stu-id="d1b44-108">Attribute can be applied to an assembly.</span></span>|  
|`catModule`|<span data-ttu-id="d1b44-109">L'attributo può essere applicato a un modulo eseguibile (con estensione dll o exe) portatile.</span><span class="sxs-lookup"><span data-stu-id="d1b44-109">Attribute can be applied to a portable executable (.dll or .exe) module.</span></span>|  
|`catClass`|<span data-ttu-id="d1b44-110">Attributo applicabile a una classe.</span><span class="sxs-lookup"><span data-stu-id="d1b44-110">Attribute can be applied to a class.</span></span>|  
|`catStruct`|<span data-ttu-id="d1b44-111">Attributo applicabile a una struttura, ovvero a un tipo valore.</span><span class="sxs-lookup"><span data-stu-id="d1b44-111">Attribute can be applied to a structure; that is, a value type.</span></span>|  
|`catEnum`|<span data-ttu-id="d1b44-112">Attributo applicabile a un'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="d1b44-112">Attribute can be applied to an enumeration.</span></span>|  
|`catConstructor`|<span data-ttu-id="d1b44-113">Attributo applicabile a un costruttore.</span><span class="sxs-lookup"><span data-stu-id="d1b44-113">Attribute can be applied to a constructor.</span></span>|  
|`catMethod`|<span data-ttu-id="d1b44-114">Attributo applicabile a un metodo.</span><span class="sxs-lookup"><span data-stu-id="d1b44-114">Attribute can be applied to a method.</span></span>|  
|`catProperty`|<span data-ttu-id="d1b44-115">Attributo applicabile a una proprietà.</span><span class="sxs-lookup"><span data-stu-id="d1b44-115">Attribute can be applied to a property.</span></span>|  
|`catField`|<span data-ttu-id="d1b44-116">Attributo applicabile a un campo.</span><span class="sxs-lookup"><span data-stu-id="d1b44-116">Attribute can be applied to a field.</span></span>|  
|`catEvent`|<span data-ttu-id="d1b44-117">Attributo applicabile a un evento.</span><span class="sxs-lookup"><span data-stu-id="d1b44-117">Attribute can be applied to an event.</span></span>|  
|`catInterface`|<span data-ttu-id="d1b44-118">Attributo applicabile a un'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="d1b44-118">Attribute can be applied to an interface.</span></span>|  
|`catParameter`|<span data-ttu-id="d1b44-119">Attributo applicabile a un parametro.</span><span class="sxs-lookup"><span data-stu-id="d1b44-119">Attribute can be applied to a parameter.</span></span>|  
|`catDelegate`|<span data-ttu-id="d1b44-120">Attributo applicabile a un delegato.</span><span class="sxs-lookup"><span data-stu-id="d1b44-120">Attribute can be applied to a delegate.</span></span>|  
|`catGenericParameter`|<span data-ttu-id="d1b44-121">Attributo applicabile a un parametro generico.</span><span class="sxs-lookup"><span data-stu-id="d1b44-121">Attribute can be applied to a generic parameter.</span></span>|  
|`catAll`|<span data-ttu-id="d1b44-122">Attributo applicabile a tutti gli elementi dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d1b44-122">Attribute can be applied to any application element.</span></span>|  
|`catClassMembers`|<span data-ttu-id="d1b44-123">L'attributo può essere applicato a un membro di una classe.</span><span class="sxs-lookup"><span data-stu-id="d1b44-123">Attribute can be applied to a member of a class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d1b44-124">Commenti</span><span class="sxs-lookup"><span data-stu-id="d1b44-124">Remarks</span></span>  
 <span data-ttu-id="d1b44-125">I `CorAttributeTargets` valori di enumerazione possono essere combinati con un'operazione OR bit per bit per ottenere la combinazione preferita.</span><span class="sxs-lookup"><span data-stu-id="d1b44-125">The `CorAttributeTargets` enumeration values can be combined with a bitwise OR operation to get the preferred combination.</span></span>  
  
 <span data-ttu-id="d1b44-126">`CorAttributeTargets`Parallels l'enumerazione gestita <xref:System.AttributeTargets?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="d1b44-126">The `CorAttributeTargets` parallels the managed <xref:System.AttributeTargets?displayProperty=nameWithType> enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d1b44-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d1b44-127">Requirements</span></span>  
 <span data-ttu-id="d1b44-128">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d1b44-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d1b44-129">**Intestazione:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="d1b44-129">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="d1b44-130">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d1b44-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1b44-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d1b44-131">See also</span></span>

- [<span data-ttu-id="d1b44-132">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="d1b44-132">Metadata Enumerations</span></span>](metadata-enumerations.md)
