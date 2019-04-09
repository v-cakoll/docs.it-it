---
title: ServiceSecurityAuditBehavior
ms.date: 03/30/2017
ms.assetid: 2c5809e7-5364-44ce-bc71-848be4672e2a
ms.openlocfilehash: 30679e1f67c6943bf674a6bbd8bf12be090765a8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59203509"
---
# <a name="servicesecurityauditbehavior"></a><span data-ttu-id="75abe-102">ServiceSecurityAuditBehavior</span><span class="sxs-lookup"><span data-stu-id="75abe-102">ServiceSecurityAuditBehavior</span></span>
<span data-ttu-id="75abe-103">ServiceSecurityAuditBehavior</span><span class="sxs-lookup"><span data-stu-id="75abe-103">ServiceSecurityAuditBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75abe-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="75abe-104">Syntax</span></span>  
  
```csharp  
class ServiceSecurityAuditBehavior : Behavior  
{  
  string AuditLogLocation;  
  string MessageAuthenticationAuditLevel;  
  string ServiceAuthorizationAuditLevel;  
  boolean SuppressAuditFailure;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="75abe-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="75abe-105">Methods</span></span>  
 <span data-ttu-id="75abe-106">La classe ServiceSecurityAuditBehavior non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="75abe-106">The ServiceSecurityAuditBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="75abe-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="75abe-107">Properties</span></span>  
 <span data-ttu-id="75abe-108">La classe ServiceSecurityAuditBehavior dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="75abe-108">The ServiceSecurityAuditBehavior class has the following properties:</span></span>  
  
### <a name="auditloglocation"></a><span data-ttu-id="75abe-109">AuditLogLocation</span><span class="sxs-lookup"><span data-stu-id="75abe-109">AuditLogLocation</span></span>  
 <span data-ttu-id="75abe-110">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="75abe-110">Data type: string</span></span>  
  
 <span data-ttu-id="75abe-111">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="75abe-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="75abe-112">Percorso del registro di controllo.</span><span class="sxs-lookup"><span data-stu-id="75abe-112">The location of the audit log.</span></span>  
  
### <a name="messageauthenticationauditlevel"></a><span data-ttu-id="75abe-113">MessageAuthenticationAuditLevel</span><span class="sxs-lookup"><span data-stu-id="75abe-113">MessageAuthenticationAuditLevel</span></span>  
 <span data-ttu-id="75abe-114">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="75abe-114">Data type: string</span></span>  
  
 <span data-ttu-id="75abe-115">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="75abe-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="75abe-116">Tipo di livello di autenticazione dei messaggi utilizzato per registrare eventi di controllo.</span><span class="sxs-lookup"><span data-stu-id="75abe-116">The type of message authentication level that is used to log audit events.</span></span>  
  
### <a name="serviceauthorizationauditlevel"></a><span data-ttu-id="75abe-117">ServiceAuthorizationAuditLevel</span><span class="sxs-lookup"><span data-stu-id="75abe-117">ServiceAuthorizationAuditLevel</span></span>  
 <span data-ttu-id="75abe-118">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="75abe-118">Data type: string</span></span>  
  
 <span data-ttu-id="75abe-119">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="75abe-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="75abe-120">Tipi di eventi di autorizzazione registrati nel registro di controllo.</span><span class="sxs-lookup"><span data-stu-id="75abe-120">The types of authorization events that are recorded in the audit log.</span></span>  
  
### <a name="suppressauditfailure"></a><span data-ttu-id="75abe-121">SuppressAuditFailure</span><span class="sxs-lookup"><span data-stu-id="75abe-121">SuppressAuditFailure</span></span>  
 <span data-ttu-id="75abe-122">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="75abe-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="75abe-123">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="75abe-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="75abe-124">Valore booleano che specifica il comportamento per l'eliminazione di errori di scrittura nel registro di controllo.</span><span class="sxs-lookup"><span data-stu-id="75abe-124">A boolean value that specifies the behavior for suppressing failures of writing to the audit log.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="75abe-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="75abe-125">Requirements</span></span>  
  
|<span data-ttu-id="75abe-126">MOF</span><span class="sxs-lookup"><span data-stu-id="75abe-126">MOF</span></span>|<span data-ttu-id="75abe-127">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="75abe-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="75abe-128">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="75abe-128">Namespace</span></span>|<span data-ttu-id="75abe-129">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="75abe-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="75abe-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="75abe-130">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>
