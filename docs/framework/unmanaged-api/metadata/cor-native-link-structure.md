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
ms.openlocfilehash: a11b7d5939c4c20504b1ff3dfb4613f85bca0db4
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007975"
---
# <a name="cor_native_link-structure"></a><span data-ttu-id="73f9a-102">Struttura COR_NATIVE_LINK</span><span class="sxs-lookup"><span data-stu-id="73f9a-102">COR_NATIVE_LINK Structure</span></span>
<span data-ttu-id="73f9a-103">Contiene informazioni usate per collegare il codice nativo.</span><span class="sxs-lookup"><span data-stu-id="73f9a-103">Contains information that is used to link native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73f9a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="73f9a-104">Syntax</span></span>  
  
```cpp  
typedef struct
{  
    BYTE        m_linkType;  
    BYTE        m_flags;  
    mdMemberRef m_entryPoint;  
} COR_NATIVE_LINK;  
```  
  
## <a name="members"></a><span data-ttu-id="73f9a-105">Membri</span><span class="sxs-lookup"><span data-stu-id="73f9a-105">Members</span></span>  
  
|<span data-ttu-id="73f9a-106">Membro</span><span class="sxs-lookup"><span data-stu-id="73f9a-106">Member</span></span>|<span data-ttu-id="73f9a-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="73f9a-107">Description</span></span>|  
|------------|-----------------|  
|`m_linkType`|<span data-ttu-id="73f9a-108">Tipo da collegare nel codice nativo.</span><span class="sxs-lookup"><span data-stu-id="73f9a-108">The type to be linked in native code.</span></span> <span data-ttu-id="73f9a-109">Questo valore è uno dei valori [CorNativeLinkType](cornativelinktype-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="73f9a-109">This value is one of the [CorNativeLinkType](cornativelinktype-enumeration.md) values.</span></span>|  
|`m_flags`|<span data-ttu-id="73f9a-110">Flag utilizzati dal linker durante il collegamento del codice nativo.</span><span class="sxs-lookup"><span data-stu-id="73f9a-110">Flags used by the linker when linking native code.</span></span> <span data-ttu-id="73f9a-111">Questo valore è uno dei valori [CorNativeLinkFlags](cornativelinkflags-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="73f9a-111">This value is one of the [CorNativeLinkFlags](cornativelinkflags-enumeration.md) values.</span></span>|  
|`m_entryPoint`|<span data-ttu-id="73f9a-112">Token di metadati MemberRef che rappresenta il punto di ingresso.</span><span class="sxs-lookup"><span data-stu-id="73f9a-112">The MemberRef metadata token that represents the entry point.</span></span> <span data-ttu-id="73f9a-113">Il formato è `lib:entrypoint`.</span><span class="sxs-lookup"><span data-stu-id="73f9a-113">The format is `lib:entrypoint`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="73f9a-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="73f9a-114">Requirements</span></span>  
 <span data-ttu-id="73f9a-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="73f9a-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="73f9a-116">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="73f9a-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="73f9a-117">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="73f9a-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="73f9a-118">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="73f9a-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73f9a-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="73f9a-119">See also</span></span>

- [<span data-ttu-id="73f9a-120">Strutture di metadati</span><span class="sxs-lookup"><span data-stu-id="73f9a-120">Metadata Structures</span></span>](metadata-structures.md)
- [<span data-ttu-id="73f9a-121">Enumerazione CorNativeLinkType</span><span class="sxs-lookup"><span data-stu-id="73f9a-121">CorNativeLinkType Enumeration</span></span>](cornativelinktype-enumeration.md)
- [<span data-ttu-id="73f9a-122">Enumerazione CorNativeLinkFlags</span><span class="sxs-lookup"><span data-stu-id="73f9a-122">CorNativeLinkFlags Enumeration</span></span>](cornativelinkflags-enumeration.md)
