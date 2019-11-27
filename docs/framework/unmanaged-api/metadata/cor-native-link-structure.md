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
ms.openlocfilehash: d03c22c455f0e44ce32d4593d9eee50ceef94a22
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74443953"
---
# <a name="cor_native_link-structure"></a><span data-ttu-id="50c42-102">Struttura COR_NATIVE_LINK</span><span class="sxs-lookup"><span data-stu-id="50c42-102">COR_NATIVE_LINK Structure</span></span>
<span data-ttu-id="50c42-103">Contiene informazioni usate per collegare il codice nativo.</span><span class="sxs-lookup"><span data-stu-id="50c42-103">Contains information that is used to link native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50c42-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="50c42-104">Syntax</span></span>  
  
```cpp  
typedef struct   
{  
    BYTE        m_linkType;  
    BYTE        m_flags;  
    mdMemberRef m_entryPoint;  
} COR_NATIVE_LINK;  
```  
  
## <a name="members"></a><span data-ttu-id="50c42-105">Members</span><span class="sxs-lookup"><span data-stu-id="50c42-105">Members</span></span>  
  
|<span data-ttu-id="50c42-106">Membro</span><span class="sxs-lookup"><span data-stu-id="50c42-106">Member</span></span>|<span data-ttu-id="50c42-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="50c42-107">Description</span></span>|  
|------------|-----------------|  
|`m_linkType`|<span data-ttu-id="50c42-108">Tipo da collegare nel codice nativo.</span><span class="sxs-lookup"><span data-stu-id="50c42-108">The type to be linked in native code.</span></span> <span data-ttu-id="50c42-109">Questo valore è uno dei valori [CorNativeLinkType](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="50c42-109">This value is one of the [CorNativeLinkType](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md) values.</span></span>|  
|`m_flags`|<span data-ttu-id="50c42-110">Flag utilizzati dal linker durante il collegamento del codice nativo.</span><span class="sxs-lookup"><span data-stu-id="50c42-110">Flags used by the linker when linking native code.</span></span> <span data-ttu-id="50c42-111">Questo valore è uno dei valori [CorNativeLinkFlags](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="50c42-111">This value is one of the [CorNativeLinkFlags](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md) values.</span></span>|  
|`m_entryPoint`|<span data-ttu-id="50c42-112">Token di metadati MemberRef che rappresenta il punto di ingresso.</span><span class="sxs-lookup"><span data-stu-id="50c42-112">The MemberRef metadata token that represents the entry point.</span></span> <span data-ttu-id="50c42-113">Il formato è `lib:entrypoint`.</span><span class="sxs-lookup"><span data-stu-id="50c42-113">The format is `lib:entrypoint`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="50c42-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="50c42-114">Requirements</span></span>  
 <span data-ttu-id="50c42-115">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="50c42-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50c42-116">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="50c42-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="50c42-117">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="50c42-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="50c42-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50c42-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50c42-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="50c42-119">See also</span></span>

- [<span data-ttu-id="50c42-120">Strutture di metadati</span><span class="sxs-lookup"><span data-stu-id="50c42-120">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
- [<span data-ttu-id="50c42-121">Enumerazione CorNativeLinkType</span><span class="sxs-lookup"><span data-stu-id="50c42-121">CorNativeLinkType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md)
- [<span data-ttu-id="50c42-122">Enumerazione CorNativeLinkFlags</span><span class="sxs-lookup"><span data-stu-id="50c42-122">CorNativeLinkFlags Enumeration</span></span>](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md)
