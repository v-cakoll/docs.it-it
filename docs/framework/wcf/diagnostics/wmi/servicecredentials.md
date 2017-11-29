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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: e4cc9d7d7d46157b7df202c6daffb31b90fa98c1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="servicecredentials"></a><span data-ttu-id="9497d-102">ServiceCredentials</span><span class="sxs-lookup"><span data-stu-id="9497d-102">ServiceCredentials</span></span>
<span data-ttu-id="9497d-103">ServiceCredentials</span><span class="sxs-lookup"><span data-stu-id="9497d-103">ServiceCredentials</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9497d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9497d-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="9497d-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="9497d-105">Methods</span></span>  
 <span data-ttu-id="9497d-106">La classe ServiceCredentials non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="9497d-106">The ServiceCredentials class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="9497d-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="9497d-107">Properties</span></span>  
 <span data-ttu-id="9497d-108">La classe ServiceCredentials dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="9497d-108">The ServiceCredentials class has the following properties:</span></span>  
  
### <a name="clientcertificate"></a><span data-ttu-id="9497d-109">ClientCertificate</span><span class="sxs-lookup"><span data-stu-id="9497d-109">ClientCertificate</span></span>  
 <span data-ttu-id="9497d-110">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="9497d-110">Data type: string</span></span>  
  
 <span data-ttu-id="9497d-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="9497d-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9497d-112">Impostazioni di provisioning e autenticazione dei certificati client per il servizio.</span><span class="sxs-lookup"><span data-stu-id="9497d-112">The client certificate authentication and provisioning settings for this service.</span></span>  
  
### <a name="issuedtokenauthentication"></a><span data-ttu-id="9497d-113">IssuedTokenAuthentication</span><span class="sxs-lookup"><span data-stu-id="9497d-113">IssuedTokenAuthentication</span></span>  
 <span data-ttu-id="9497d-114">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="9497d-114">Data type: string</span></span>  
  
 <span data-ttu-id="9497d-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="9497d-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9497d-116">Impostazioni correnti di autenticazione del token rilasciato per il servizio.</span><span class="sxs-lookup"><span data-stu-id="9497d-116">The current issued token authentication settings for this service.</span></span>  
  
### <a name="peer"></a><span data-ttu-id="9497d-117">Peer</span><span class="sxs-lookup"><span data-stu-id="9497d-117">Peer</span></span>  
 <span data-ttu-id="9497d-118">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="9497d-118">Data type: string</span></span>  
  
 <span data-ttu-id="9497d-119">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="9497d-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9497d-120">Impostazioni correnti di provisioning e autenticazione delle credenziali utilizzate dagli endpoint di trasporto del peer.</span><span class="sxs-lookup"><span data-stu-id="9497d-120">The current credential authentication and provisioning settings to be used by peer transport endpoints.</span></span>  
  
### <a name="secureconversationauthentication"></a><span data-ttu-id="9497d-121">SecureConversationAuthentication</span><span class="sxs-lookup"><span data-stu-id="9497d-121">SecureConversationAuthentication</span></span>  
 <span data-ttu-id="9497d-122">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="9497d-122">Data type: string</span></span>  
  
 <span data-ttu-id="9497d-123">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="9497d-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9497d-124">Specifica le impostazioni correnti per le conversazioni protette.</span><span class="sxs-lookup"><span data-stu-id="9497d-124">Specifies the current secure conversation settings.</span></span>  
  
### <a name="servicecertificate"></a><span data-ttu-id="9497d-125">ServiceCertificate</span><span class="sxs-lookup"><span data-stu-id="9497d-125">ServiceCertificate</span></span>  
 <span data-ttu-id="9497d-126">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="9497d-126">Data type: string</span></span>  
  
 <span data-ttu-id="9497d-127">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="9497d-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9497d-128">Certificato associato al servizio.</span><span class="sxs-lookup"><span data-stu-id="9497d-128">The certificate associated with this service.</span></span>  
  
### <a name="usernameauthentication"></a><span data-ttu-id="9497d-129">UserNameAuthentication</span><span class="sxs-lookup"><span data-stu-id="9497d-129">UserNameAuthentication</span></span>  
 <span data-ttu-id="9497d-130">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="9497d-130">Data type: string</span></span>  
  
 <span data-ttu-id="9497d-131">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="9497d-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9497d-132">Impostazioni di nome utente e password per il servizio.</span><span class="sxs-lookup"><span data-stu-id="9497d-132">The username/password settings for this service.</span></span>  
  
### <a name="windowsauthentication"></a><span data-ttu-id="9497d-133">WindowsAuthentication</span><span class="sxs-lookup"><span data-stu-id="9497d-133">WindowsAuthentication</span></span>  
 <span data-ttu-id="9497d-134">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="9497d-134">Data type: string</span></span>  
  
 <span data-ttu-id="9497d-135">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="9497d-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9497d-136">Impostazioni di autenticazione Windows per il servizio.</span><span class="sxs-lookup"><span data-stu-id="9497d-136">The Windows authentication settings for this service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9497d-137">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9497d-137">Requirements</span></span>  
  
|<span data-ttu-id="9497d-138">MOF</span><span class="sxs-lookup"><span data-stu-id="9497d-138">MOF</span></span>|<span data-ttu-id="9497d-139">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="9497d-139">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="9497d-140">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="9497d-140">Namespace</span></span>|<span data-ttu-id="9497d-141">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="9497d-141">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9497d-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9497d-142">See Also</span></span>  
 <xref:System.ServiceModel.Description.ServiceCredentials>
