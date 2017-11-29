---
title: ServiceSecurityAuditBehavior
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2c5809e7-5364-44ce-bc71-848be4672e2a
caps.latest.revision: "8"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 1ce712bbdb258c477a2ee56f47281b1a1d09ec54
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="servicesecurityauditbehavior"></a><span data-ttu-id="29ffe-102">ServiceSecurityAuditBehavior</span><span class="sxs-lookup"><span data-stu-id="29ffe-102">ServiceSecurityAuditBehavior</span></span>
<span data-ttu-id="29ffe-103">ServiceSecurityAuditBehavior</span><span class="sxs-lookup"><span data-stu-id="29ffe-103">ServiceSecurityAuditBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29ffe-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="29ffe-104">Syntax</span></span>  
  
```  
class ServiceSecurityAuditBehavior : Behavior  
{  
  string AuditLogLocation;  
  string MessageAuthenticationAuditLevel;  
  string ServiceAuthorizationAuditLevel;  
  boolean SuppressAuditFailure;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="29ffe-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="29ffe-105">Methods</span></span>  
 <span data-ttu-id="29ffe-106">La classe ServiceSecurityAuditBehavior non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="29ffe-106">The ServiceSecurityAuditBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="29ffe-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="29ffe-107">Properties</span></span>  
 <span data-ttu-id="29ffe-108">La classe ServiceSecurityAuditBehavior dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="29ffe-108">The ServiceSecurityAuditBehavior class has the following properties:</span></span>  
  
### <a name="auditloglocation"></a><span data-ttu-id="29ffe-109">AuditLogLocation</span><span class="sxs-lookup"><span data-stu-id="29ffe-109">AuditLogLocation</span></span>  
 <span data-ttu-id="29ffe-110">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="29ffe-110">Data type: string</span></span>  
  
 <span data-ttu-id="29ffe-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="29ffe-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="29ffe-112">Percorso del registro di controllo.</span><span class="sxs-lookup"><span data-stu-id="29ffe-112">The location of the audit log.</span></span>  
  
### <a name="messageauthenticationauditlevel"></a><span data-ttu-id="29ffe-113">MessageAuthenticationAuditLevel</span><span class="sxs-lookup"><span data-stu-id="29ffe-113">MessageAuthenticationAuditLevel</span></span>  
 <span data-ttu-id="29ffe-114">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="29ffe-114">Data type: string</span></span>  
  
 <span data-ttu-id="29ffe-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="29ffe-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="29ffe-116">Tipo di livello di autenticazione dei messaggi utilizzato per registrare eventi di controllo.</span><span class="sxs-lookup"><span data-stu-id="29ffe-116">The type of message authentication level that is used to log audit events.</span></span>  
  
### <a name="serviceauthorizationauditlevel"></a><span data-ttu-id="29ffe-117">ServiceAuthorizationAuditLevel</span><span class="sxs-lookup"><span data-stu-id="29ffe-117">ServiceAuthorizationAuditLevel</span></span>  
 <span data-ttu-id="29ffe-118">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="29ffe-118">Data type: string</span></span>  
  
 <span data-ttu-id="29ffe-119">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="29ffe-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="29ffe-120">Tipi di eventi di autorizzazione registrati nel registro di controllo.</span><span class="sxs-lookup"><span data-stu-id="29ffe-120">The types of authorization events that are recorded in the audit log.</span></span>  
  
### <a name="suppressauditfailure"></a><span data-ttu-id="29ffe-121">SuppressAuditFailure</span><span class="sxs-lookup"><span data-stu-id="29ffe-121">SuppressAuditFailure</span></span>  
 <span data-ttu-id="29ffe-122">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="29ffe-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="29ffe-123">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="29ffe-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="29ffe-124">Valore booleano che specifica il comportamento per l'eliminazione di errori di scrittura nel registro di controllo.</span><span class="sxs-lookup"><span data-stu-id="29ffe-124">A boolean value that specifies the behavior for suppressing failures of writing to the audit log.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="29ffe-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="29ffe-125">Requirements</span></span>  
  
|<span data-ttu-id="29ffe-126">MOF</span><span class="sxs-lookup"><span data-stu-id="29ffe-126">MOF</span></span>|<span data-ttu-id="29ffe-127">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="29ffe-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="29ffe-128">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="29ffe-128">Namespace</span></span>|<span data-ttu-id="29ffe-129">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="29ffe-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="29ffe-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="29ffe-130">See Also</span></span>  
 <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>
