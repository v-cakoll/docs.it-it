---
title: Enumerazione CorCheckDuplicatesFor
ms.date: 03/30/2017
api_name:
- CorCheckDuplicatesFor
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorCheckDuplicatesFor
helpviewer_keywords:
- CorCheckDuplicatesFor enumeration [.NET Framework metadata]
ms.assetid: d8ec8d3c-70f7-4cc6-9957-68068fd8f49c
topic_type:
- apiref
ms.openlocfilehash: 2985c419b25b8bf76df8fee0f0f37ba9ebee3df7
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007901"
---
# <a name="corcheckduplicatesfor-enumeration"></a><span data-ttu-id="d175d-102">Enumerazione CorCheckDuplicatesFor</span><span class="sxs-lookup"><span data-stu-id="d175d-102">CorCheckDuplicatesFor Enumeration</span></span>
<span data-ttu-id="d175d-103">Specifica i token di metadati per i quali verrà verificata la presenza di duplicati.</span><span class="sxs-lookup"><span data-stu-id="d175d-103">Specifies the metadata tokens that will be checked for duplicates.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d175d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d175d-104">Syntax</span></span>  
  
```cpp  
typedef enum CorCheckDuplicatesFor {  
  
    MDDupAll                    = 0xffffffff,  
    MDDupENC                    = MDDupAll,  
    MDNoDupChecks               = 0x00000000,  
    MDDupTypeDef                = 0x00000001,  
    MDDupInterfaceImpl          = 0x00000002,  
    MDDupMethodDef              = 0x00000004,  
    MDDupTypeRef                = 0x00000008,  
    MDDupMemberRef              = 0x00000010,  
    MDDupCustomAttribute        = 0x00000020,  
    MDDupParamDef               = 0x00000040,  
    MDDupPermission             = 0x00000080,  
    MDDupProperty               = 0x00000100,  
    MDDupEvent                  = 0x00000200,  
    MDDupFieldDef               = 0x00000400,  
    MDDupSignature              = 0x00000800,  
    MDDupModuleRef              = 0x00001000,  
    MDDupTypeSpec               = 0x00002000,  
    MDDupImplMap                = 0x00004000,  
    MDDupAssemblyRef            = 0x00008000,  
    MDDupFile                   = 0x00010000,  
    MDDupExportedType           = 0x00020000,  
    MDDupManifestResource       = 0x00040000,  
    MDDupGenericParam           = 0x00080000,  
    MDDupMethodSpec             = 0x00100000,  
    MDDupGenericParamConstraint = 0x00200000,  
  
    MDDupAssembly               = 0x10000000,  
  
    MDDupDefault =
        MDNoDupChecks | MDDupTypeRef | MDDupMemberRef |
        MDDupSignature | MDDupTypeSpec | MDDupMethodSpec  
  
} CorCheckDuplicatesFor;  
```  
  
## <a name="members"></a><span data-ttu-id="d175d-105">Membri</span><span class="sxs-lookup"><span data-stu-id="d175d-105">Members</span></span>  
  
