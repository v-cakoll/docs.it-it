---
title: ServiceAuthorizationBehavior
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 77dad8e8-fea4-4d1c-b366-2f01a2a87f78
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: fd22cd7e7783a67e7ad10371533eee680bd3af16
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="serviceauthorizationbehavior"></a><span data-ttu-id="064c2-102">ServiceAuthorizationBehavior</span><span class="sxs-lookup"><span data-stu-id="064c2-102">ServiceAuthorizationBehavior</span></span>
<span data-ttu-id="064c2-103">ServiceAuthorizationBehavior</span><span class="sxs-lookup"><span data-stu-id="064c2-103">ServiceAuthorizationBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="064c2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="064c2-104">Syntax</span></span>  
  
```  
class ServiceAuthorizationBehavior : Behavior  
{  
  boolean ImpersonateCallerForAllOperations;  
  string PrincipalPermissionMode;  
  string RoleProvider;  
  string ServiceAuthorizationManager;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="064c2-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="064c2-105">Methods</span></span>  
 <span data-ttu-id="064c2-106">La classe ServiceAuthorizationBehavior non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="064c2-106">The ServiceAuthorizationBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="064c2-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="064c2-107">Properties</span></span>  
 <span data-ttu-id="064c2-108">La classe ServiceAuthorizationBehavior dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="064c2-108">The ServiceAuthorizationBehavior class has the following properties:</span></span>  
  
### <a name="impersonatecallerforalloperations"></a><span data-ttu-id="064c2-109">ImpersonateCallerForAllOperations</span><span class="sxs-lookup"><span data-stu-id="064c2-109">ImpersonateCallerForAllOperations</span></span>  
 <span data-ttu-id="064c2-110">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="064c2-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="064c2-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="064c2-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="064c2-112">Valore che controlla se il servizio tenta di eseguire una rappresentazione utilizzando le credenziali fornite dal messaggio in ingresso.</span><span class="sxs-lookup"><span data-stu-id="064c2-112">A value that controls whether the service attempts to impersonate using the credentials provided by the incoming message.</span></span>  
  
### <a name="principalpermissionmode"></a><span data-ttu-id="064c2-113">PrincipalPermissionMode</span><span class="sxs-lookup"><span data-stu-id="064c2-113">PrincipalPermissionMode</span></span>  
 <span data-ttu-id="064c2-114">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="064c2-114">Data type: string</span></span>  
  
 <span data-ttu-id="064c2-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="064c2-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="064c2-116">Entità di protezione utilizzata per eseguire operazioni nel server.</span><span class="sxs-lookup"><span data-stu-id="064c2-116">The principal used to carry out operations on the server.</span></span>  
  
### <a name="roleprovider"></a><span data-ttu-id="064c2-117">RoleProvider</span><span class="sxs-lookup"><span data-stu-id="064c2-117">RoleProvider</span></span>  
 <span data-ttu-id="064c2-118">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="064c2-118">Data type: string</span></span>  
  
 <span data-ttu-id="064c2-119">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="064c2-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="064c2-120">Nome del provider del ruolo ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="064c2-120">The name of the ASP.NET role provider.</span></span>  
  
### <a name="serviceauthorizationmanager"></a><span data-ttu-id="064c2-121">ServiceAuthorizationManager</span><span class="sxs-lookup"><span data-stu-id="064c2-121">ServiceAuthorizationManager</span></span>  
 <span data-ttu-id="064c2-122">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="064c2-122">Data type: string</span></span>  
  
 <span data-ttu-id="064c2-123">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="064c2-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="064c2-124">Gestore autorizzazioni utilizzato per l'autorizzazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="064c2-124">The authorization manager used for custom authorization.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="064c2-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="064c2-125">Requirements</span></span>  
  
|<span data-ttu-id="064c2-126">MOF</span><span class="sxs-lookup"><span data-stu-id="064c2-126">MOF</span></span>|<span data-ttu-id="064c2-127">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="064c2-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="064c2-128">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="064c2-128">Namespace</span></span>|<span data-ttu-id="064c2-129">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="064c2-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="064c2-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="064c2-130">See Also</span></span>  
 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
