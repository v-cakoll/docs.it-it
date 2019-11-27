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
ms.openlocfilehash: 5f83cb96e39b257a1d35786130cd5ed31d071de7
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74443877"
---
# <a name="corattributetargets-enumeration"></a><span data-ttu-id="94fd2-102">Enumerazione CorAttributeTargets</span><span class="sxs-lookup"><span data-stu-id="94fd2-102">CorAttributeTargets Enumeration</span></span>
<span data-ttu-id="94fd2-103">Specifica gli elementi dell'applicazione ai quali è valido applicare un attributo.</span><span class="sxs-lookup"><span data-stu-id="94fd2-103">Specifies the application elements on which it is valid to apply an attribute.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94fd2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="94fd2-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="94fd2-105">Members</span><span class="sxs-lookup"><span data-stu-id="94fd2-105">Members</span></span>  
  
|<span data-ttu-id="94fd2-106">Membro</span><span class="sxs-lookup"><span data-stu-id="94fd2-106">Member</span></span>|<span data-ttu-id="94fd2-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="94fd2-107">Description</span></span>|  
|------------|-----------------|  
|`catAssembly`|<span data-ttu-id="94fd2-108">L'attributo può essere applicato a un assembly.</span><span class="sxs-lookup"><span data-stu-id="94fd2-108">Attribute can be applied to an assembly.</span></span>|  
|`catModule`|<span data-ttu-id="94fd2-109">L'attributo può essere applicato a un modulo eseguibile (con estensione dll o exe) portatile.</span><span class="sxs-lookup"><span data-stu-id="94fd2-109">Attribute can be applied to a portable executable (.dll or .exe) module.</span></span>|  
|`catClass`|<span data-ttu-id="94fd2-110">L'attributo può essere applicato a una classe.</span><span class="sxs-lookup"><span data-stu-id="94fd2-110">Attribute can be applied to a class.</span></span>|  
|`catStruct`|<span data-ttu-id="94fd2-111">L'attributo può essere applicato a una struttura; ovvero un tipo di valore.</span><span class="sxs-lookup"><span data-stu-id="94fd2-111">Attribute can be applied to a structure; that is, a value type.</span></span>|  
|`catEnum`|<span data-ttu-id="94fd2-112">L'attributo può essere applicato a un'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="94fd2-112">Attribute can be applied to an enumeration.</span></span>|  
|`catConstructor`|<span data-ttu-id="94fd2-113">L'attributo può essere applicato a un costruttore.</span><span class="sxs-lookup"><span data-stu-id="94fd2-113">Attribute can be applied to a constructor.</span></span>|  
|`catMethod`|<span data-ttu-id="94fd2-114">L'attributo può essere applicato a un metodo.</span><span class="sxs-lookup"><span data-stu-id="94fd2-114">Attribute can be applied to a method.</span></span>|  
|`catProperty`|<span data-ttu-id="94fd2-115">L'attributo può essere applicato a una proprietà.</span><span class="sxs-lookup"><span data-stu-id="94fd2-115">Attribute can be applied to a property.</span></span>|  
|`catField`|<span data-ttu-id="94fd2-116">L'attributo può essere applicato a un campo.</span><span class="sxs-lookup"><span data-stu-id="94fd2-116">Attribute can be applied to a field.</span></span>|  
|`catEvent`|<span data-ttu-id="94fd2-117">L'attributo può essere applicato a un evento.</span><span class="sxs-lookup"><span data-stu-id="94fd2-117">Attribute can be applied to an event.</span></span>|  
|`catInterface`|<span data-ttu-id="94fd2-118">L'attributo può essere applicato a un'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="94fd2-118">Attribute can be applied to an interface.</span></span>|  
|`catParameter`|<span data-ttu-id="94fd2-119">L'attributo può essere applicato a un parametro.</span><span class="sxs-lookup"><span data-stu-id="94fd2-119">Attribute can be applied to a parameter.</span></span>|  
|`catDelegate`|<span data-ttu-id="94fd2-120">L'attributo può essere applicato a un delegato.</span><span class="sxs-lookup"><span data-stu-id="94fd2-120">Attribute can be applied to a delegate.</span></span>|  
|`catGenericParameter`|<span data-ttu-id="94fd2-121">L'attributo può essere applicato a un parametro generico.</span><span class="sxs-lookup"><span data-stu-id="94fd2-121">Attribute can be applied to a generic parameter.</span></span>|  
|`catAll`|<span data-ttu-id="94fd2-122">L'attributo può essere applicato a qualsiasi elemento dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="94fd2-122">Attribute can be applied to any application element.</span></span>|  
|`catClassMembers`|<span data-ttu-id="94fd2-123">L'attributo può essere applicato a un membro di una classe.</span><span class="sxs-lookup"><span data-stu-id="94fd2-123">Attribute can be applied to a member of a class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="94fd2-124">Note</span><span class="sxs-lookup"><span data-stu-id="94fd2-124">Remarks</span></span>  
 <span data-ttu-id="94fd2-125">I valori di enumerazione `CorAttributeTargets` possono essere combinati con un'operazione OR bit per bit per ottenere la combinazione preferita.</span><span class="sxs-lookup"><span data-stu-id="94fd2-125">The `CorAttributeTargets` enumeration values can be combined with a bitwise OR operation to get the preferred combination.</span></span>  
  
 <span data-ttu-id="94fd2-126">Il `CorAttributeTargets` in parallelo all'enumerazione <xref:System.AttributeTargets?displayProperty=nameWithType> gestita.</span><span class="sxs-lookup"><span data-stu-id="94fd2-126">The `CorAttributeTargets` parallels the managed <xref:System.AttributeTargets?displayProperty=nameWithType> enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="94fd2-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="94fd2-127">Requirements</span></span>  
 <span data-ttu-id="94fd2-128">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="94fd2-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94fd2-129">**Intestazione:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="94fd2-129">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="94fd2-130">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94fd2-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94fd2-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="94fd2-131">See also</span></span>

- [<span data-ttu-id="94fd2-132">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="94fd2-132">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
