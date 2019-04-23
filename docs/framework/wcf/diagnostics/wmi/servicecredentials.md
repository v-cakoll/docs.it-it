---
title: ServiceCredentials
ms.date: 03/30/2017
ms.assetid: 9c780793-4785-46f7-add9-ac1ebeadb614
ms.openlocfilehash: d9563bd3bfe067ad83bfa03e7c6375a9db933f14
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59772102"
---
# <a name="servicecredentials"></a><span data-ttu-id="dd663-102">ServiceCredentials</span><span class="sxs-lookup"><span data-stu-id="dd663-102">ServiceCredentials</span></span>
<span data-ttu-id="dd663-103">ServiceCredentials</span><span class="sxs-lookup"><span data-stu-id="dd663-103">ServiceCredentials</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd663-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dd663-104">Syntax</span></span>  
  
```csharp
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
  
## <a name="methods"></a><span data-ttu-id="dd663-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="dd663-105">Methods</span></span>  
 <span data-ttu-id="dd663-106">La classe ServiceCredentials non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="dd663-106">The ServiceCredentials class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="dd663-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="dd663-107">Properties</span></span>  
 <span data-ttu-id="dd663-108">La classe ServiceCredentials dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="dd663-108">The ServiceCredentials class has the following properties:</span></span>  
  
### <a name="clientcertificate"></a><span data-ttu-id="dd663-109">ClientCertificate</span><span class="sxs-lookup"><span data-stu-id="dd663-109">ClientCertificate</span></span>  
 <span data-ttu-id="dd663-110">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="dd663-110">Data type: string</span></span>  
  
 <span data-ttu-id="dd663-111">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="dd663-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="dd663-112">Impostazioni di provisioning e autenticazione dei certificati client per il servizio.</span><span class="sxs-lookup"><span data-stu-id="dd663-112">The client certificate authentication and provisioning settings for this service.</span></span>  
  
### <a name="issuedtokenauthentication"></a><span data-ttu-id="dd663-113">IssuedTokenAuthentication</span><span class="sxs-lookup"><span data-stu-id="dd663-113">IssuedTokenAuthentication</span></span>  
 <span data-ttu-id="dd663-114">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="dd663-114">Data type: string</span></span>  
  
 <span data-ttu-id="dd663-115">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="dd663-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="dd663-116">Impostazioni correnti di autenticazione del token rilasciato per il servizio.</span><span class="sxs-lookup"><span data-stu-id="dd663-116">The current issued token authentication settings for this service.</span></span>  
  
### <a name="peer"></a><span data-ttu-id="dd663-117">Peer</span><span class="sxs-lookup"><span data-stu-id="dd663-117">Peer</span></span>  
 <span data-ttu-id="dd663-118">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="dd663-118">Data type: string</span></span>  
  
 <span data-ttu-id="dd663-119">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="dd663-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="dd663-120">Impostazioni correnti di provisioning e autenticazione delle credenziali utilizzate dagli endpoint di trasporto del peer.</span><span class="sxs-lookup"><span data-stu-id="dd663-120">The current credential authentication and provisioning settings to be used by peer transport endpoints.</span></span>  
  
### <a name="secureconversationauthentication"></a><span data-ttu-id="dd663-121">SecureConversationAuthentication</span><span class="sxs-lookup"><span data-stu-id="dd663-121">SecureConversationAuthentication</span></span>  
 <span data-ttu-id="dd663-122">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="dd663-122">Data type: string</span></span>  
  
 <span data-ttu-id="dd663-123">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="dd663-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="dd663-124">Specifica le impostazioni correnti per le conversazioni protette.</span><span class="sxs-lookup"><span data-stu-id="dd663-124">Specifies the current secure conversation settings.</span></span>  
  
### <a name="servicecertificate"></a><span data-ttu-id="dd663-125">ServiceCertificate</span><span class="sxs-lookup"><span data-stu-id="dd663-125">ServiceCertificate</span></span>  
 <span data-ttu-id="dd663-126">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="dd663-126">Data type: string</span></span>  
  
 <span data-ttu-id="dd663-127">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="dd663-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="dd663-128">Certificato associato al servizio.</span><span class="sxs-lookup"><span data-stu-id="dd663-128">The certificate associated with this service.</span></span>  
  
### <a name="usernameauthentication"></a><span data-ttu-id="dd663-129">UserNameAuthentication</span><span class="sxs-lookup"><span data-stu-id="dd663-129">UserNameAuthentication</span></span>  
 <span data-ttu-id="dd663-130">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="dd663-130">Data type: string</span></span>  
  
 <span data-ttu-id="dd663-131">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="dd663-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="dd663-132">Impostazioni di nome utente e password per il servizio.</span><span class="sxs-lookup"><span data-stu-id="dd663-132">The username/password settings for this service.</span></span>  
  
### <a name="windowsauthentication"></a><span data-ttu-id="dd663-133">WindowsAuthentication</span><span class="sxs-lookup"><span data-stu-id="dd663-133">WindowsAuthentication</span></span>  
 <span data-ttu-id="dd663-134">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="dd663-134">Data type: string</span></span>  
  
 <span data-ttu-id="dd663-135">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="dd663-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="dd663-136">Impostazioni di autenticazione Windows per il servizio.</span><span class="sxs-lookup"><span data-stu-id="dd663-136">The Windows authentication settings for this service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dd663-137">Requisiti</span><span class="sxs-lookup"><span data-stu-id="dd663-137">Requirements</span></span>  
  
|<span data-ttu-id="dd663-138">MOF</span><span class="sxs-lookup"><span data-stu-id="dd663-138">MOF</span></span>|<span data-ttu-id="dd663-139">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="dd663-139">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="dd663-140">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="dd663-140">Namespace</span></span>|<span data-ttu-id="dd663-141">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="dd663-141">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dd663-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dd663-142">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceCredentials>
