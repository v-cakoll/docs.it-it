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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 47819740207ae94b814b3009708c2fd247688661
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54564005"
---
# <a name="cordeclsecurity-enumeration"></a><span data-ttu-id="3fa3e-102">Enumerazione CorDeclSecurity</span><span class="sxs-lookup"><span data-stu-id="3fa3e-102">CorDeclSecurity Enumeration</span></span>
<span data-ttu-id="3fa3e-103">Specifica le azioni relative alla sicurezza che possono essere eseguite con la sicurezza dichiarativa.</span><span class="sxs-lookup"><span data-stu-id="3fa3e-103">Specifies the security actions that can be performed using declarative security.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3fa3e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3fa3e-104">Syntax</span></span>  
  
```  
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
  
## <a name="members"></a><span data-ttu-id="3fa3e-105">Membri</span><span class="sxs-lookup"><span data-stu-id="3fa3e-105">Members</span></span>  
  
|<span data-ttu-id="3fa3e-106">Membro</span><span class="sxs-lookup"><span data-stu-id="3fa3e-106">Member</span></span>|<span data-ttu-id="3fa3e-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3fa3e-107">Description</span></span>|  
|------------|-----------------|  
|`dclActionMask`|<span data-ttu-id="3fa3e-108">Riservato.</span><span class="sxs-lookup"><span data-stu-id="3fa3e-108">Reserved.</span></span>|  
|`dclActionNil`|<span data-ttu-id="3fa3e-109">Riservato.</span><span class="sxs-lookup"><span data-stu-id="3fa3e-109">Reserved.</span></span>|  
|`dclRequest`|<span data-ttu-id="3fa3e-110">Riservato.</span><span class="sxs-lookup"><span data-stu-id="3fa3e-110">Reserved.</span></span>|  
|`dclDemand`|<span data-ttu-id="3fa3e-111">A tutti i chiamanti nella parte superiore dello stack di chiamate deve essere concessa l'autorizzazione specificata dall'oggetto di autorizzazione corrente.</span><span class="sxs-lookup"><span data-stu-id="3fa3e-111">All callers higher in the call stack are required to have been granted the permission specified by the current permission object.</span></span>|  
|`dclAssert`|<span data-ttu-id="3fa3e-112">Il codice chiamante può accedere alla risorsa identificata dall'oggetto autorizzazioni corrente, anche se i primi chiamanti dello stack non sono state concesse autorizzazioni per accedere alla risorsa</span><span class="sxs-lookup"><span data-stu-id="3fa3e-112">The calling code can access the resource identified by the current permission object, even if callers higher in the stack have not been granted permission to access the resource</span></span>|  
|`dclDeny`|<span data-ttu-id="3fa3e-113">La possibilità di accedere alla risorsa specificata dall'oggetto autorizzazioni corrente viene negata ai chiamanti, anche se dispongono dell'autorizzazione per accedervi.</span><span class="sxs-lookup"><span data-stu-id="3fa3e-113">The ability to access the resource specified by the current permission object is denied to callers, even if they have been granted permission to access it.</span></span>|  
|`dclPermitOnly`|<span data-ttu-id="3fa3e-114">È possibile accedere solo alle risorse specificate dall'oggetto di autorizzazione, anche se al codice è stata concessa l'autorizzazione per accedere ad altre risorse.</span><span class="sxs-lookup"><span data-stu-id="3fa3e-114">Only the resources specified by this permission object can be accessed, even if the code has been granted permission to access other resources.</span></span>|  
|`dclLinktimeCheck`|<span data-ttu-id="3fa3e-115">Il chiamante immediato è necessario disporre sia concessa l'autorizzazione specificata per un determinato periodo di tempo.</span><span class="sxs-lookup"><span data-stu-id="3fa3e-115">The immediate caller is required to have been granted the specified permission for a given period of time.</span></span>|  
|`dclInheritanceCheck`|<span data-ttu-id="3fa3e-116">La classe derivata che eredita un'altra classe o l'override di un metodo è necessaria disporre dell'autorizzazione specificata.</span><span class="sxs-lookup"><span data-stu-id="3fa3e-116">The derived class inheriting another class or overriding a method is required to have been granted the specified permission.</span></span>|  
|`dclRequestMinimum`|<span data-ttu-id="3fa3e-117">Il chiamante può richiedere per le autorizzazioni minime necessarie per l'esecuzione di codice.</span><span class="sxs-lookup"><span data-stu-id="3fa3e-117">The caller can request for the minimum permissions required for code to run.</span></span> <span data-ttu-id="3fa3e-118">Questa azione può essere usata solo nell'ambito dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="3fa3e-118">This action can only be used within the scope of the assembly.</span></span>|  
|`dclRequestOptional`|<span data-ttu-id="3fa3e-119">Il chiamante può richiedere autorizzazioni aggiuntive che sono facoltative (non necessario per l'esecuzione).</span><span class="sxs-lookup"><span data-stu-id="3fa3e-119">The caller can request for additional permissions that are optional (not required to run).</span></span> <span data-ttu-id="3fa3e-120">Con questa richiesta viene implicitamente rifiutata ogni altra autorizzazione che non sia stata esplicitamente richiesta.</span><span class="sxs-lookup"><span data-stu-id="3fa3e-120">This request implicitly refuses all other permissions not specifically requested.</span></span> <span data-ttu-id="3fa3e-121">Questa azione può essere usata solo nell'ambito dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="3fa3e-121">This action can only be used within the scope of the assembly.</span></span>|  
|`dclRequestRefuse`|<span data-ttu-id="3fa3e-122">Non verrà concessa richiesta del chiamante per le autorizzazioni utilizzabili in modo improprio.</span><span class="sxs-lookup"><span data-stu-id="3fa3e-122">The caller's request for permissions that might be misused will not be granted.</span></span> <span data-ttu-id="3fa3e-123">Questa azione può essere usata solo nell'ambito dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="3fa3e-123">This action can only be used within the scope of the assembly.</span></span>|  
|`dclPrejitGrant`|<span data-ttu-id="3fa3e-124">Riservato.</span><span class="sxs-lookup"><span data-stu-id="3fa3e-124">Reserved.</span></span>|  
|`dclPrejitDenied`|<span data-ttu-id="3fa3e-125">Riservato.</span><span class="sxs-lookup"><span data-stu-id="3fa3e-125">Reserved.</span></span>|  
|`dclNonCasDemand`|<span data-ttu-id="3fa3e-126">Riservato.</span><span class="sxs-lookup"><span data-stu-id="3fa3e-126">Reserved.</span></span>|  
|`dclNonCasLinkDemand`|<span data-ttu-id="3fa3e-127">È necessario concedere al chiamante diretto l'autorizzazione specificata.</span><span class="sxs-lookup"><span data-stu-id="3fa3e-127">The immediate caller is required to have been granted the specified permission.</span></span>|  
|`dclNonCasInheritance`|<span data-ttu-id="3fa3e-128">Riservato.</span><span class="sxs-lookup"><span data-stu-id="3fa3e-128">Reserved.</span></span>|  
|`dclLinkDemandChoice`|<span data-ttu-id="3fa3e-129">Riservato.</span><span class="sxs-lookup"><span data-stu-id="3fa3e-129">Reserved.</span></span>|  
|`dclInheritanceDemandChoice`|<span data-ttu-id="3fa3e-130">Riservato.</span><span class="sxs-lookup"><span data-stu-id="3fa3e-130">Reserved.</span></span>|  
|`dclDemandChoice`|<span data-ttu-id="3fa3e-131">Riservato.</span><span class="sxs-lookup"><span data-stu-id="3fa3e-131">Reserved.</span></span>|  
|`dclMaximumValue`|<span data-ttu-id="3fa3e-132">Riservato.</span><span class="sxs-lookup"><span data-stu-id="3fa3e-132">Reserved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3fa3e-133">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3fa3e-133">Requirements</span></span>  
 <span data-ttu-id="3fa3e-134">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3fa3e-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3fa3e-135">**Intestazione:** CorHdr. H</span><span class="sxs-lookup"><span data-stu-id="3fa3e-135">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="3fa3e-136">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3fa3e-136">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fa3e-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3fa3e-137">See also</span></span>
- [<span data-ttu-id="3fa3e-138">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="3fa3e-138">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