|<span data-ttu-id="d175d-106">Membro</span><span class="sxs-lookup"><span data-stu-id="d175d-106">Member</span></span>|<span data-ttu-id="d175d-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d175d-107">Description</span></span>|  
|------------|-----------------|  
|`MDDupAll`|<span data-ttu-id="d175d-108">Verificare la presenza di duplicati in tutti i token di metadati.</span><span class="sxs-lookup"><span data-stu-id="d175d-108">Check all metadata tokens for duplicates.</span></span>|  
|`MDDupENC`|<span data-ttu-id="d175d-109">Non usato.</span><span class="sxs-lookup"><span data-stu-id="d175d-109">Not used.</span></span>|  
|`MDNoDupChecks`|<span data-ttu-id="d175d-110">Non controllare i token dei metadati per i duplicati.</span><span class="sxs-lookup"><span data-stu-id="d175d-110">Do not check metadata tokens for duplicates.</span></span>|  
|`MDDupTypeDef`|<span data-ttu-id="d175d-111">Verificare la presenza di duplicati dei `mdTypeDef` token.</span><span class="sxs-lookup"><span data-stu-id="d175d-111">Check for duplicates of `mdTypeDef` tokens.</span></span>|  
|`MDDupInterfaceImpl`|<span data-ttu-id="d175d-112">Verificare la presenza di duplicati dei `mdInterfaceImpl` token.</span><span class="sxs-lookup"><span data-stu-id="d175d-112">Check for duplicates of `mdInterfaceImpl` tokens.</span></span>|  
|`MDDupMethodDef`|<span data-ttu-id="d175d-113">Verificare la presenza di duplicati dei `mdMethodDef` token.</span><span class="sxs-lookup"><span data-stu-id="d175d-113">Check for duplicates of `mdMethodDef` tokens.</span></span>|  
|`MDDupTypeRef`|<span data-ttu-id="d175d-114">Verificare la presenza di duplicati dei `mdTypeRef` token.</span><span class="sxs-lookup"><span data-stu-id="d175d-114">Check for duplicates of `mdTypeRef` tokens.</span></span>|  
|`MDDupMemberRef`|<span data-ttu-id="d175d-115">Verificare la presenza di duplicati dei `mdMemberRef` token.</span><span class="sxs-lookup"><span data-stu-id="d175d-115">Check for duplicates of `mdMemberRef` tokens.</span></span>|  
|`MDDupCustomAttribute`|<span data-ttu-id="d175d-116">Verificare la presenza di duplicati dei `mdCustomAttribute` token.</span><span class="sxs-lookup"><span data-stu-id="d175d-116">Check for duplicates of `mdCustomAttribute` tokens.</span></span>|  
|`MDDupParamDef`|<span data-ttu-id="d175d-117">Verificare la presenza di duplicati dei `mdParamDef` token.</span><span class="sxs-lookup"><span data-stu-id="d175d-117">Check for duplicates of `mdParamDef` tokens.</span></span>|  
|`MDDupPermission`|<span data-ttu-id="d175d-118">Verificare la presenza di duplicati dei `mdPermission` token.</span><span class="sxs-lookup"><span data-stu-id="d175d-118">Check for duplicates of `mdPermission` tokens.</span></span>|  
|`MDDupProperty`|<span data-ttu-id="d175d-119">Verificare la presenza di duplicati dei `mdProperty` token.</span><span class="sxs-lookup"><span data-stu-id="d175d-119">Check for duplicates of `mdProperty` tokens.</span></span>|  
|`MDDupEvent`|<span data-ttu-id="d175d-120">Verificare la presenza di duplicati dei `mdEvent` token.</span><span class="sxs-lookup"><span data-stu-id="d175d-120">Check for duplicates of `mdEvent` tokens.</span></span>|  
|`MDDupFieldDef`|<span data-ttu-id="d175d-121">Verificare la presenza di duplicati dei `mdFieldDef` token.</span><span class="sxs-lookup"><span data-stu-id="d175d-121">Check for duplicates of `mdFieldDef` tokens.</span></span>|  
|`MDDupSignature`|<span data-ttu-id="d175d-122">Verificare la presenza di duplicati dei `mdSignature` token.</span><span class="sxs-lookup"><span data-stu-id="d175d-122">Check for duplicates of `mdSignature` tokens.</span></span>|  
|`MDDupModuleRef`|<span data-ttu-id="d175d-123">Verificare la presenza di duplicati dei `mdModuleRef` token.</span><span class="sxs-lookup"><span data-stu-id="d175d-123">Check for duplicates of `mdModuleRef` tokens.</span></span>|  
|`MDDupTypeSpec`|<span data-ttu-id="d175d-124">Verificare la presenza di duplicati dei `mdTypeSpec` token.</span><span class="sxs-lookup"><span data-stu-id="d175d-124">Check for duplicates of `mdTypeSpec` tokens.</span></span>|  
|`MDDupImplMap`|<span data-ttu-id="d175d-125">Verificare la presenza di duplicati dei `mdImplMap` token.</span><span class="sxs-lookup"><span data-stu-id="d175d-125">Check for duplicates of `mdImplMap` tokens.</span></span>|  
|`MDDupAssemblyRef`|<span data-ttu-id="d175d-126">Verificare la presenza di duplicati dei `mdAssemblyRef` token.</span><span class="sxs-lookup"><span data-stu-id="d175d-126">Check for duplicates of `mdAssemblyRef` tokens.</span></span>|  
|`MDDupFile`|<span data-ttu-id="d175d-127">Verificare la presenza di duplicati dei `mdFile` token.</span><span class="sxs-lookup"><span data-stu-id="d175d-127">Check for duplicates of `mdFile` tokens.</span></span>|  
|`MDDupExportedType`|<span data-ttu-id="d175d-128">Verificare la presenza di duplicati dei `mdExportedType` token.</span><span class="sxs-lookup"><span data-stu-id="d175d-128">Check for duplicates of `mdExportedType` tokens.</span></span>|  
|`MDDupManifestResource`|<span data-ttu-id="d175d-129">Verificare la presenza di duplicati dei `mdManifestResource` token.</span><span class="sxs-lookup"><span data-stu-id="d175d-129">Check for duplicates of `mdManifestResource` tokens.</span></span>|  
|`MDDupGenericParam`|<span data-ttu-id="d175d-130">Verificare la presenza di duplicati dei `mdGenericParam` token.</span><span class="sxs-lookup"><span data-stu-id="d175d-130">Check for duplicates of `mdGenericParam` tokens.</span></span>|  
|`MDDupMethodSpec`|<span data-ttu-id="d175d-131">Verificare la presenza di duplicati dei `mdMethodSpec` token.</span><span class="sxs-lookup"><span data-stu-id="d175d-131">Check for duplicates of `mdMethodSpec` tokens.</span></span>|  
|`MDDupGenericParamConstraint`|<span data-ttu-id="d175d-132">Verificare la presenza di duplicati dei `mdGenericParamConstraint` token.</span><span class="sxs-lookup"><span data-stu-id="d175d-132">Check for duplicates of `mdGenericParamConstraint` tokens.</span></span>|  
|`MDDupAssembly`|<span data-ttu-id="d175d-133">Verificare la presenza di duplicati dei `mdAssembly` token.</span><span class="sxs-lookup"><span data-stu-id="d175d-133">Check for duplicates of `mdAssembly` tokens.</span></span>|  
|`MDDupDefault`|<span data-ttu-id="d175d-134">Verificare la presenza di duplicati dei `mdMemberRef` `mdTypeRef` token,,, `mdSignature` `mdTypeSpec` e `mdMethodSpec` .</span><span class="sxs-lookup"><span data-stu-id="d175d-134">Check for duplicates of `mdMemberRef`, `mdTypeRef`, `mdSignature`, `mdTypeSpec`, and `mdMethodSpec` tokens.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d175d-135">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d175d-135">Requirements</span></span>  
 <span data-ttu-id="d175d-136">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d175d-136">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d175d-137">**Intestazione:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="d175d-137">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="d175d-138">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d175d-138">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d175d-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d175d-139">See also</span></span>

- [<span data-ttu-id="d175d-140">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="d175d-140">Metadata Enumerations</span></span>](metadata-enumerations.md)
