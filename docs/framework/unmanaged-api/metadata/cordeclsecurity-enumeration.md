---
title: Enumerazione CorDeclSecurity
ms.date: 03/30/2017
api_name:
- CorDeclSecurity
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorDeclSecurity
helpviewer_keywords:
- CorDeclSecurity enumeration [.NET Framework metadata]
ms.assetid: 864f1267-d267-4696-8df7-1f83f8444d6f
topic_type:
- apiref
ms.openlocfilehash: ffbc9a10ff48b3dfd59b95c0f6b9ecab80b6a49c
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007884"
---
# <a name="cordeclsecurity-enumeration"></a><span data-ttu-id="c44fd-102">Enumerazione CorDeclSecurity</span><span class="sxs-lookup"><span data-stu-id="c44fd-102">CorDeclSecurity Enumeration</span></span>
<span data-ttu-id="c44fd-103">Specifica le azioni relative alla sicurezza che possono essere eseguite con la sicurezza dichiarativa.</span><span class="sxs-lookup"><span data-stu-id="c44fd-103">Specifies the security actions that can be performed using declarative security.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c44fd-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c44fd-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDeclSecurity {  
  
    dclActionMask               =   0x001f,  
    dclActionNil                =   0x0000,  
    dclRequest                  =   0x0001,  
    dclDemand                   =   0x0002,  
    dclAssert                   =   0x0003,  
    dclDeny                     =   0x0004,  
    dclPermitOnly               =   0x0005,  
    dclLinktimeCheck            =   0x0006,  
    dclInheritanceCheck         =   0x0007,  
    dclRequestMinimum           =   0x0008,  
    dclRequestOptional          =   0x0009,  
    dclRequestRefuse            =   0x000a,  
    dclPrejitGrant              =   0x000b,  
    dclPrejitDenied             =   0x000c,  
    dclNonCasDemand             =   0x000d,  
    dclNonCasLinkDemand         =   0x000e,  
    dclNonCasInheritance        =   0x000f,  
    dclLinkDemandChoice         =   0x0010,  
    dclInheritanceDemandChoice  =   0x0011,  
    dclDemandChoice             =   0x0012,  
    dclMaximumValue             =   0x0012  
  
} CorDeclSecurity;  
```  
  
## <a name="members"></a><span data-ttu-id="c44fd-105">Membri</span><span class="sxs-lookup"><span data-stu-id="c44fd-105">Members</span></span>  
  
|<span data-ttu-id="c44fd-106">Membro</span><span class="sxs-lookup"><span data-stu-id="c44fd-106">Member</span></span>|<span data-ttu-id="c44fd-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c44fd-107">Description</span></span>|  
|------------|-----------------|  
|`dclActionMask`|<span data-ttu-id="c44fd-108">Riservato.</span><span class="sxs-lookup"><span data-stu-id="c44fd-108">Reserved.</span></span>|  
|`dclActionNil`|<span data-ttu-id="c44fd-109">Riservato.</span><span class="sxs-lookup"><span data-stu-id="c44fd-109">Reserved.</span></span>|  
|`dclRequest`|<span data-ttu-id="c44fd-110">Riservato.</span><span class="sxs-lookup"><span data-stu-id="c44fd-110">Reserved.</span></span>|  
|`dclDemand`|<span data-ttu-id="c44fd-111">A tutti i chiamanti nella parte superiore dello stack di chiamate deve essere concessa l'autorizzazione specificata dall'oggetto di autorizzazione corrente.</span><span class="sxs-lookup"><span data-stu-id="c44fd-111">All callers higher in the call stack are required to have been granted the permission specified by the current permission object.</span></span>|  
|`dclAssert`|<span data-ttu-id="c44fd-112">Il codice chiamante può accedere alla risorsa identificata dall'oggetto di autorizzazione corrente, anche se ai chiamanti più in alto nello stack non è stata concessa l'autorizzazione per accedere alla risorsa</span><span class="sxs-lookup"><span data-stu-id="c44fd-112">The calling code can access the resource identified by the current permission object, even if callers higher in the stack have not been granted permission to access the resource</span></span>|  
|`dclDeny`|<span data-ttu-id="c44fd-113">La possibilità di accedere alla risorsa specificata dall'oggetto di autorizzazione corrente viene negata ai chiamanti, anche se è stata concessa l'autorizzazione per accedervi.</span><span class="sxs-lookup"><span data-stu-id="c44fd-113">The ability to access the resource specified by the current permission object is denied to callers, even if they have been granted permission to access it.</span></span>|  
|`dclPermitOnly`|<span data-ttu-id="c44fd-114">È possibile accedere solo alle risorse specificate dall'oggetto di autorizzazione, anche se al codice è stata concessa l'autorizzazione per accedere ad altre risorse.</span><span class="sxs-lookup"><span data-stu-id="c44fd-114">Only the resources specified by this permission object can be accessed, even if the code has been granted permission to access other resources.</span></span>|  
|`dclLinktimeCheck`|<span data-ttu-id="c44fd-115">Al chiamante immediato è necessario concedere l'autorizzazione specificata per un determinato periodo di tempo.</span><span class="sxs-lookup"><span data-stu-id="c44fd-115">The immediate caller is required to have been granted the specified permission for a given period of time.</span></span>|  
|`dclInheritanceCheck`|<span data-ttu-id="c44fd-116">Alla classe derivata che eredita un'altra classe o che esegue l'override di un metodo è necessario concedere l'autorizzazione specificata.</span><span class="sxs-lookup"><span data-stu-id="c44fd-116">The derived class inheriting another class or overriding a method is required to have been granted the specified permission.</span></span>|  
|`dclRequestMinimum`|<span data-ttu-id="c44fd-117">Il chiamante può richiedere le autorizzazioni minime necessarie per l'esecuzione del codice.</span><span class="sxs-lookup"><span data-stu-id="c44fd-117">The caller can request for the minimum permissions required for code to run.</span></span> <span data-ttu-id="c44fd-118">Questa azione può essere usata solo nell'ambito dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="c44fd-118">This action can only be used within the scope of the assembly.</span></span>|  
|`dclRequestOptional`|<span data-ttu-id="c44fd-119">Il chiamante può richiedere autorizzazioni aggiuntive facoltative (non necessarie per l'esecuzione).</span><span class="sxs-lookup"><span data-stu-id="c44fd-119">The caller can request for additional permissions that are optional (not required to run).</span></span> <span data-ttu-id="c44fd-120">Con questa richiesta viene implicitamente rifiutata ogni altra autorizzazione che non sia stata esplicitamente richiesta.</span><span class="sxs-lookup"><span data-stu-id="c44fd-120">This request implicitly refuses all other permissions not specifically requested.</span></span> <span data-ttu-id="c44fd-121">Questa azione può essere usata solo nell'ambito dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="c44fd-121">This action can only be used within the scope of the assembly.</span></span>|  
|`dclRequestRefuse`|<span data-ttu-id="c44fd-122">La richiesta del chiamante per le autorizzazioni che potrebbero essere impiegate in uso non verrà concessa.</span><span class="sxs-lookup"><span data-stu-id="c44fd-122">The caller's request for permissions that might be misused will not be granted.</span></span> <span data-ttu-id="c44fd-123">Questa azione può essere usata solo nell'ambito dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="c44fd-123">This action can only be used within the scope of the assembly.</span></span>|  
|`dclPrejitGrant`|<span data-ttu-id="c44fd-124">Riservato.</span><span class="sxs-lookup"><span data-stu-id="c44fd-124">Reserved.</span></span>|  
|`dclPrejitDenied`|<span data-ttu-id="c44fd-125">Riservato.</span><span class="sxs-lookup"><span data-stu-id="c44fd-125">Reserved.</span></span>|  
|`dclNonCasDemand`|<span data-ttu-id="c44fd-126">Riservato.</span><span class="sxs-lookup"><span data-stu-id="c44fd-126">Reserved.</span></span>|  
|`dclNonCasLinkDemand`|<span data-ttu-id="c44fd-127">È necessario concedere al chiamante diretto l'autorizzazione specificata.</span><span class="sxs-lookup"><span data-stu-id="c44fd-127">The immediate caller is required to have been granted the specified permission.</span></span>|  
|`dclNonCasInheritance`|<span data-ttu-id="c44fd-128">Riservato.</span><span class="sxs-lookup"><span data-stu-id="c44fd-128">Reserved.</span></span>|  
|`dclLinkDemandChoice`|<span data-ttu-id="c44fd-129">Riservato.</span><span class="sxs-lookup"><span data-stu-id="c44fd-129">Reserved.</span></span>|  
|`dclInheritanceDemandChoice`|<span data-ttu-id="c44fd-130">Riservato.</span><span class="sxs-lookup"><span data-stu-id="c44fd-130">Reserved.</span></span>|  
|`dclDemandChoice`|<span data-ttu-id="c44fd-131">Riservato.</span><span class="sxs-lookup"><span data-stu-id="c44fd-131">Reserved.</span></span>|  
|`dclMaximumValue`|<span data-ttu-id="c44fd-132">Riservato.</span><span class="sxs-lookup"><span data-stu-id="c44fd-132">Reserved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c44fd-133">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c44fd-133">Requirements</span></span>  
 <span data-ttu-id="c44fd-134">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c44fd-134">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c44fd-135">**Intestazione:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="c44fd-135">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="c44fd-136">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c44fd-136">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c44fd-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c44fd-137">See also</span></span>

- [<span data-ttu-id="c44fd-138">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="c44fd-138">Metadata Enumerations</span></span>](metadata-enumerations.md)
