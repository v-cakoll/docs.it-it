---
title: Struttura COR_NATIVE_LINK
ms.date: 03/30/2017
api_name:
- COR_NATIVE_LINK
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COR_NATIVE_LINK
helpviewer_keywords:
- COR_NATIVE_LINK structure [.NET Framework metadata]
ms.assetid: 6ef78d3c-1c69-4141-b687-dcb065b7a74d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d0d9b8a9a1014d98c51f1471f8203be07f7ff49c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33440957"
---
# <a name="cornativelink-structure"></a><span data-ttu-id="f258f-102">Struttura COR_NATIVE_LINK</span><span class="sxs-lookup"><span data-stu-id="f258f-102">COR_NATIVE_LINK Structure</span></span>
<span data-ttu-id="f258f-103">Contiene informazioni usate per collegare il codice nativo.</span><span class="sxs-lookup"><span data-stu-id="f258f-103">Contains information that is used to link native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f258f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f258f-104">Syntax</span></span>  
  
```  
typedef struct   
{  
    BYTE        m_linkType;  
    BYTE        m_flags;  
    mdMemberRef m_entryPoint;  
} COR_NATIVE_LINK;  
```  
  
## <a name="members"></a><span data-ttu-id="f258f-105">Membri</span><span class="sxs-lookup"><span data-stu-id="f258f-105">Members</span></span>  
  
|<span data-ttu-id="f258f-106">Membro</span><span class="sxs-lookup"><span data-stu-id="f258f-106">Member</span></span>|<span data-ttu-id="f258f-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f258f-107">Description</span></span>|  
|------------|-----------------|  
|`m_linkType`|<span data-ttu-id="f258f-108">Il tipo di collegamento in codice nativo.</span><span class="sxs-lookup"><span data-stu-id="f258f-108">The type to be linked in native code.</span></span> <span data-ttu-id="f258f-109">Questo valore è un valore di [CorNativeLinkType](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md) valori.</span><span class="sxs-lookup"><span data-stu-id="f258f-109">This value is one of the [CorNativeLinkType](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md) values.</span></span>|  
|`m_flags`|<span data-ttu-id="f258f-110">Flag usati dal linker durante il collegamento del codice nativo.</span><span class="sxs-lookup"><span data-stu-id="f258f-110">Flags used by the linker when linking native code.</span></span> <span data-ttu-id="f258f-111">Questo valore è un valore di [CorNativeLinkFlags](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md) valori.</span><span class="sxs-lookup"><span data-stu-id="f258f-111">This value is one of the [CorNativeLinkFlags](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md) values.</span></span>|  
|`m_entryPoint`|<span data-ttu-id="f258f-112">Il token di metadati di MemberRef che rappresenta il punto di ingresso.</span><span class="sxs-lookup"><span data-stu-id="f258f-112">The MemberRef metadata token that represents the entry point.</span></span> <span data-ttu-id="f258f-113">Il formato è `lib:entrypoint`.</span><span class="sxs-lookup"><span data-stu-id="f258f-113">The format is `lib:entrypoint`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f258f-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f258f-114">Requirements</span></span>  
 <span data-ttu-id="f258f-115">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f258f-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f258f-116">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="f258f-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f258f-117">**Libreria:** usata come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="f258f-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f258f-118">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f258f-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f258f-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f258f-119">See Also</span></span>  
 [<span data-ttu-id="f258f-120">Strutture di metadati</span><span class="sxs-lookup"><span data-stu-id="f258f-120">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)  
 [<span data-ttu-id="f258f-121">Enumerazione CorNativeLinkType</span><span class="sxs-lookup"><span data-stu-id="f258f-121">CorNativeLinkType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md)  
 [<span data-ttu-id="f258f-122">Enumerazione CorNativeLinkFlags</span><span class="sxs-lookup"><span data-stu-id="f258f-122">CorNativeLinkFlags Enumeration</span></span>](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md)
