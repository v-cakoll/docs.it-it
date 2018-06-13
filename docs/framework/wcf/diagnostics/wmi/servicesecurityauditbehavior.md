---
title: ServiceSecurityAuditBehavior
ms.date: 03/30/2017
ms.assetid: 2c5809e7-5364-44ce-bc71-848be4672e2a
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 3adc721dd8ad0fb706e172373e5da70fe6032db6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33485895"
---
# <a name="servicesecurityauditbehavior"></a><span data-ttu-id="ae869-102">ServiceSecurityAuditBehavior</span><span class="sxs-lookup"><span data-stu-id="ae869-102">ServiceSecurityAuditBehavior</span></span>
<span data-ttu-id="ae869-103">ServiceSecurityAuditBehavior</span><span class="sxs-lookup"><span data-stu-id="ae869-103">ServiceSecurityAuditBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae869-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ae869-104">Syntax</span></span>  
  
```  
class ServiceSecurityAuditBehavior : Behavior  
{  
  string AuditLogLocation;  
  string MessageAuthenticationAuditLevel;  
  string ServiceAuthorizationAuditLevel;  
  boolean SuppressAuditFailure;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="ae869-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="ae869-105">Methods</span></span>  
 <span data-ttu-id="ae869-106">La classe ServiceSecurityAuditBehavior non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="ae869-106">The ServiceSecurityAuditBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="ae869-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="ae869-107">Properties</span></span>  
 <span data-ttu-id="ae869-108">La classe ServiceSecurityAuditBehavior dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="ae869-108">The ServiceSecurityAuditBehavior class has the following properties:</span></span>  
  
### <a name="auditloglocation"></a><span data-ttu-id="ae869-109">AuditLogLocation</span><span class="sxs-lookup"><span data-stu-id="ae869-109">AuditLogLocation</span></span>  
 <span data-ttu-id="ae869-110">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="ae869-110">Data type: string</span></span>  
  
 <span data-ttu-id="ae869-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="ae869-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ae869-112">Percorso del registro di controllo.</span><span class="sxs-lookup"><span data-stu-id="ae869-112">The location of the audit log.</span></span>  
  
### <a name="messageauthenticationauditlevel"></a><span data-ttu-id="ae869-113">MessageAuthenticationAuditLevel</span><span class="sxs-lookup"><span data-stu-id="ae869-113">MessageAuthenticationAuditLevel</span></span>  
 <span data-ttu-id="ae869-114">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="ae869-114">Data type: string</span></span>  
  
 <span data-ttu-id="ae869-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="ae869-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ae869-116">Tipo di livello di autenticazione dei messaggi utilizzato per registrare eventi di controllo.</span><span class="sxs-lookup"><span data-stu-id="ae869-116">The type of message authentication level that is used to log audit events.</span></span>  
  
### <a name="serviceauthorizationauditlevel"></a><span data-ttu-id="ae869-117">ServiceAuthorizationAuditLevel</span><span class="sxs-lookup"><span data-stu-id="ae869-117">ServiceAuthorizationAuditLevel</span></span>  
 <span data-ttu-id="ae869-118">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="ae869-118">Data type: string</span></span>  
  
 <span data-ttu-id="ae869-119">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="ae869-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ae869-120">Tipi di eventi di autorizzazione registrati nel registro di controllo.</span><span class="sxs-lookup"><span data-stu-id="ae869-120">The types of authorization events that are recorded in the audit log.</span></span>  
  
### <a name="suppressauditfailure"></a><span data-ttu-id="ae869-121">SuppressAuditFailure</span><span class="sxs-lookup"><span data-stu-id="ae869-121">SuppressAuditFailure</span></span>  
 <span data-ttu-id="ae869-122">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="ae869-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="ae869-123">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="ae869-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ae869-124">Valore booleano che specifica il comportamento per l'eliminazione di errori di scrittura nel registro di controllo.</span><span class="sxs-lookup"><span data-stu-id="ae869-124">A boolean value that specifies the behavior for suppressing failures of writing to the audit log.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae869-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ae869-125">Requirements</span></span>  
  
|<span data-ttu-id="ae869-126">MOF</span><span class="sxs-lookup"><span data-stu-id="ae869-126">MOF</span></span>|<span data-ttu-id="ae869-127">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="ae869-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="ae869-128">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="ae869-128">Namespace</span></span>|<span data-ttu-id="ae869-129">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="ae869-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ae869-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ae869-130">See Also</span></span>  
 <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>
