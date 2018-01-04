---
title: Struttura COR_NATIVE_LINK
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_NATIVE_LINK
api_location: mscoree.dll
api_type: COM
f1_keywords: COR_NATIVE_LINK
helpviewer_keywords: COR_NATIVE_LINK structure [.NET Framework metadata]
ms.assetid: 6ef78d3c-1c69-4141-b687-dcb065b7a74d
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 63e5946e98e7c862a2502a71a02e605a38086618
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="cornativelink-structure"></a><span data-ttu-id="7b0c5-102">Struttura COR_NATIVE_LINK</span><span class="sxs-lookup"><span data-stu-id="7b0c5-102">COR_NATIVE_LINK Structure</span></span>
<span data-ttu-id="7b0c5-103">Contiene informazioni usate per collegare il codice nativo.</span><span class="sxs-lookup"><span data-stu-id="7b0c5-103">Contains information that is used to link native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b0c5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7b0c5-104">Syntax</span></span>  
  
```  
typedef struct   
{  
    BYTE        m_linkType;  
    BYTE        m_flags;  
    mdMemberRef m_entryPoint;  
} COR_NATIVE_LINK;  
```  
  
## <a name="members"></a><span data-ttu-id="7b0c5-105">Membri</span><span class="sxs-lookup"><span data-stu-id="7b0c5-105">Members</span></span>  
  
|<span data-ttu-id="7b0c5-106">Membro</span><span class="sxs-lookup"><span data-stu-id="7b0c5-106">Member</span></span>|<span data-ttu-id="7b0c5-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7b0c5-107">Description</span></span>|  
|------------|-----------------|  
|`m_linkType`|<span data-ttu-id="7b0c5-108">Il tipo di collegamento in codice nativo.</span><span class="sxs-lookup"><span data-stu-id="7b0c5-108">The type to be linked in native code.</span></span> <span data-ttu-id="7b0c5-109">Questo valore è un valore di [CorNativeLinkType](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md) valori.</span><span class="sxs-lookup"><span data-stu-id="7b0c5-109">This value is one of the [CorNativeLinkType](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md) values.</span></span>|  
|`m_flags`|<span data-ttu-id="7b0c5-110">Flag usati dal linker durante il collegamento del codice nativo.</span><span class="sxs-lookup"><span data-stu-id="7b0c5-110">Flags used by the linker when linking native code.</span></span> <span data-ttu-id="7b0c5-111">Questo valore è un valore di [CorNativeLinkFlags](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md) valori.</span><span class="sxs-lookup"><span data-stu-id="7b0c5-111">This value is one of the [CorNativeLinkFlags](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md) values.</span></span>|  
|`m_entryPoint`|<span data-ttu-id="7b0c5-112">Il token di metadati di MemberRef che rappresenta il punto di ingresso.</span><span class="sxs-lookup"><span data-stu-id="7b0c5-112">The MemberRef metadata token that represents the entry point.</span></span> <span data-ttu-id="7b0c5-113">Il formato è `lib:entrypoint`.</span><span class="sxs-lookup"><span data-stu-id="7b0c5-113">The format is `lib:entrypoint`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7b0c5-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7b0c5-114">Requirements</span></span>  
 <span data-ttu-id="7b0c5-115">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7b0c5-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b0c5-116">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="7b0c5-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7b0c5-117">**Libreria:** usata come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7b0c5-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7b0c5-118">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b0c5-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b0c5-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7b0c5-119">See Also</span></span>  
 [<span data-ttu-id="7b0c5-120">Strutture di metadati</span><span class="sxs-lookup"><span data-stu-id="7b0c5-120">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)  
 [<span data-ttu-id="7b0c5-121">Enumerazione CorNativeLinkType</span><span class="sxs-lookup"><span data-stu-id="7b0c5-121">CorNativeLinkType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md)  
 [<span data-ttu-id="7b0c5-122">Enumerazione CorNativeLinkFlags</span><span class="sxs-lookup"><span data-stu-id="7b0c5-122">CorNativeLinkFlags Enumeration</span></span>](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md)
