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
ms.openlocfilehash: 7024140ed9b870b5db38dba7e9b13321dd37386a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59157586"
---
# <a name="cornativelink-structure"></a><span data-ttu-id="49114-102">Struttura COR_NATIVE_LINK</span><span class="sxs-lookup"><span data-stu-id="49114-102">COR_NATIVE_LINK Structure</span></span>
<span data-ttu-id="49114-103">Contiene informazioni usate per collegare il codice nativo.</span><span class="sxs-lookup"><span data-stu-id="49114-103">Contains information that is used to link native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49114-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="49114-104">Syntax</span></span>  
  
```  
typedef struct   
{  
    BYTE        m_linkType;  
    BYTE        m_flags;  
    mdMemberRef m_entryPoint;  
} COR_NATIVE_LINK;  
```  
  
## <a name="members"></a><span data-ttu-id="49114-105">Membri</span><span class="sxs-lookup"><span data-stu-id="49114-105">Members</span></span>  
  
|<span data-ttu-id="49114-106">Member</span><span class="sxs-lookup"><span data-stu-id="49114-106">Member</span></span>|<span data-ttu-id="49114-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="49114-107">Description</span></span>|  
|------------|-----------------|  
|`m_linkType`|<span data-ttu-id="49114-108">Il tipo di collegamento in codice nativo.</span><span class="sxs-lookup"><span data-stu-id="49114-108">The type to be linked in native code.</span></span> <span data-ttu-id="49114-109">Questo valore è un valore di [CorNativeLinkType](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md) valori.</span><span class="sxs-lookup"><span data-stu-id="49114-109">This value is one of the [CorNativeLinkType](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md) values.</span></span>|  
|`m_flags`|<span data-ttu-id="49114-110">Flag usati dal linker durante il collegamento di codice nativo.</span><span class="sxs-lookup"><span data-stu-id="49114-110">Flags used by the linker when linking native code.</span></span> <span data-ttu-id="49114-111">Questo valore è un valore di [CorNativeLinkFlags](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md) valori.</span><span class="sxs-lookup"><span data-stu-id="49114-111">This value is one of the [CorNativeLinkFlags](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md) values.</span></span>|  
|`m_entryPoint`|<span data-ttu-id="49114-112">Il token di metadati MemberRef che rappresenta il punto di ingresso.</span><span class="sxs-lookup"><span data-stu-id="49114-112">The MemberRef metadata token that represents the entry point.</span></span> <span data-ttu-id="49114-113">Il formato è `lib:entrypoint`.</span><span class="sxs-lookup"><span data-stu-id="49114-113">The format is `lib:entrypoint`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="49114-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="49114-114">Requirements</span></span>  
 <span data-ttu-id="49114-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="49114-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="49114-116">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="49114-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="49114-117">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="49114-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="49114-118">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="49114-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="49114-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="49114-119">See also</span></span>

- [<span data-ttu-id="49114-120">Strutture di metadati</span><span class="sxs-lookup"><span data-stu-id="49114-120">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
- [<span data-ttu-id="49114-121">Enumerazione CorNativeLinkType</span><span class="sxs-lookup"><span data-stu-id="49114-121">CorNativeLinkType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md)
- [<span data-ttu-id="49114-122">Enumerazione CorNativeLinkFlags</span><span class="sxs-lookup"><span data-stu-id="49114-122">CorNativeLinkFlags Enumeration</span></span>](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md)
