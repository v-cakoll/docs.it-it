---
title: ServiceCredentials
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9c780793-4785-46f7-add9-ac1ebeadb614
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 73fad36b5bf14745ca70d297fa988b90d46990df
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="servicecredentials"></a><span data-ttu-id="d94f7-102">ServiceCredentials</span><span class="sxs-lookup"><span data-stu-id="d94f7-102">ServiceCredentials</span></span>
<span data-ttu-id="d94f7-103">ServiceCredentials</span><span class="sxs-lookup"><span data-stu-id="d94f7-103">ServiceCredentials</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d94f7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d94f7-104">Syntax</span></span>  
  
```  
class ServiceCredentials : Behavior  
{  
  string ClientCertificate;  
  string IssuedTokenAuthentication;  
  string Peer;  
  string SecureConversationAuthentication;  
  string ServiceCertificate;  
  string UserNameAuthentication;  
  string WindowsAuthentication;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="d94f7-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="d94f7-105">Methods</span></span>  
 <span data-ttu-id="d94f7-106">La classe ServiceCredentials non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="d94f7-106">The ServiceCredentials class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="d94f7-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="d94f7-107">Properties</span></span>  
 <span data-ttu-id="d94f7-108">La classe ServiceCredentials dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="d94f7-108">The ServiceCredentials class has the following properties:</span></span>  
  
### <a name="clientcertificate"></a><span data-ttu-id="d94f7-109">ClientCertificate</span><span class="sxs-lookup"><span data-stu-id="d94f7-109">ClientCertificate</span></span>  
 <span data-ttu-id="d94f7-110">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="d94f7-110">Data type: string</span></span>  
  
 <span data-ttu-id="d94f7-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="d94f7-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d94f7-112">Impostazioni di provisioning e autenticazione dei certificati client per il servizio.</span><span class="sxs-lookup"><span data-stu-id="d94f7-112">The client certificate authentication and provisioning settings for this service.</span></span>  
  
### <a name="issuedtokenauthentication"></a><span data-ttu-id="d94f7-113">IssuedTokenAuthentication</span><span class="sxs-lookup"><span data-stu-id="d94f7-113">IssuedTokenAuthentication</span></span>  
 <span data-ttu-id="d94f7-114">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="d94f7-114">Data type: string</span></span>  
  
 <span data-ttu-id="d94f7-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="d94f7-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d94f7-116">Impostazioni correnti di autenticazione del token rilasciato per il servizio.</span><span class="sxs-lookup"><span data-stu-id="d94f7-116">The current issued token authentication settings for this service.</span></span>  
  
### <a name="peer"></a><span data-ttu-id="d94f7-117">Peer</span><span class="sxs-lookup"><span data-stu-id="d94f7-117">Peer</span></span>  
 <span data-ttu-id="d94f7-118">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="d94f7-118">Data type: string</span></span>  
  
 <span data-ttu-id="d94f7-119">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="d94f7-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d94f7-120">Impostazioni correnti di provisioning e autenticazione delle credenziali utilizzate dagli endpoint di trasporto del peer.</span><span class="sxs-lookup"><span data-stu-id="d94f7-120">The current credential authentication and provisioning settings to be used by peer transport endpoints.</span></span>  
  
### <a name="secureconversationauthentication"></a><span data-ttu-id="d94f7-121">SecureConversationAuthentication</span><span class="sxs-lookup"><span data-stu-id="d94f7-121">SecureConversationAuthentication</span></span>  
 <span data-ttu-id="d94f7-122">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="d94f7-122">Data type: string</span></span>  
  
 <span data-ttu-id="d94f7-123">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="d94f7-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d94f7-124">Specifica le impostazioni correnti per le conversazioni protette.</span><span class="sxs-lookup"><span data-stu-id="d94f7-124">Specifies the current secure conversation settings.</span></span>  
  
### <a name="servicecertificate"></a><span data-ttu-id="d94f7-125">ServiceCertificate</span><span class="sxs-lookup"><span data-stu-id="d94f7-125">ServiceCertificate</span></span>  
 <span data-ttu-id="d94f7-126">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="d94f7-126">Data type: string</span></span>  
  
 <span data-ttu-id="d94f7-127">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="d94f7-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d94f7-128">Certificato associato al servizio.</span><span class="sxs-lookup"><span data-stu-id="d94f7-128">The certificate associated with this service.</span></span>  
  
### <a name="usernameauthentication"></a><span data-ttu-id="d94f7-129">UserNameAuthentication</span><span class="sxs-lookup"><span data-stu-id="d94f7-129">UserNameAuthentication</span></span>  
 <span data-ttu-id="d94f7-130">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="d94f7-130">Data type: string</span></span>  
  
 <span data-ttu-id="d94f7-131">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="d94f7-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d94f7-132">Impostazioni di nome utente e password per il servizio.</span><span class="sxs-lookup"><span data-stu-id="d94f7-132">The username/password settings for this service.</span></span>  
  
### <a name="windowsauthentication"></a><span data-ttu-id="d94f7-133">WindowsAuthentication</span><span class="sxs-lookup"><span data-stu-id="d94f7-133">WindowsAuthentication</span></span>  
 <span data-ttu-id="d94f7-134">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="d94f7-134">Data type: string</span></span>  
  
 <span data-ttu-id="d94f7-135">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="d94f7-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d94f7-136">Impostazioni di autenticazione Windows per il servizio.</span><span class="sxs-lookup"><span data-stu-id="d94f7-136">The Windows authentication settings for this service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d94f7-137">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d94f7-137">Requirements</span></span>  
  
|<span data-ttu-id="d94f7-138">MOF</span><span class="sxs-lookup"><span data-stu-id="d94f7-138">MOF</span></span>|<span data-ttu-id="d94f7-139">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="d94f7-139">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="d94f7-140">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="d94f7-140">Namespace</span></span>|<span data-ttu-id="d94f7-141">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="d94f7-141">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d94f7-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d94f7-142">See Also</span></span>  
 <xref:System.ServiceModel.Description.ServiceCredentials>
