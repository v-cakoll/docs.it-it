---
title: ServiceSecurityAuditBehavior
ms.date: 03/30/2017
ms.assetid: 2c5809e7-5364-44ce-bc71-848be4672e2a
ms.openlocfilehash: 30679e1f67c6943bf674a6bbd8bf12be090765a8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2019
ms.locfileid: "59979134"
---
# <a name="servicesecurityauditbehavior"></a><span data-ttu-id="c16b1-102">ServiceSecurityAuditBehavior</span><span class="sxs-lookup"><span data-stu-id="c16b1-102">ServiceSecurityAuditBehavior</span></span>
<span data-ttu-id="c16b1-103">ServiceSecurityAuditBehavior</span><span class="sxs-lookup"><span data-stu-id="c16b1-103">ServiceSecurityAuditBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c16b1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c16b1-104">Syntax</span></span>  
  
```csharp  
class ServiceSecurityAuditBehavior : Behavior  
{  
  string AuditLogLocation;  
  string MessageAuthenticationAuditLevel;  
  string ServiceAuthorizationAuditLevel;  
  boolean SuppressAuditFailure;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="c16b1-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="c16b1-105">Methods</span></span>  
 <span data-ttu-id="c16b1-106">La classe ServiceSecurityAuditBehavior non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="c16b1-106">The ServiceSecurityAuditBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="c16b1-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="c16b1-107">Properties</span></span>  
 <span data-ttu-id="c16b1-108">La classe ServiceSecurityAuditBehavior dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="c16b1-108">The ServiceSecurityAuditBehavior class has the following properties:</span></span>  
  
### <a name="auditloglocation"></a><span data-ttu-id="c16b1-109">AuditLogLocation</span><span class="sxs-lookup"><span data-stu-id="c16b1-109">AuditLogLocation</span></span>  
 <span data-ttu-id="c16b1-110">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="c16b1-110">Data type: string</span></span>  
  
 <span data-ttu-id="c16b1-111">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="c16b1-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c16b1-112">Percorso del registro di controllo.</span><span class="sxs-lookup"><span data-stu-id="c16b1-112">The location of the audit log.</span></span>  
  
### <a name="messageauthenticationauditlevel"></a><span data-ttu-id="c16b1-113">MessageAuthenticationAuditLevel</span><span class="sxs-lookup"><span data-stu-id="c16b1-113">MessageAuthenticationAuditLevel</span></span>  
 <span data-ttu-id="c16b1-114">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="c16b1-114">Data type: string</span></span>  
  
 <span data-ttu-id="c16b1-115">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="c16b1-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c16b1-116">Tipo di livello di autenticazione dei messaggi utilizzato per registrare eventi di controllo.</span><span class="sxs-lookup"><span data-stu-id="c16b1-116">The type of message authentication level that is used to log audit events.</span></span>  
  
### <a name="serviceauthorizationauditlevel"></a><span data-ttu-id="c16b1-117">ServiceAuthorizationAuditLevel</span><span class="sxs-lookup"><span data-stu-id="c16b1-117">ServiceAuthorizationAuditLevel</span></span>  
 <span data-ttu-id="c16b1-118">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="c16b1-118">Data type: string</span></span>  
  
 <span data-ttu-id="c16b1-119">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="c16b1-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c16b1-120">Tipi di eventi di autorizzazione registrati nel registro di controllo.</span><span class="sxs-lookup"><span data-stu-id="c16b1-120">The types of authorization events that are recorded in the audit log.</span></span>  
  
### <a name="suppressauditfailure"></a><span data-ttu-id="c16b1-121">SuppressAuditFailure</span><span class="sxs-lookup"><span data-stu-id="c16b1-121">SuppressAuditFailure</span></span>  
 <span data-ttu-id="c16b1-122">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="c16b1-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="c16b1-123">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="c16b1-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c16b1-124">Valore booleano che specifica il comportamento per l'eliminazione di errori di scrittura nel registro di controllo.</span><span class="sxs-lookup"><span data-stu-id="c16b1-124">A boolean value that specifies the behavior for suppressing failures of writing to the audit log.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c16b1-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c16b1-125">Requirements</span></span>  
  
|<span data-ttu-id="c16b1-126">MOF</span><span class="sxs-lookup"><span data-stu-id="c16b1-126">MOF</span></span>|<span data-ttu-id="c16b1-127">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="c16b1-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="c16b1-128">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="c16b1-128">Namespace</span></span>|<span data-ttu-id="c16b1-129">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="c16b1-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c16b1-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c16b1-130">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>
