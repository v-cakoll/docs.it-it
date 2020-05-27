---
title: Enumerazione CorMethodSemanticsAttr
ms.date: 03/30/2017
api_name:
- CorMethodSemanticsAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorMethodSemanticsAttr
helpviewer_keywords:
- CorMethodSemanticsAttr enumeration [.NET Framework metadata]
ms.assetid: ca2af325-eb9d-4a91-90e4-267e45b98611
topic_type:
- apiref
ms.openlocfilehash: 1572c206f4a5a5fe0fd189ca84d0bcda2249c6d4
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007650"
---
# <a name="cormethodsemanticsattr-enumeration"></a><span data-ttu-id="47dcb-102">Enumerazione CorMethodSemanticsAttr</span><span class="sxs-lookup"><span data-stu-id="47dcb-102">CorMethodSemanticsAttr Enumeration</span></span>
<span data-ttu-id="47dcb-103">Contiene valori che descrivono la relazione tra un metodo e una proprietà o evento associato.</span><span class="sxs-lookup"><span data-stu-id="47dcb-103">Contains values that describe the relationship between a method and an associated property or event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47dcb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="47dcb-104">Syntax</span></span>  
  
```cpp  
typedef enum CorMethodSemanticsAttr {  
  
    msSetter    =   0x0001,  
    msGetter    =   0x0002,  
    msOther     =   0x0004,  
    msAddOn     =   0x0008,  
    msRemoveOn  =   0x0010,  
    msFire      =   0x0020,  
  
} CorMethodSemanticsAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="47dcb-105">Membri</span><span class="sxs-lookup"><span data-stu-id="47dcb-105">Members</span></span>  
  
|<span data-ttu-id="47dcb-106">Membro</span><span class="sxs-lookup"><span data-stu-id="47dcb-106">Member</span></span>|<span data-ttu-id="47dcb-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="47dcb-107">Description</span></span>|  
|------------|-----------------|  
|`msSetter`|<span data-ttu-id="47dcb-108">Specifica che il metodo è una `set` funzione di accesso per una proprietà.</span><span class="sxs-lookup"><span data-stu-id="47dcb-108">Specifies that the method is a `set` accessor for a property.</span></span>|  
|`msGetter`|<span data-ttu-id="47dcb-109">Specifica che il metodo è una `get` funzione di accesso per una proprietà.</span><span class="sxs-lookup"><span data-stu-id="47dcb-109">Specifies that the method is a `get` accessor for a property.</span></span>|  
|`msOther`|<span data-ttu-id="47dcb-110">Specifica che il metodo ha una relazione con una proprietà o un evento diverso da quelli definiti qui.</span><span class="sxs-lookup"><span data-stu-id="47dcb-110">Specifies that the method has a relationship to a property or an event other than those defined here.</span></span>|  
|`msAddOn`|<span data-ttu-id="47dcb-111">Specifica che il metodo aggiunge metodi di gestione per un evento.</span><span class="sxs-lookup"><span data-stu-id="47dcb-111">Specifies that the method adds handler methods for an event.</span></span>|  
|`msRemoveOn`|<span data-ttu-id="47dcb-112">Specifica che il metodo rimuove i metodi del gestore per un evento.</span><span class="sxs-lookup"><span data-stu-id="47dcb-112">Specifies that the method removes handler methods for an event.</span></span>|  
|`msFire`|<span data-ttu-id="47dcb-113">Specifica che il metodo genera un evento.</span><span class="sxs-lookup"><span data-stu-id="47dcb-113">Specifies that the method raises an event.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="47dcb-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="47dcb-114">Requirements</span></span>  
 <span data-ttu-id="47dcb-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="47dcb-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="47dcb-116">**Intestazione:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="47dcb-116">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="47dcb-117">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="47dcb-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47dcb-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="47dcb-118">See also</span></span>

- [<span data-ttu-id="47dcb-119">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="47dcb-119">Metadata Enumerations</span></span>](metadata-enumerations.md)
