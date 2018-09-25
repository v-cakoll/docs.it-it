---
title: ServiceSecurityAuditBehavior
ms.date: 03/30/2017
ms.assetid: 2c5809e7-5364-44ce-bc71-848be4672e2a
author: BrucePerlerMS
ms.openlocfilehash: 8f43ee752830d95db6bbbdbe311b6d77735e31b5
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2018
ms.locfileid: "47070149"
---
# <a name="servicesecurityauditbehavior"></a><span data-ttu-id="87e00-102">ServiceSecurityAuditBehavior</span><span class="sxs-lookup"><span data-stu-id="87e00-102">ServiceSecurityAuditBehavior</span></span>
<span data-ttu-id="87e00-103">ServiceSecurityAuditBehavior</span><span class="sxs-lookup"><span data-stu-id="87e00-103">ServiceSecurityAuditBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87e00-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="87e00-104">Syntax</span></span>  
  
```  
class ServiceSecurityAuditBehavior : Behavior  
{  
  string AuditLogLocation;  
  string MessageAuthenticationAuditLevel;  
  string ServiceAuthorizationAuditLevel;  
  boolean SuppressAuditFailure;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="87e00-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="87e00-105">Methods</span></span>  
 <span data-ttu-id="87e00-106">La classe ServiceSecurityAuditBehavior non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="87e00-106">The ServiceSecurityAuditBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="87e00-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="87e00-107">Properties</span></span>  
 <span data-ttu-id="87e00-108">La classe ServiceSecurityAuditBehavior dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="87e00-108">The ServiceSecurityAuditBehavior class has the following properties:</span></span>  
  
### <a name="auditloglocation"></a><span data-ttu-id="87e00-109">AuditLogLocation</span><span class="sxs-lookup"><span data-stu-id="87e00-109">AuditLogLocation</span></span>  
 <span data-ttu-id="87e00-110">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="87e00-110">Data type: string</span></span>  
  
 <span data-ttu-id="87e00-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="87e00-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="87e00-112">Percorso del registro di controllo.</span><span class="sxs-lookup"><span data-stu-id="87e00-112">The location of the audit log.</span></span>  
  
### <a name="messageauthenticationauditlevel"></a><span data-ttu-id="87e00-113">MessageAuthenticationAuditLevel</span><span class="sxs-lookup"><span data-stu-id="87e00-113">MessageAuthenticationAuditLevel</span></span>  
 <span data-ttu-id="87e00-114">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="87e00-114">Data type: string</span></span>  
  
 <span data-ttu-id="87e00-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="87e00-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="87e00-116">Tipo di livello di autenticazione dei messaggi utilizzato per registrare eventi di controllo.</span><span class="sxs-lookup"><span data-stu-id="87e00-116">The type of message authentication level that is used to log audit events.</span></span>  
  
### <a name="serviceauthorizationauditlevel"></a><span data-ttu-id="87e00-117">ServiceAuthorizationAuditLevel</span><span class="sxs-lookup"><span data-stu-id="87e00-117">ServiceAuthorizationAuditLevel</span></span>  
 <span data-ttu-id="87e00-118">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="87e00-118">Data type: string</span></span>  
  
 <span data-ttu-id="87e00-119">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="87e00-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="87e00-120">Tipi di eventi di autorizzazione registrati nel registro di controllo.</span><span class="sxs-lookup"><span data-stu-id="87e00-120">The types of authorization events that are recorded in the audit log.</span></span>  
  
### <a name="suppressauditfailure"></a><span data-ttu-id="87e00-121">SuppressAuditFailure</span><span class="sxs-lookup"><span data-stu-id="87e00-121">SuppressAuditFailure</span></span>  
 <span data-ttu-id="87e00-122">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="87e00-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="87e00-123">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="87e00-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="87e00-124">Valore booleano che specifica il comportamento per l'eliminazione di errori di scrittura nel registro di controllo.</span><span class="sxs-lookup"><span data-stu-id="87e00-124">A boolean value that specifies the behavior for suppressing failures of writing to the audit log.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="87e00-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="87e00-125">Requirements</span></span>  
  
|<span data-ttu-id="87e00-126">MOF</span><span class="sxs-lookup"><span data-stu-id="87e00-126">MOF</span></span>|<span data-ttu-id="87e00-127">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="87e00-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="87e00-128">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="87e00-128">Namespace</span></span>|<span data-ttu-id="87e00-129">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="87e00-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="87e00-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="87e00-130">See Also</span></span>  
 <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>
