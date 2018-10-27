---
title: ServiceAuthorizationBehavior
ms.date: 03/30/2017
ms.assetid: 77dad8e8-fea4-4d1c-b366-2f01a2a87f78
ms.openlocfilehash: c916d0820a1eae333384deab7b0619abfbdc8167
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/26/2018
ms.locfileid: "49415380"
---
# <a name="serviceauthorizationbehavior"></a><span data-ttu-id="0f52a-102">ServiceAuthorizationBehavior</span><span class="sxs-lookup"><span data-stu-id="0f52a-102">ServiceAuthorizationBehavior</span></span>
<span data-ttu-id="0f52a-103">ServiceAuthorizationBehavior</span><span class="sxs-lookup"><span data-stu-id="0f52a-103">ServiceAuthorizationBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f52a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0f52a-104">Syntax</span></span>  
  
```csharp
class ServiceAuthorizationBehavior : Behavior  
{  
  boolean ImpersonateCallerForAllOperations;  
  string PrincipalPermissionMode;  
  string RoleProvider;  
  string ServiceAuthorizationManager;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="0f52a-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="0f52a-105">Methods</span></span>  
 <span data-ttu-id="0f52a-106">La classe ServiceAuthorizationBehavior non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="0f52a-106">The ServiceAuthorizationBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="0f52a-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="0f52a-107">Properties</span></span>  
 <span data-ttu-id="0f52a-108">La classe ServiceAuthorizationBehavior dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="0f52a-108">The ServiceAuthorizationBehavior class has the following properties:</span></span>  
  
### <a name="impersonatecallerforalloperations"></a><span data-ttu-id="0f52a-109">ImpersonateCallerForAllOperations</span><span class="sxs-lookup"><span data-stu-id="0f52a-109">ImpersonateCallerForAllOperations</span></span>  
 <span data-ttu-id="0f52a-110">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="0f52a-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="0f52a-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="0f52a-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0f52a-112">Valore che controlla se il servizio tenta di eseguire una rappresentazione utilizzando le credenziali fornite dal messaggio in ingresso.</span><span class="sxs-lookup"><span data-stu-id="0f52a-112">A value that controls whether the service attempts to impersonate using the credentials provided by the incoming message.</span></span>  
  
### <a name="principalpermissionmode"></a><span data-ttu-id="0f52a-113">PrincipalPermissionMode</span><span class="sxs-lookup"><span data-stu-id="0f52a-113">PrincipalPermissionMode</span></span>  
 <span data-ttu-id="0f52a-114">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="0f52a-114">Data type: string</span></span>  
  
 <span data-ttu-id="0f52a-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="0f52a-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0f52a-116">Entità di protezione utilizzata per eseguire operazioni nel server.</span><span class="sxs-lookup"><span data-stu-id="0f52a-116">The principal used to carry out operations on the server.</span></span>  
  
### <a name="roleprovider"></a><span data-ttu-id="0f52a-117">RoleProvider</span><span class="sxs-lookup"><span data-stu-id="0f52a-117">RoleProvider</span></span>  
 <span data-ttu-id="0f52a-118">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="0f52a-118">Data type: string</span></span>  
  
 <span data-ttu-id="0f52a-119">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="0f52a-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0f52a-120">Nome del provider del ruolo ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="0f52a-120">The name of the ASP.NET role provider.</span></span>  
  
### <a name="serviceauthorizationmanager"></a><span data-ttu-id="0f52a-121">ServiceAuthorizationManager</span><span class="sxs-lookup"><span data-stu-id="0f52a-121">ServiceAuthorizationManager</span></span>  
 <span data-ttu-id="0f52a-122">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="0f52a-122">Data type: string</span></span>  
  
 <span data-ttu-id="0f52a-123">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="0f52a-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0f52a-124">Gestore autorizzazioni utilizzato per l'autorizzazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="0f52a-124">The authorization manager used for custom authorization.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f52a-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0f52a-125">Requirements</span></span>  
  
|<span data-ttu-id="0f52a-126">MOF</span><span class="sxs-lookup"><span data-stu-id="0f52a-126">MOF</span></span>|<span data-ttu-id="0f52a-127">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="0f52a-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="0f52a-128">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="0f52a-128">Namespace</span></span>|<span data-ttu-id="0f52a-129">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="0f52a-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0f52a-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0f52a-130">See Also</span></span>  
 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
