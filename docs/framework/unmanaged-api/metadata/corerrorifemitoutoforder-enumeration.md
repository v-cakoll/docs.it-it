---
title: Enumerazione CorErrorIfEmitOutOfOrder
ms.date: 03/30/2017
api_name:
- CorErrorIfEmitOutOfOrder
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorErrorIfEmitOutOfOrder
helpviewer_keywords:
- CorErrorIfEmitOutOfOrder enumeration [.NET Framework metadata]
ms.assetid: 6d758aad-29a7-44fe-9481-bbff5b799a32
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d4e9d03dcf4603f9470f8f2509050eb6f875746a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33442640"
---
# <a name="corerrorifemitoutoforder-enumeration"></a><span data-ttu-id="87a00-102">Enumerazione CorErrorIfEmitOutOfOrder</span><span class="sxs-lookup"><span data-stu-id="87a00-102">CorErrorIfEmitOutOfOrder Enumeration</span></span>
<span data-ttu-id="87a00-103">Contiene valori di flag che indicano in quali condizioni è necessario generare un messaggio di errore per notificare che i metadati sono stati emessi senza ordine.</span><span class="sxs-lookup"><span data-stu-id="87a00-103">Contains flag values that indicate the conditions under which an error message should be generated when metadata is emitted out of order.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87a00-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="87a00-104">Syntax</span></span>  
  
```  
typedef enum CorErrorIfEmitOutOfOrder {  
  
    MDErrorOutOfOrderDefault    = 0x00000000,  
    MDErrorOutOfOrderNone       = 0x00000000,  
    MDErrorOutOfOrderAll        = 0xffffffff,  
    MDMethodOutOfOrder          = 0x00000001,  
    MDFieldOutOfOrder           = 0x00000002,  
    MDParamOutOfOrder           = 0x00000004,  
    MDPropertyOutOfOrder        = 0x00000008,  
    MDEventOutOfOrder           = 0x00000010  
  
} CorErrorIfEmitOutOfOrder;  
```  
  
## <a name="members"></a><span data-ttu-id="87a00-105">Membri</span><span class="sxs-lookup"><span data-stu-id="87a00-105">Members</span></span>  
  
|<span data-ttu-id="87a00-106">Membro</span><span class="sxs-lookup"><span data-stu-id="87a00-106">Member</span></span>|<span data-ttu-id="87a00-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="87a00-107">Description</span></span>|  
|------------|-----------------|  
|`MDErrorOutOfOrderDefault`|<span data-ttu-id="87a00-108">Indica il comportamento predefinito, che non genera messaggi di errore.</span><span class="sxs-lookup"><span data-stu-id="87a00-108">Indicates the default behavior, which does not generate error messages.</span></span>|  
|`MDErrorOutOfOrderNone`|<span data-ttu-id="87a00-109">Indica che il compilatore non deve generare messaggi di errore.</span><span class="sxs-lookup"><span data-stu-id="87a00-109">Indicates that the compiler should not generate error messages.</span></span>|  
|`MDErrorOutOfOrderAll`|<span data-ttu-id="87a00-110">Indica che il compilatore deve generare un messaggio di errore quando un campo, proprietà, evento, un metodo, o parametro è emesso senza ordine.</span><span class="sxs-lookup"><span data-stu-id="87a00-110">Indicates that the compiler should generate an error message when a field, property, event, method, or parameter is emitted out of order.</span></span>|  
|`MDMethodOutOfOrder`|<span data-ttu-id="87a00-111">Indica che il compilatore deve generare un messaggio di errore quando un metodo è emesso senza ordine.</span><span class="sxs-lookup"><span data-stu-id="87a00-111">Indicates that the compiler should generate an error message when a method is emitted out of order.</span></span>|  
|`MDFieldOutOfOrder`|<span data-ttu-id="87a00-112">Indica che il compilatore deve generare un messaggio di errore quando un campo è emesso senza ordine.</span><span class="sxs-lookup"><span data-stu-id="87a00-112">Indicates that the compiler should generate an error message when a field is emitted out of order.</span></span>|  
|`MDParamOutOfOrder`|<span data-ttu-id="87a00-113">Indica che il compilatore deve generare un messaggio di errore quando un parametro è emesso senza ordine.</span><span class="sxs-lookup"><span data-stu-id="87a00-113">Indicates that the compiler should generate an error message when a parameter is emitted out of order.</span></span>|  
|`MDPropertyOutOfOrder`|<span data-ttu-id="87a00-114">Indica che il compilatore deve generare un messaggio di errore quando una proprietà è emesso senza ordine.</span><span class="sxs-lookup"><span data-stu-id="87a00-114">Indicates that the compiler should generate an error message when a property is emitted out of order.</span></span>|  
|`MDEventOutOfOrder`|<span data-ttu-id="87a00-115">Indica che il compilatore deve generare un messaggio di errore quando un evento è emesso senza ordine.</span><span class="sxs-lookup"><span data-stu-id="87a00-115">Indicates that the compiler should generate an error message when an event is emitted out of order.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="87a00-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="87a00-116">Requirements</span></span>  
 <span data-ttu-id="87a00-117">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="87a00-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="87a00-118">**Intestazione:** CorHdr. H</span><span class="sxs-lookup"><span data-stu-id="87a00-118">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="87a00-119">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="87a00-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87a00-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="87a00-120">See Also</span></span>  
 [<span data-ttu-id="87a00-121">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="87a00-121">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
