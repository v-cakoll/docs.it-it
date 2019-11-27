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
ms.openlocfilehash: 6b551743227dc1c6069796038782a515e6dbe8c4
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74443781"
---
# <a name="corcheckduplicatesfor-enumeration"></a><span data-ttu-id="1ab33-102">Enumerazione CorCheckDuplicatesFor</span><span class="sxs-lookup"><span data-stu-id="1ab33-102">CorCheckDuplicatesFor Enumeration</span></span>
<span data-ttu-id="1ab33-103">Specifica i token di metadati per i quali verrà verificata la presenza di duplicati.</span><span class="sxs-lookup"><span data-stu-id="1ab33-103">Specifies the metadata tokens that will be checked for duplicates.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ab33-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1ab33-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="1ab33-105">Members</span><span class="sxs-lookup"><span data-stu-id="1ab33-105">Members</span></span>  
  
|<span data-ttu-id="1ab33-106">Membro</span><span class="sxs-lookup"><span data-stu-id="1ab33-106">Member</span></span>|<span data-ttu-id="1ab33-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1ab33-107">Description</span></span>|  
|------------|-----------------|  
|`MDDupAll`|<span data-ttu-id="1ab33-108">Verificare la presenza di duplicati in tutti i token di metadati.</span><span class="sxs-lookup"><span data-stu-id="1ab33-108">Check all metadata tokens for duplicates.</span></span>|  
|`MDDupENC`|<span data-ttu-id="1ab33-109">Non usato.</span><span class="sxs-lookup"><span data-stu-id="1ab33-109">Not used.</span></span>|  
|`MDNoDupChecks`|<span data-ttu-id="1ab33-110">Non controllare i token dei metadati per i duplicati.</span><span class="sxs-lookup"><span data-stu-id="1ab33-110">Do not check metadata tokens for duplicates.</span></span>|  
|`MDDupTypeDef`|<span data-ttu-id="1ab33-111">Verificare la presenza di duplicati dei token `mdTypeDef`.</span><span class="sxs-lookup"><span data-stu-id="1ab33-111">Check for duplicates of `mdTypeDef` tokens.</span></span>|  
|`MDDupInterfaceImpl`|<span data-ttu-id="1ab33-112">Verificare la presenza di duplicati dei token `mdInterfaceImpl`.</span><span class="sxs-lookup"><span data-stu-id="1ab33-112">Check for duplicates of `mdInterfaceImpl` tokens.</span></span>|  
|`MDDupMethodDef`|<span data-ttu-id="1ab33-113">Verificare la presenza di duplicati dei token `mdMethodDef`.</span><span class="sxs-lookup"><span data-stu-id="1ab33-113">Check for duplicates of `mdMethodDef` tokens.</span></span>|  
|`MDDupTypeRef`|<span data-ttu-id="1ab33-114">Verificare la presenza di duplicati dei token `mdTypeRef`.</span><span class="sxs-lookup"><span data-stu-id="1ab33-114">Check for duplicates of `mdTypeRef` tokens.</span></span>|  
|`MDDupMemberRef`|<span data-ttu-id="1ab33-115">Verificare la presenza di duplicati dei token `mdMemberRef`.</span><span class="sxs-lookup"><span data-stu-id="1ab33-115">Check for duplicates of `mdMemberRef` tokens.</span></span>|  
|`MDDupCustomAttribute`|<span data-ttu-id="1ab33-116">Verificare la presenza di duplicati dei token `mdCustomAttribute`.</span><span class="sxs-lookup"><span data-stu-id="1ab33-116">Check for duplicates of `mdCustomAttribute` tokens.</span></span>|  
|`MDDupParamDef`|<span data-ttu-id="1ab33-117">Verificare la presenza di duplicati dei token `mdParamDef`.</span><span class="sxs-lookup"><span data-stu-id="1ab33-117">Check for duplicates of `mdParamDef` tokens.</span></span>|  
|`MDDupPermission`|<span data-ttu-id="1ab33-118">Verificare la presenza di duplicati dei token `mdPermission`.</span><span class="sxs-lookup"><span data-stu-id="1ab33-118">Check for duplicates of `mdPermission` tokens.</span></span>|  
|`MDDupProperty`|<span data-ttu-id="1ab33-119">Verificare la presenza di duplicati dei token `mdProperty`.</span><span class="sxs-lookup"><span data-stu-id="1ab33-119">Check for duplicates of `mdProperty` tokens.</span></span>|  
|`MDDupEvent`|<span data-ttu-id="1ab33-120">Verificare la presenza di duplicati dei token `mdEvent`.</span><span class="sxs-lookup"><span data-stu-id="1ab33-120">Check for duplicates of `mdEvent` tokens.</span></span>|  
|`MDDupFieldDef`|<span data-ttu-id="1ab33-121">Verificare la presenza di duplicati dei token `mdFieldDef`.</span><span class="sxs-lookup"><span data-stu-id="1ab33-121">Check for duplicates of `mdFieldDef` tokens.</span></span>|  
|`MDDupSignature`|<span data-ttu-id="1ab33-122">Verificare la presenza di duplicati dei token `mdSignature`.</span><span class="sxs-lookup"><span data-stu-id="1ab33-122">Check for duplicates of `mdSignature` tokens.</span></span>|  
|`MDDupModuleRef`|<span data-ttu-id="1ab33-123">Verificare la presenza di duplicati dei token `mdModuleRef`.</span><span class="sxs-lookup"><span data-stu-id="1ab33-123">Check for duplicates of `mdModuleRef` tokens.</span></span>|  
|`MDDupTypeSpec`|<span data-ttu-id="1ab33-124">Verificare la presenza di duplicati dei token `mdTypeSpec`.</span><span class="sxs-lookup"><span data-stu-id="1ab33-124">Check for duplicates of `mdTypeSpec` tokens.</span></span>|  
|`MDDupImplMap`|<span data-ttu-id="1ab33-125">Verificare la presenza di duplicati dei token `mdImplMap`.</span><span class="sxs-lookup"><span data-stu-id="1ab33-125">Check for duplicates of `mdImplMap` tokens.</span></span>|  
|`MDDupAssemblyRef`|<span data-ttu-id="1ab33-126">Verificare la presenza di duplicati dei token `mdAssemblyRef`.</span><span class="sxs-lookup"><span data-stu-id="1ab33-126">Check for duplicates of `mdAssemblyRef` tokens.</span></span>|  
|`MDDupFile`|<span data-ttu-id="1ab33-127">Verificare la presenza di duplicati dei token `mdFile`.</span><span class="sxs-lookup"><span data-stu-id="1ab33-127">Check for duplicates of `mdFile` tokens.</span></span>|  
|`MDDupExportedType`|<span data-ttu-id="1ab33-128">Verificare la presenza di duplicati dei token `mdExportedType`.</span><span class="sxs-lookup"><span data-stu-id="1ab33-128">Check for duplicates of `mdExportedType` tokens.</span></span>|  
|`MDDupManifestResource`|<span data-ttu-id="1ab33-129">Verificare la presenza di duplicati dei token `mdManifestResource`.</span><span class="sxs-lookup"><span data-stu-id="1ab33-129">Check for duplicates of `mdManifestResource` tokens.</span></span>|  
|`MDDupGenericParam`|<span data-ttu-id="1ab33-130">Verificare la presenza di duplicati dei token `mdGenericParam`.</span><span class="sxs-lookup"><span data-stu-id="1ab33-130">Check for duplicates of `mdGenericParam` tokens.</span></span>|  
|`MDDupMethodSpec`|<span data-ttu-id="1ab33-131">Verificare la presenza di duplicati dei token `mdMethodSpec`.</span><span class="sxs-lookup"><span data-stu-id="1ab33-131">Check for duplicates of `mdMethodSpec` tokens.</span></span>|  
|`MDDupGenericParamConstraint`|<span data-ttu-id="1ab33-132">Verificare la presenza di duplicati dei token `mdGenericParamConstraint`.</span><span class="sxs-lookup"><span data-stu-id="1ab33-132">Check for duplicates of `mdGenericParamConstraint` tokens.</span></span>|  
|`MDDupAssembly`|<span data-ttu-id="1ab33-133">Verificare la presenza di duplicati dei token `mdAssembly`.</span><span class="sxs-lookup"><span data-stu-id="1ab33-133">Check for duplicates of `mdAssembly` tokens.</span></span>|  
|`MDDupDefault`|<span data-ttu-id="1ab33-134">Verificare la presenza di duplicati di `mdMemberRef`, `mdTypeRef`, `mdSignature`, `mdTypeSpec`e `mdMethodSpec` token.</span><span class="sxs-lookup"><span data-stu-id="1ab33-134">Check for duplicates of `mdMemberRef`, `mdTypeRef`, `mdSignature`, `mdTypeSpec`, and `mdMethodSpec` tokens.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1ab33-135">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1ab33-135">Requirements</span></span>  
 <span data-ttu-id="1ab33-136">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1ab33-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1ab33-137">**Intestazione:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="1ab33-137">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="1ab33-138">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1ab33-138">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ab33-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1ab33-139">See also</span></span>

- [<span data-ttu-id="1ab33-140">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="1ab33-140">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
